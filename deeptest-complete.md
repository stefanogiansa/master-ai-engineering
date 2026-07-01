# DeepTest Complete

Domande aperte con risposta ragionata

---

## Come utilizzare questo documento

Questo DeepTest è pensato per verificare la comprensione reale degli argomenti studiati durante il Master AI Engineering.

Ogni domanda richiede una risposta argomentata.

Prima di leggere la soluzione, prova a rispondere autonomamente.

---

## Fondamenti di Machine Learning

## Domanda 1

### Cos’è realmente il Machine Learning?
### Risposta

Il Machine Learning è una disciplina dell’Intelligenza Artificiale che permette ai sistemi di apprendere automaticamente dai dati senza essere programmati con regole esplicite.

L’obiettivo non è memorizzare esempi, ma costruire un modello capace di generalizzare su dati mai osservati.

---

## Domanda 2

### Qual è la differenza tra classificazione e regressione?
### Risposta

La classificazione produce un insieme finito di categorie (ad esempio spam/non spam), mentre la regressione restituisce un valore numerico continuo (ad esempio il prezzo di una casa).

---

## Domanda 3

### Perché il preprocessing è così importante?
### Risposta

Perché la qualità del modello dipende fortemente dalla qualità dei dati.

Gestione dei valori mancanti, encoding, normalizzazione e standardizzazione possono migliorare significativamente le prestazioni degli algoritmi.

---

## Domanda 4

### Cosa significa che un modello generalizza?
### Risposta

Generalizzare significa ottenere buone prestazioni anche su dati non utilizzati durante l’addestramento.

È l’obiettivo principale del Machine Learning.

---

## Domanda 5

### Cos’è l’overfitting?
### Risposta

L’overfitting si verifica quando il modello apprende troppo bene il training set, compreso il rumore, perdendo la capacità di generalizzare.

Tipicamente:

- accuracy molto elevata sul training;
- accuracy inferiore sul test.

---

## Domanda 6

### Come si riduce l’overfitting?
### Risposta

Le principali tecniche sono:

- train/test split;
- cross validation;
- regolarizzazione;
- early stopping;
- Random Forest;
- raccolta di più dati.

---

## Domanda 7

### Perché Accuracy e F1-Score non misurano la stessa cosa?
### Risposta

Accuracy considera la percentuale totale di classificazioni corrette.

F1-Score combina Precision e Recall ed è molto più adatta ai dataset sbilanciati.

---

## Domanda 8

### Quando una Accuracy del 99% può essere fuorviante?
### Risposta

Quando il dataset è fortemente sbilanciato.

Ad esempio, se il 99% dei campioni appartiene alla stessa classe, un classificatore banale può ottenere il 99% di Accuracy senza essere realmente utile.

---

## Domanda 9

### Perché il Train/Test Split è indispensabile?
### Risposta

Perché permette di valutare il modello su dati mai osservati durante il training.

Senza questa separazione non sarebbe possibile stimare la capacità di generalizzazione.

---

## Domanda 10

### Perché il Machine Learning è considerato un problema di ottimizzazione?
### Risposta

Perché durante il training l’obiettivo consiste nel trovare i parametri che minimizzano una funzione di costo.

Molti algoritmi utilizzano il Gradient Descent per raggiungere questo obiettivo.

---

## Gradient Descent

## Domanda 11

### Qual è il ruolo del Learning Rate?
### Risposta

Controlla la dimensione dell’aggiornamento dei pesi.

Un valore troppo basso rallenta la convergenza, mentre un valore troppo elevato può impedire il raggiungimento del minimo.

---

## Domanda 12

### Perché il Gradient Descent segue la direzione opposta al gradiente?
### Risposta

Perché il gradiente indica la direzione di massima crescita della funzione di costo.

Muovendosi nella direzione opposta si riduce progressivamente l’errore.

---

## Domanda 13

### Qual è la differenza tra Batch, Mini-Batch e Stochastic Gradient Descent?
### Risposta

- Batch: utilizza tutto il dataset ad ogni aggiornamento.
- Mini-Batch: utilizza piccoli gruppi di campioni.
- Stochastic: aggiorna i pesi utilizzando un solo campione alla volta.

Il Mini-Batch rappresenta oggi la soluzione più utilizzata nelle reti neurali.

---

## Domanda 14

### Perché il Gradient Descent è un concetto trasversale del Machine Learning?
### Risposta

Perché viene utilizzato da numerosi algoritmi, tra cui Logistic Regression e Neural Networks, per ottimizzare i parametri del modello minimizzando la funzione di costo.

---

## Domanda 15

### Se dovessi spiegare il Gradient Descent a una persona senza conoscenze matematiche, come lo faresti?
### Risposta

Lo descriverei come una persona che, trovandosi su una montagna immersa nella nebbia, procede a piccoli passi sempre nella direzione di massima discesa fino a raggiungere il punto più basso della valle. Allo stesso modo, il Gradient Descent modifica progressivamente i parametri del modello per ridurre l’errore.

## Logistic Regression, Naive Bayes e Support Vector Machine

## Domanda 16

### Perché la Logistic Regression, nonostante il nome, è un algoritmo di classificazione?
### Risposta

La Logistic Regression non predice un valore numerico continuo, ma la probabilità che un’osservazione appartenga a una determinata classe.

Applicando una soglia (ad esempio 0,5), la probabilità viene trasformata in una classe.

Il termine “Regression” deriva dal modello matematico utilizzato, non dal tipo di problema risolto.

---

## Domanda 17

### Quali sono le principali ipotesi della Logistic Regression?
### Risposta

La Logistic Regression assume principalmente che:

- esista una relazione approssimativamente lineare tra le feature e il logit della probabilità;
- le osservazioni siano indipendenti;
- non vi sia una forte multicollinearità tra le feature.

Queste ipotesi influenzano direttamente le prestazioni del modello.

---

## Domanda 18

### Perché la Logistic Regression richiede normalmente la standardizzazione delle feature?
### Risposta

Il Gradient Descent converge più rapidamente quando le feature hanno scale confrontabili.

Inoltre, feature con ordini di grandezza molto diversi possono influenzare in modo sproporzionato l’ottimizzazione dei pesi.

---

## Domanda 19

### Qual è il principale vantaggio della Logistic Regression rispetto a modelli più complessi?
### Risposta

È semplice da addestrare, veloce, facilmente interpretabile e restituisce direttamente probabilità.

Per molti problemi rappresenta un eccellente modello di riferimento (baseline).

---

## Domanda 20

### In quali situazioni eviteresti la Logistic Regression?
### Risposta

Quando:

- le relazioni sono fortemente non lineari;
- il problema richiede una grande capacità di rappresentazione;
- sono disponibili grandi quantità di dati non strutturati come immagini o audio.

In questi casi possono risultare più adatti algoritmi come Random Forest o Neural Networks.

---

## Domanda 21

### Perché Naive Bayes viene definito “naive”?
### Risposta

Perché assume che tutte le feature siano indipendenti tra loro una volta nota la classe.

Questa ipotesi è raramente verificata nella pratica, ma semplifica enormemente il calcolo delle probabilità.

---

## Domanda 22

### Perché Naive Bayes funziona bene anche se l’ipotesi di indipendenza è spesso falsa?
### Risposta

Per la classificazione è spesso sufficiente confrontare le probabilità relative delle classi.

Anche se le probabilità assolute non sono perfette, l’algoritmo riesce frequentemente a identificare correttamente la classe più probabile.

---

## Domanda 23

### Perché Naive Bayes è particolarmente efficace nella classificazione del testo?
### Risposta

Nei problemi testuali ogni parola può essere trattata come una feature.

L’ipotesi di indipendenza tra le parole, pur non essendo rigorosamente vera, produce spesso risultati molto competitivi con costi computazionali estremamente ridotti.

---

## Domanda 24

### Qual è la differenza concettuale tra Logistic Regression e Naive Bayes?
### Risposta

La Logistic Regression apprende direttamente una frontiera decisionale ottimizzando una funzione di costo.

Naive Bayes, invece, costruisce un modello probabilistico basato sul Teorema di Bayes e sulle distribuzioni delle feature.

Entrambi possono produrre probabilità, ma il processo con cui le ottengono è completamente differente.

---

## Domanda 25

### In quale scenario sceglieresti Naive Bayes invece della Logistic Regression?
### Risposta

Ad esempio nella classificazione di email spam, documenti o recensioni, dove:

- le feature sono molto numerose;
- il training deve essere estremamente veloce;
- è disponibile un dataset testuale.

---

## Domanda 26

### Qual è l’obiettivo principale di una Support Vector Machine?
### Risposta

Trovare l’iperpiano che separa le classi massimizzando il margine tra esse.

Un margine più ampio favorisce generalmente una migliore capacità di generalizzazione.

---

## Domanda 27

### Che cosa rappresenta il margine in una SVM?
### Risposta

È la distanza tra l’iperpiano di separazione e i Support Vectors.

Massimizzare questa distanza rende il classificatore più robusto rispetto a piccole variazioni dei dati.

---

## Domanda 28

### Perché le SVM richiedono generalmente il feature scaling?
### Risposta

Perché si basano sul calcolo di distanze e prodotti scalari.

Feature con scale molto diverse altererebbero la geometria dello spazio e influenzerebbero negativamente la ricerca dell’iperpiano ottimale.

---

## Domanda 29

### Qual è il ruolo del parametro C in una SVM?
### Risposta

Il parametro C controlla il compromesso tra:

- massimizzazione del margine;
- penalizzazione degli errori di classificazione.

Valori elevati privilegiano la riduzione degli errori sul training set, mentre valori più piccoli consentono un margine più ampio.

---

## Domanda 30

### Quando preferiresti una SVM rispetto alla Logistic Regression?
### Risposta

Quando il dataset è di dimensioni medio-piccole e presenta confini decisionali complessi o non lineari.

Grazie al kernel trick, una SVM può modellare relazioni che una Logistic Regression non è in grado di rappresentare.

---

## Domanda di sintesi

## Domanda 31

### Dovendo classificare recensioni di prodotti, quali algoritmi prenderesti in considerazione e come motiveresti la scelta?
### Risposta

Una possibile strategia consiste nel confrontare:

- Naive Bayes, come baseline veloce ed efficace sul testo;
- Logistic Regression, se le feature testuali sono rappresentate tramite TF-IDF e si desidera un modello interpretabile;
- Neural Networks (o modelli NLP più avanzati) se il dataset è molto grande e l’obiettivo è massimizzare le prestazioni.

La scelta finale dipende dal compromesso tra accuratezza, interpretabilità, tempo di addestramento e disponibilità di dati.

## K-Nearest Neighbors, Decision Tree, Random Forest e Neural Networks

## Domanda 32

### Perché KNN viene definito un algoritmo “lazy”?
### Risposta

Perché durante il training non costruisce un vero modello.

Si limita a memorizzare il dataset e rimanda tutto il lavoro alla fase di inferenza, quando deve cercare i K vicini più prossimi.

---

## Domanda 33

### Qual è il principale svantaggio di KNN?
### Risposta

La fase di predizione è costosa.

Per classificare un nuovo campione è necessario confrontarlo con tutti (o molti) dei campioni del training set.

Per dataset molto grandi questo rende l’inferenza lenta.

---

## Domanda 34

### Perché KNN richiede normalmente la standardizzazione delle feature?
### Risposta

KNN basa le proprie decisioni sulle distanze.

Se una feature ha valori molto più grandi delle altre, finirà per dominare il calcolo della distanza, alterando la scelta dei vicini.

---

## Domanda 35

### Come influisce il valore di K sul comportamento dell’algoritmo?
### Risposta

Un valore di K troppo piccolo rende il modello molto sensibile al rumore e aumenta il rischio di overfitting.

Un valore troppo grande produce decisioni più stabili ma può portare a underfitting.

La scelta di K rappresenta quindi un compromesso tra flessibilità e robustezza.

---

## Domanda 36

### Quando sceglieresti KNN?
### Risposta

Quando:

- il dataset è piccolo;
- serve una baseline semplice;
- il training deve essere praticamente immediato;
- le relazioni tra i dati sono complesse ma locali.

---

## Domanda 37

### Perché un Decision Tree è considerato altamente interpretabile?
### Risposta

Perché ogni decisione deriva da una sequenza di regole esplicite.

È possibile seguire il percorso dalla radice alla foglia e spiegare facilmente il motivo di una classificazione.

---

## Domanda 38

### Perché i Decision Tree tendono all’overfitting?
### Risposta

Se non vengono limitati, possono continuare a suddividere il dataset fino a memorizzare anche il rumore presente nei dati.

Questo migliora le prestazioni sul training set ma peggiora la generalizzazione.

---

## Domanda 39

### Qual è il ruolo di Gini ed Entropia?
### Risposta

Entrambi misurano l’impurità di un nodo.

L’albero utilizza queste misure per scegliere lo split che separa meglio le classi.

L’obiettivo è ottenere nodi sempre più omogenei.

---

## Domanda 40

### Perché Decision Tree e Random Forest non richiedono normalmente il feature scaling?
### Risposta

Perché gli split vengono effettuati confrontando valori delle singole feature e non utilizzando distanze tra osservazioni.

Di conseguenza la scala delle variabili influisce molto meno rispetto ad algoritmi come SVM o KNN.

---

## Domanda 41

### Perché la Random Forest riduce l’overfitting?
### Risposta

Perché combina le predizioni di molti alberi differenti.

Ogni albero viene addestrato su un campione bootstrap e considera solo un sottoinsieme casuale delle feature.

L’aggregazione finale riduce la varianza e migliora la capacità di generalizzazione.

---

## Domanda 42

### Qual è il principale vantaggio della Random Forest rispetto a un singolo Decision Tree?
### Risposta

Generalmente offre una maggiore accuratezza ed è molto più robusta al rumore e agli outlier.

Il prezzo da pagare è una minore interpretabilità.

---

## Domanda 43

### Quando sceglieresti una Random Forest?
### Risposta

Quando:

- il dataset è tabellare;
- è richiesta un’elevata accuratezza;
- non è fondamentale interpretare ogni singola decisione;
- si desidera un algoritmo robusto con poco tuning.

---

## Domanda 44

### Perché le Neural Networks richiedono normalmente grandi quantità di dati?
### Risposta

Perché contengono un numero molto elevato di parametri.

Per apprenderli correttamente è necessario disporre di molti esempi, altrimenti aumenta il rischio di overfitting.

---

## Domanda 45

### Qual è il ruolo delle funzioni di attivazione?
### Risposta

Introducono non linearità nel modello.

Senza funzioni di attivazione, una rete composta da molti layer sarebbe equivalente a un semplice modello lineare.

---

## Domanda 46

### Qual è la differenza tra Forward Propagation e Backpropagation?
### Risposta

Durante la Forward Propagation i dati attraversano la rete producendo una predizione.

La Backpropagation calcola invece come modificare i pesi propagando l’errore all’indietro attraverso i layer.

---

## Domanda 47

### Perché le Neural Networks sono spesso considerate una “black box”?
### Risposta

Perché le decisioni dipendono dall’interazione di migliaia o milioni di parametri.

A differenza di un Decision Tree o di una Logistic Regression, è difficile spiegare in modo intuitivo il contributo di ogni singola feature.

---

## Domanda 48

### Quando una Neural Network è preferibile a una Random Forest?
### Risposta

Quando:

- il dataset è molto grande;
- i dati sono immagini, audio o testo;
- il problema richiede una capacità di rappresentazione molto elevata.

Su dataset tabellari di dimensioni contenute, una Random Forest può invece ottenere prestazioni comparabili con minore complessità.

---

## Domanda 49

### Dovendo classificare immagini mediche, quale algoritmo sceglieresti?
### Risposta

Una Neural Network convoluzionale (CNN), perché è progettata per apprendere automaticamente pattern spaziali complessi presenti nelle immagini.

Algoritmi classici come Logistic Regression o Random Forest richiederebbero una fase di Feature Engineering molto più estesa.

---

## Domanda 50

### Se un cliente richiedesse un modello facilmente spiegabile, quale algoritmo proporresti?
### Risposta

La scelta dipende dal problema, ma generalmente proporrei:

- Decision Tree, se è importante visualizzare le regole decisionali;
- Logistic Regression, se il problema è lineare e si desidera interpretare il contributo delle feature.

Eviterei invece Neural Networks quando la spiegabilità rappresenta un requisito fondamentale.

---

## Domanda di sintesi

## Domanda 51

### Hai un dataset tabellare con 200.000 osservazioni e 50 feature numeriche. Devi ottenere un’elevata accuratezza senza investire troppo tempo nel tuning. Quale algoritmo sceglieresti e perché?
### Risposta

La Random Forest rappresenta spesso una scelta eccellente.

Offre:

- elevate prestazioni su dati tabellari;
- robustezza all’overfitting;
- limitata necessità di preprocessing;
- pochi iperparametri critici rispetto ad algoritmi più complessi.

Una valida alternativa potrebbe essere una Gradient Boosting Machine (ad esempio XGBoost), ma tra gli algoritmi trattati nel Master la Random Forest è generalmente la soluzione più equilibrata.

## MLOps e scenari reali

## Domanda 52

### Qual è la differenza tra un modello addestrato e un modello in produzione?

### Risposta

Un modello addestrato è il risultato del processo di training.

Un modello in produzione è un sistema completo che:

- riceve richieste;
- produce predizioni;
- viene monitorato;
- può essere aggiornato senza interrompere il servizio.

L'addestramento rappresenta solo una fase del ciclo di vita.

---

## Domanda 53

### Perché MLOps è nato come disciplina?

### Risposta

Perché sviluppare un modello accurato non basta.

È necessario garantire:

- riproducibilità;
- versionamento;
- deployment;
- monitoraggio;
- aggiornamento continuo.

MLOps estende i principi di DevOps al Machine Learning, integrando anche aspetti di Data Engineering.

---

## Domanda 54

### Perché è importante versionare i modelli?

### Risposta

Il versionamento consente di:

- riprodurre esperimenti;
- confrontare versioni differenti;
- effettuare rollback in caso di problemi;
- sapere quale modello è stato utilizzato in produzione in un determinato momento.

---

## Domanda 55

### Qual è il ruolo di un Model Registry?

### Risposta

Il Model Registry è un archivio centralizzato che conserva:

- modelli addestrati;
- metadati;
- metriche;
- versioni;
- stato del modello (staging, production, archived).

Permette di gestire il ciclo di vita dei modelli in modo controllato.

---

## Domanda 56

### Perché Docker è così utilizzato in MLOps?

### Risposta

Docker consente di distribuire il modello insieme a tutte le sue dipendenze.

In questo modo il comportamento dell'applicazione rimane coerente tra ambiente di sviluppo, test e produzione.

---

## Domanda 57

### Qual è il ruolo di Kubernetes?

### Risposta

Kubernetes automatizza la gestione dei container.

Consente di:

- distribuire applicazioni;
- scalare automaticamente;
- riavviare servizi in errore;
- bilanciare il carico tra più istanze.

---

## Domanda 58

### Perché FastAPI è particolarmente adatto al Model Serving?

### Risposta

FastAPI permette di esporre rapidamente un modello tramite API REST.

Offre:

- alte prestazioni;
- validazione automatica dei dati con Pydantic;
- documentazione OpenAPI generata automaticamente;
- facilità di integrazione con applicazioni esterne.

---

## Domanda 59

### Qual è la differenza tra training e inference?

### Risposta

Durante il training il modello apprende i parametri dai dati.

Durante l'inference utilizza tali parametri per effettuare nuove predizioni.

Il training è normalmente molto più costoso dell'inference.

---

## Domanda 60

### Perché un modello può peggiorare nel tempo anche se il codice non cambia?

### Risposta

Perché cambiano i dati.

La distribuzione degli input può evolvere rispetto a quella utilizzata durante il training, riducendo progressivamente la qualità delle predizioni.

---

## Domanda 61

### Qual è la differenza tra Data Drift e Concept Drift?

### Risposta

Il Data Drift indica un cambiamento nella distribuzione delle feature di input.

Il Concept Drift riguarda invece il cambiamento della relazione tra input e target.

Entrambi possono compromettere le prestazioni del modello e richiedere nuove attività di addestramento.

---

## Domanda 62

### Perché il monitoring è fondamentale?

### Risposta

Perché permette di individuare tempestivamente:

- cali di accuratezza;
- aumento della latenza;
- errori di servizio;
- drift dei dati;
- anomalie operative.

Un modello non monitorato può degradare senza che nessuno se ne accorga.

---

## Domanda 63

### Quali metriche monitoreresti in produzione?

### Risposta

Dipende dal contesto, ma normalmente monitorerei:

- accuratezza (quando disponibile);
- latenza;
- throughput;
- tasso di errore;
- utilizzo delle risorse;
- Data Drift;
- Concept Drift.

---

## Domanda 64

### Quando è opportuno riaddestrare un modello?

### Risposta

Il retraining può essere eseguito:

- a intervalli regolari;
- quando viene rilevato un drift significativo;
- quando sono disponibili nuovi dati rappresentativi;
- quando le prestazioni scendono sotto una soglia definita.

---

## Domanda 65

### Immagina che un modello in produzione perda improvvisamente accuratezza. Come procederesti?

### Risposta

Una possibile strategia consiste nel:

1. verificare la qualità dei dati in ingresso;
2. controllare eventuali Data Drift o Concept Drift;
3. confrontare le metriche con le versioni precedenti;
4. analizzare eventuali errori di deployment;
5. decidere se effettuare rollback o retraining.

L'obiettivo è identificare la causa prima di modificare il modello.

---

## Domanda 66

### Hai sviluppato un modello eccellente, ma il cliente chiede di poter spiegare ogni decisione. Come ti comporti?

### Risposta

La scelta dipende dai requisiti di business.

Potrei:

- sostituire il modello con uno più interpretabile (ad esempio Logistic Regression o Decision Tree);
- utilizzare tecniche di Explainable AI (XAI) se il mantenimento del modello complesso è indispensabile.

La massima accuratezza non è sempre il criterio più importante.

---

## Domanda 67

### Qual è la competenza più importante acquisita durante il Master?

### Risposta

La capacità di affrontare un problema di Machine Learning in modo strutturato.

Ciò significa essere in grado di:

- comprendere il problema;
- preparare i dati;
- scegliere il modello più adatto;
- valutarne le prestazioni;
- distribuirlo in produzione;
- monitorarne il comportamento nel tempo.

Questa visione end-to-end rappresenta il principale risultato del percorso formativo.

---

## Deep Test Finale

## Domanda 68

### Ti viene affidato un nuovo progetto di Machine Learning. Quali sono, nell'ordine, le fasi che seguirai?

### Risposta

Un possibile workflow è il seguente:

1. comprendere il problema di business;
2. raccogliere e analizzare i dati;
3. eseguire il preprocessing;
4. suddividere il dataset;
5. scegliere uno o più algoritmi candidati;
6. addestrare i modelli;
7. valutarne le prestazioni con metriche adeguate;
8. selezionare il modello migliore;
9. distribuirlo tramite API;
10. monitorarlo in produzione;
11. pianificare il retraining.

Questo rappresenta il ciclo di vita completo di un progetto di Machine Learning.

---

---

## Deep Test Avanzato

## Domanda 69

### Perché non conviene scegliere un algoritmo solo in base all'Accuracy?

### Risposta

Perché l'Accuracy misura solo la percentuale complessiva di predizioni corrette e può nascondere problemi importanti, soprattutto nei dataset sbilanciati.

In questi casi è necessario osservare anche Precision, Recall, F1-Score, ROC-AUC e Confusion Matrix.

---

## Domanda 70

### Se un modello ha ottime prestazioni in validazione ma pessime in produzione, quali cause analizzeresti?

### Risposta

Analizzerei:

- differenze tra dati di training e dati reali;
- data leakage nella fase di sviluppo;
- preprocessing non coerente tra training e produzione;
- Data Drift;
- Concept Drift;
- bug nel servizio di inferenza;
- differenze di versione tra modello, librerie e ambiente.

---

## Domanda 71

### Perché la pipeline di preprocessing deve essere salvata insieme al modello?

### Risposta

Perché il modello è stato addestrato su dati trasformati in un certo modo.

Se in produzione si applica un preprocessing diverso, le feature ricevute dal modello non saranno coerenti con quelle viste durante il training.

Questo può degradare drasticamente le prestazioni.

---

## Domanda 72

### Perché Random Forest è spesso una scelta forte su dati tabellari?

### Risposta

Perché combina molti alberi decisionali, riduce la varianza, gestisce relazioni non lineari e richiede relativamente poco preprocessing.

È robusta, performante e spesso richiede meno tuning rispetto a modelli più complessi.

---

## Domanda 73

### Perché una rete neurale senza funzioni di attivazione sarebbe limitata?

### Risposta

Senza funzioni di attivazione, la composizione di più layer lineari rimarrebbe una trasformazione lineare.

La rete non sarebbe quindi in grado di modellare relazioni non lineari complesse.

Le funzioni di attivazione introducono la non linearità necessaria per aumentare la capacità espressiva del modello.

---

## Domanda 74

### Che cosa significa scegliere una baseline?

### Risposta

Scegliere una baseline significa addestrare un modello semplice come primo riferimento.

La baseline serve per capire se modelli più complessi producono davvero un miglioramento significativo.

Esempi comuni sono Logistic Regression, Naive Bayes o un Decision Tree semplice.

---

## Domanda 75

### Perché è utile confrontare più modelli sullo stesso dataset?

### Risposta

Perché non esiste un algoritmo migliore in assoluto.

Modelli diversi fanno ipotesi diverse sui dati e possono comportarsi in modo molto differente a seconda del problema.

Il confronto empirico permette di scegliere il modello più adatto al caso specifico.

---

## Domanda 76

### Come spiegheresti la differenza tra parametro e iperparametro?

### Risposta

Un parametro viene appreso automaticamente durante il training, ad esempio i pesi di una rete neurale.

Un iperparametro viene scelto prima o durante il processo di training e controlla il comportamento dell'algoritmo, ad esempio `K` in KNN, `C` in SVM o il learning rate.

---

## Domanda 77

### Perché il test set non deve essere usato per scegliere gli iperparametri?

### Risposta

Perché il test set deve rappresentare una valutazione finale imparziale.

Se viene usato durante il tuning, il modello viene indirettamente ottimizzato anche su quel set e la stima delle prestazioni finali diventa troppo ottimistica.

---

## Domanda 78

### Perché la Cross Validation fornisce una stima più robusta delle prestazioni?

### Risposta

Perché valuta il modello su più suddivisioni differenti del dataset.

In questo modo il risultato dipende meno da una singola divisione casuale train/test e rappresenta meglio la capacità di generalizzazione.

---

## Domanda 79

### Quando preferiresti un modello più semplice anche se leggermente meno accurato?

### Risposta

Quando sono importanti:

- interpretabilità;
- velocità di inferenza;
- facilità di manutenzione;
- vincoli normativi;
- stabilità in produzione;
- semplicità di deployment.

In molti contesti reali un modello leggermente meno accurato ma più comprensibile è preferibile a una black box.

---

## Domanda 80

### Cosa significa valutare un modello end-to-end?

### Risposta

Significa valutare non solo l'algoritmo, ma l'intero sistema:

- preprocessing;
- modello;
- API;
- latenza;
- robustezza;
- monitoring;
- comportamento sui dati reali.

In produzione, il modello è solo una parte del sistema complessivo.

---

## Domanda 81

### Come motiveresti la scelta di FastAPI per un progetto di model serving?

### Risposta

FastAPI è adatto perché consente di creare rapidamente API REST performanti, supporta la validazione automatica dei dati tramite Pydantic e genera documentazione interattiva tramite OpenAPI.

È quindi una scelta pratica per esporre modelli ML tramite endpoint HTTP.

---

## Domanda 82

### Perché il monitoring deve includere anche metriche tecniche e non solo metriche ML?

### Risposta

Perché un modello può essere accurato ma inutilizzabile se il servizio è lento, instabile o soggetto a errori.

In produzione bisogna monitorare anche latenza, throughput, error rate, memoria, CPU e disponibilità del servizio.

---

## Domanda 83

### Che differenza c'è tra errore del modello ed errore del sistema?

### Risposta

L'errore del modello riguarda la qualità delle predizioni.

L'errore del sistema può invece dipendere da API, preprocessing, infrastruttura, dipendenze, configurazione o problemi di deployment.

In MLOps è necessario distinguere queste due categorie per diagnosticare correttamente i problemi.

---

## Domanda 84

### Perché un modello deve essere riproducibile?

### Risposta

Perché deve essere possibile ricostruire come è stato generato un certo risultato.

La riproducibilità richiede versionamento di codice, dati, modello, dipendenze, configurazione e metriche.

È essenziale per debugging, audit, rollback e miglioramento continuo.

---

## Domanda 85

### Qual è il rischio principale di un deployment senza rollback?

### Risposta

Se la nuova versione del modello o dell'applicazione ha problemi, non è possibile tornare rapidamente alla versione precedente.

Questo può causare disservizi, predizioni errate e perdita di fiducia nel sistema.

---

## Domanda 86

### Come valuteresti se un retraining ha davvero migliorato il modello?

### Risposta

Confronterei la nuova versione con quella precedente usando:

- stesso dataset di validazione;
- metriche offline;
- test su dati recenti;
- eventuale A/B test;
- monitoraggio in produzione;
- analisi degli errori.

Il retraining non deve essere considerato automaticamente un miglioramento.

---

## Domanda 87

### Perché è importante documentare le assunzioni fatte durante lo sviluppo del modello?

### Risposta

Perché le assunzioni guidano scelte su dati, preprocessing, algoritmo, metriche e deployment.

Se non vengono documentate, diventa difficile capire perché il modello è stato costruito in un certo modo e quando tali assunzioni non sono più valide.

---

## Domanda 88

### Come collegheresti il capitolo sui fondamenti con MLOps?

### Risposta

I fondamenti spiegano come costruire e valutare un modello.

MLOps estende questi concetti al ciclo di vita completo, includendo deployment, monitoring, versionamento e retraining.

Senza una solida comprensione dei fondamenti, non è possibile gestire correttamente un modello in produzione.

---

## Domanda 89

### Qual è la differenza tra sapere usare una libreria e capire il Machine Learning?

### Risposta

Sapere usare una libreria significa conoscere strumenti e funzioni operative.

Capire il Machine Learning significa comprendere dati, ipotesi, metriche, limiti, trade-off e comportamento dei modelli.

Le librerie sono strumenti; la competenza consiste nel sapere quando e perché usarle.

---

## Domanda 90

### Qual è il messaggio più importante dell'intero Master?

### Risposta

Il Machine Learning non è solo addestrare modelli.

È un processo end-to-end che parte da un problema reale, passa attraverso dati, modelli e metriche, e arriva fino a deployment, monitoring e miglioramento continuo.

La competenza principale è saper collegare tutte queste fasi in modo coerente.

---

## Stato editoriale

**Stato:** FINAL 1.0

Il DeepTest raccoglie 90 domande aperte con risposta ragionata sui principali argomenti del Master AI Engineering.

L'obiettivo non è verificare la semplice memorizzazione dei concetti, ma la capacità di comprenderli, collegarli e applicarli in contesti reali.

Per un allenamento complementare basato su domande a risposta multipla si rimanda al documento `quiz-complete.md`.
