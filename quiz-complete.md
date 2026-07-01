# Quiz Complete

> Banca dati di quiz del Master AI Engineering

---

## Obiettivo

Questo documento raccoglie quiz a risposta multipla per verificare la conoscenza degli argomenti trattati nel repository.

Ogni domanda presenta quattro possibili risposte, una sola corretta, seguita dalla soluzione e da una breve spiegazione.

Il documento è organizzato per capitoli e può essere utilizzato sia per il ripasso sia per la simulazione dell'esame.

---

## Struttura del documento

- Fondamenti di Machine Learning
- Gradient Descent
- Logistic Regression
- Naive Bayes
- Support Vector Machine
- K-Nearest Neighbors
- Decision Tree
- Random Forest
- Neural Networks
- MLOps
- Quiz misti

---

## Convenzioni

Per ogni domanda utilizzare sempre il seguente formato:

```markdown
## Domanda N

Testo della domanda.

A. ...

B. ...

C. ...

D. ...

**Risposta corretta:** X

**Spiegazione**

...
```

---

## Fondamenti di Machine Learning

## Domanda 1

Che cosa indica il termine Machine Learning?

A. Un insieme di regole scritte manualmente per risolvere un problema.

B. Una disciplina che permette ai sistemi di apprendere dai dati.

C. Un linguaggio di programmazione per l'intelligenza artificiale.

D. Un metodo per creare solo reti neurali profonde.

**Risposta corretta:** B

**Spiegazione**

Il Machine Learning consente ai sistemi di apprendere pattern dai dati senza essere programmati tramite regole esplicite per ogni possibile caso.

---

## Domanda 2

Qual è la differenza principale tra classificazione e regressione?

A. La classificazione prevede categorie, la regressione valori continui.

B. La classificazione usa solo reti neurali, la regressione solo alberi.

C. La classificazione non richiede dati, la regressione sì.

D. Non esiste alcuna differenza.

**Risposta corretta:** A

**Spiegazione**

La classificazione assegna un campione a una classe discreta, mentre la regressione predice un valore numerico continuo.

---

## Domanda 3

Che cosa rappresentano le feature in un dataset?

A. Le variabili di input usate dal modello.

B. Le previsioni prodotte dal modello.

C. Gli errori del modello.

D. Le metriche finali.

**Risposta corretta:** A

**Spiegazione**

Le feature sono le variabili descrittive fornite al modello per produrre una predizione.

---

## Domanda 4

Che cosa rappresenta il target?

A. Il valore che il modello deve imparare a prevedere.

B. Il numero di righe del dataset.

C. Il nome del file di training.

D. Il learning rate dell'algoritmo.

**Risposta corretta:** A

**Spiegazione**

Il target è l'output desiderato: può essere una classe o un valore numerico.

---

## Domanda 5

Perché si divide il dataset in training set e test set?

A. Per aumentare artificialmente il numero di feature.

B. Per valutare il modello su dati non visti durante l'addestramento.

C. Per eliminare automaticamente gli outlier.

D. Per evitare di usare metriche.

**Risposta corretta:** B

**Spiegazione**

Il test set permette di stimare la capacità di generalizzazione del modello su dati nuovi.

---

## Domanda 6

A cosa serve il validation set?

A. A scegliere iperparametri e confrontare modelli durante lo sviluppo.

B. A sostituire sempre il training set.

C. A contenere solo dati non etichettati.

D. A calcolare il numero di feature.

**Risposta corretta:** A

**Spiegazione**

Il validation set viene usato per prendere decisioni di sviluppo senza contaminare il test set finale.

---

## Domanda 7

Che cosa significa generalizzazione?

A. Capacità del modello di memorizzare perfettamente il training set.

B. Capacità del modello di funzionare bene su dati nuovi.

C. Capacità del modello di usare solo una feature.

D. Capacità di eliminare la fase di training.

**Risposta corretta:** B

**Spiegazione**

Un modello generalizza quando mantiene buone prestazioni su esempi mai osservati durante il training.

---

## Domanda 8

Quando si verifica l'overfitting?

A. Quando il modello è troppo semplice e sbaglia sia training sia test.

B. Quando il modello apprende troppo bene il training set, incluso il rumore.

C. Quando non viene calcolata alcuna metrica.

D. Quando il dataset è sempre bilanciato.

**Risposta corretta:** B

**Spiegazione**

L'overfitting produce ottime prestazioni sul training set ma scarsa generalizzazione sul test set.

---

## Domanda 9

Quando si verifica l'underfitting?

A. Quando il modello è troppo complesso.

B. Quando il modello è troppo semplice per catturare la struttura del problema.

C. Quando il modello usa troppi dati.

D. Quando il test set è troppo piccolo.

**Risposta corretta:** B

**Spiegazione**

L'underfitting indica che il modello non riesce a rappresentare adeguatamente il problema, con errori elevati anche sul training set.

---

## Domanda 10

Che cosa indica il bias nel Bias-Variance Tradeoff?

A. L'errore dovuto a un modello troppo semplice.

B. La dimensione del dataset.

C. Il numero di classi.

D. La probabilità di un evento.

**Risposta corretta:** A

**Spiegazione**

Bias elevato indica che il modello fa assunzioni troppo semplici e tende all'underfitting.

---

## Domanda 11

Che cosa indica la variance nel Bias-Variance Tradeoff?

A. La sensibilità del modello alle variazioni del training set.

B. Il numero di epoche.

C. La probabilità condizionata.

D. Il valore massimo di una feature.

**Risposta corretta:** A

**Spiegazione**

Variance elevata indica che il modello è molto sensibile al dataset usato per il training e può andare in overfitting.

---

## Domanda 12

Qual è l'obiettivo del Bias-Variance Tradeoff?

A. Massimizzare sia bias sia variance.

B. Trovare un equilibrio tra semplicità e flessibilità del modello.

C. Eliminare completamente il test set.

D. Usare sempre reti neurali.

**Risposta corretta:** B

**Spiegazione**

Un buon modello deve evitare sia underfitting sia overfitting, bilanciando bias e variance.

---

## Domanda 13

Perché l'Accuracy può essere fuorviante?

A. Perché funziona solo con la regressione.

B. Perché su dataset sbilanciati può nascondere prestazioni scarse sulla classe minoritaria.

C. Perché è sempre uguale alla Precision.

D. Perché non si calcola sui classificatori.

**Risposta corretta:** B

**Spiegazione**

Se una classe è dominante, un modello può avere Accuracy alta pur ignorando quasi completamente la classe minoritaria.

---

## Domanda 14

Che cosa misura la Precision?

A. Tra i positivi predetti, quanti sono davvero positivi.

B. Tra i positivi reali, quanti sono stati trovati.

C. Il numero totale di feature.

D. L'errore medio assoluto.

**Risposta corretta:** A

**Spiegazione**

La Precision è utile quando si vuole ridurre il numero di falsi positivi.

---

## Domanda 15

Che cosa misura la Recall?

A. Tra i positivi reali, quanti sono stati individuati.

B. Tra i positivi predetti, quanti sono corretti.

C. La distanza euclidea media.

D. Il numero di parametri del modello.

**Risposta corretta:** A

**Spiegazione**

La Recall è importante quando è critico ridurre i falsi negativi.

---

## Domanda 16

Quando è particolarmente utile l'F1-Score?

A. Quando le classi sono sbilanciate e serve bilanciare Precision e Recall.

B. Quando si vuole misurare solo il tempo di training.

C. Quando il target è continuo.

D. Quando si usa solo clustering.

**Risposta corretta:** A

**Spiegazione**

L'F1-Score combina Precision e Recall tramite media armonica.

---

## Domanda 17

Che cosa rappresenta la Confusion Matrix?

A. Una tabella con TP, TN, FP e FN.

B. Una tecnica di scaling.

C. Un algoritmo supervisionato.

D. Una funzione di attivazione.

**Risposta corretta:** A

**Spiegazione**

La Confusion Matrix permette di analizzare in dettaglio gli errori di classificazione.

---

## Domanda 18

Che cosa indica il termine Data Leakage?

A. Uso accidentale di informazioni non disponibili nella realtà durante il training.

B. Perdita fisica del file CSV.

C. Compressione del dataset.

D. Uso di feature categoriche.

**Risposta corretta:** A

**Spiegazione**

Il Data Leakage produce valutazioni troppo ottimistiche perché il modello vede informazioni che non dovrebbe conoscere.

---

## Domanda 19

A cosa serve la Cross Validation?

A. A stimare le prestazioni in modo più robusto usando più suddivisioni del dataset.

B. A eliminare il bisogno di training.

C. A trasformare testo in immagini.

D. A creare automaticamente nuove classi.

**Risposta corretta:** A

**Spiegazione**

La Cross Validation riduce la dipendenza da una singola divisione train/test.

---

## Domanda 20

Quale tra questi algoritmi richiede più spesso feature scaling?

A. Decision Tree.

B. Random Forest.

C. KNN.

D. Alberi decisionali in generale.

**Risposta corretta:** C

**Spiegazione**

KNN usa distanze: feature con scale diverse possono dominare il calcolo.

---

## Domanda 21

Quale tra questi algoritmi normalmente non richiede scaling?

A. SVM.

B. KNN.

C. Logistic Regression.

D. Decision Tree.

**Risposta corretta:** D

**Spiegazione**

Gli alberi decisionali basano gli split su soglie delle singole feature e sono poco sensibili alla scala.

---

## Domanda 22

Che cosa significa preprocessing?

A. Preparazione e trasformazione dei dati prima del training.

B. Predizione finale del modello.

C. Eliminazione del validation set.

D. Pubblicazione del modello in produzione.

**Risposta corretta:** A

**Spiegazione**

Il preprocessing include pulizia, scaling, encoding e gestione dei valori mancanti.

---

## Domanda 23

Che cosa indica il termine Feature Engineering?

A. Creazione, trasformazione e selezione di feature utili.

B. Scelta casuale del test set.

C. Calcolo automatico dell'Accuracy.

D. Rimozione del modello.

**Risposta corretta:** A

**Spiegazione**

Il Feature Engineering migliora la rappresentazione dei dati fornita al modello.

---

## Domanda 24

Qual è la differenza tra parametro e iperparametro?

A. Il parametro è appreso dal modello, l'iperparametro viene scelto dall'esterno.

B. Sono sinonimi.

C. L'iperparametro è sempre il target.

D. Il parametro è sempre una metrica.

**Risposta corretta:** A

**Spiegazione**

Pesi e bias sono parametri; learning rate, K, C o max_depth sono iperparametri.

---

## Domanda 25

Perché il test set non dovrebbe essere usato per il tuning?

A. Perché perderebbe il ruolo di valutazione finale imparziale.

B. Perché il test set contiene sempre solo dati non numerici.

C. Perché il tuning non richiede dati.

D. Perché il test set serve solo per il deployment.

**Risposta corretta:** A

**Spiegazione**

Usare il test set per scegliere iperparametri porta a una stima troppo ottimistica delle prestazioni.

---

## Domanda 26

Che cosa misura la ROC Curve?

A. Il compromesso tra True Positive Rate e False Positive Rate al variare della soglia.

B. La media degli errori assoluti.

C. Il numero di epoche.

D. La profondità dell'albero.

**Risposta corretta:** A

**Spiegazione**

La ROC Curve aiuta a valutare un classificatore binario per diverse soglie decisionali.

---

## Domanda 27

Che cosa indica l'AUC?

A. L'area sotto la curva ROC.

B. Il numero di feature.

C. Il valore del learning rate.

D. La profondità massima di una rete.

**Risposta corretta:** A

**Spiegazione**

AUC sintetizza la capacità del classificatore di separare le classi.

---

## Domanda 28

Quale metrica è tipicamente usata per problemi di regressione?

A. RMSE.

B. Recall.

C. Precision.

D. Confusion Matrix.

**Risposta corretta:** A

**Spiegazione**

RMSE misura l'errore nei problemi con target continuo.

---

## Domanda 29

Che cosa indica R²?

A. La quota di variabilità del target spiegata dal modello.

B. La probabilità della classe positiva.

C. Il numero di vicini in KNN.

D. La loss della Logistic Regression.

**Risposta corretta:** A

**Spiegazione**

R² misura quanto il modello spiega la variabilità osservata nei dati.

---

## Domanda 30

Qual è una buona pratica generale prima di addestrare un modello?

A. Esplorare e comprendere i dati.

B. Saltare il preprocessing.

C. Usare direttamente il test set per il training.

D. Scegliere sempre il modello più complesso.

**Risposta corretta:** A

**Spiegazione**

L'analisi preliminare del dataset è essenziale per scegliere preprocessing, metriche e modelli adeguati.

---

## Domanda 31

Perché non esiste un algoritmo migliore in assoluto?

A. Perché ogni algoritmo fa ipotesi diverse ed è adatto a contesti diversi.

B. Perché tutti gli algoritmi producono gli stessi risultati.

C. Perché i dati non influenzano mai le prestazioni.

D. Perché solo le reti neurali sono realmente utili.

**Risposta corretta:** A

**Spiegazione**

La scelta dipende da dati, obiettivi, interpretabilità, risorse e vincoli applicativi.

---

## Domanda 32

Che cosa indica un modello con training error alto e test error alto?

A. Underfitting.

B. Overfitting.

C. Data leakage certo.

D. Perfetta generalizzazione.

**Risposta corretta:** A

**Spiegazione**

Errori elevati sia su training sia su test indicano che il modello non riesce a catturare la struttura del problema.

---

## Domanda 33

Che cosa indica un modello con training error basso e test error alto?

A. Overfitting.

B. Underfitting.

C. Assenza di training.

D. Dataset perfettamente bilanciato.

**Risposta corretta:** A

**Spiegazione**

Il modello ha appreso troppo il training set e generalizza male.

---

## Domanda 34

Quale tecnica può aiutare a ridurre l'overfitting?

A. Regolarizzazione.

B. Eliminare il test set.

C. Aumentare sempre la complessità del modello.

D. Usare solo Accuracy.

**Risposta corretta:** A

**Spiegazione**

La regolarizzazione penalizza modelli troppo complessi e favorisce la generalizzazione.

---

## Domanda 35

Che cosa significa dataset sbilanciato?

A. Le classi non hanno numerosità simili.

B. Le feature hanno tutte media zero.

C. Tutti i dati sono testuali.

D. Il dataset contiene solo valori continui.

**Risposta corretta:** A

**Spiegazione**

Nei dataset sbilanciati una o più classi sono molto più frequenti delle altre.

---

## Domanda 36

Quale metrica è particolarmente importante quando si vogliono ridurre i falsi negativi?

A. Recall.

B. Precision.

C. MSE.

D. R².

**Risposta corretta:** A

**Spiegazione**

La Recall misura quanti positivi reali vengono individuati dal modello.

---

## Domanda 37

Quale metrica è particolarmente importante quando si vogliono ridurre i falsi positivi?

A. Precision.

B. Recall.

C. RMSE.

D. Entropia.

**Risposta corretta:** A

**Spiegazione**

La Precision misura l'affidabilità delle predizioni positive.

---

## Domanda 38

Quale fase viene prima del training in un workflow ML corretto?

A. Preprocessing dei dati.

B. Monitoring in produzione.

C. Retraining automatico.

D. Calcolo della latenza API.

**Risposta corretta:** A

**Spiegazione**

I dati devono essere preparati prima di essere forniti al modello.

---

## Domanda 39

Che cosa significa inferenza?

A. Uso di un modello addestrato per produrre nuove predizioni.

B. Addestramento iniziale del modello.

C. Divisione del dataset.

D. Calcolo dell'entropia.

**Risposta corretta:** A

**Spiegazione**

L'inferenza è la fase in cui il modello viene usato su nuovi dati.

---

## Domanda 40

Qual è lo scopo principale del Machine Learning?

A. Costruire modelli capaci di apprendere dai dati e generalizzare.

B. Scrivere regole fisse per ogni caso possibile.

C. Eliminare completamente la valutazione.

D. Usare sempre lo stesso algoritmo.

**Risposta corretta:** A

**Spiegazione**

Il Machine Learning mira a costruire modelli che apprendono pattern dai dati e li applicano a nuovi esempi.

---

## Gradient Descent

## Domanda 41

Qual è l'obiettivo principale del Gradient Descent?

A. Massimizzare il numero di feature.

B. Minimizzare una funzione di costo.

C. Eliminare il training set.

D. Convertire testo in vettori.

**Risposta corretta:** B

**Spiegazione**

Il Gradient Descent aggiorna iterativamente i parametri del modello per ridurre il valore della funzione di costo.

---

## Domanda 42

Che cosa rappresenta il gradiente?

A. La direzione di massima crescita della funzione di costo.

B. Il numero di classi del dataset.

C. La probabilità della classe positiva.

D. Il valore medio delle feature.

**Risposta corretta:** A

**Spiegazione**

Il gradiente indica la direzione in cui la funzione cresce più rapidamente; per minimizzarla ci si muove nella direzione opposta.

---

## Domanda 43

Perché il Gradient Descent aggiorna i pesi nella direzione opposta al gradiente?

A. Per aumentare la loss.

B. Per ridurre progressivamente la funzione di costo.

C. Per eliminare i dati rumorosi.

D. Per rendere il modello non supervisionato.

**Risposta corretta:** B

**Spiegazione**

Muoversi contro il gradiente permette di scendere verso valori più bassi della funzione di costo.

---

## Domanda 44

Che cosa controlla il learning rate?

A. La dimensione del passo di aggiornamento dei pesi.

B. Il numero di classi.

C. Il tipo di metrica usata.

D. La profondità di un albero decisionale.

**Risposta corretta:** A

**Spiegazione**

Il learning rate stabilisce quanto grandi sono gli aggiornamenti dei parametri ad ogni iterazione.

---

## Domanda 45

Che cosa può accadere se il learning rate è troppo alto?

A. Il modello può divergere o oscillare senza convergere.

B. Il modello non usa più feature numeriche.

C. La loss diventa sempre zero.

D. Il training set viene eliminato.

**Risposta corretta:** A

**Spiegazione**

Passi troppo grandi possono superare il minimo e rendere l'ottimizzazione instabile.

---

## Domanda 46

Che cosa può accadere se il learning rate è troppo basso?

A. La convergenza può diventare molto lenta.

B. Il modello diventa automaticamente una Random Forest.

C. La funzione di costo non viene calcolata.

D. Le feature vengono duplicate.

**Risposta corretta:** A

**Spiegazione**

Un learning rate troppo piccolo produce aggiornamenti minimi e richiede molte iterazioni.

---

## Domanda 47

Quale variante del Gradient Descent usa tutto il dataset ad ogni aggiornamento?

A. Batch Gradient Descent.

B. Stochastic Gradient Descent.

C. Mini-Batch Gradient Descent.

D. Kernel Gradient Descent.

**Risposta corretta:** A

**Spiegazione**

Il Batch Gradient Descent calcola il gradiente usando l'intero training set.

---

## Domanda 48

Quale variante aggiorna i pesi usando un singolo campione alla volta?

A. Stochastic Gradient Descent.

B. Batch Gradient Descent.

C. Random Forest.

D. Cross Validation.

**Risposta corretta:** A

**Spiegazione**

Lo Stochastic Gradient Descent aggiorna i parametri dopo ogni singolo esempio.

---

## Domanda 49

Perché il Mini-Batch Gradient Descent è molto usato nelle reti neurali?

A. Bilancia efficienza computazionale e stabilità degli aggiornamenti.

B. Elimina completamente il rischio di overfitting.

C. Non richiede una funzione di costo.

D. Funziona solo con dati categorici.

**Risposta corretta:** A

**Spiegazione**

I mini-batch permettono aggiornamenti più efficienti rispetto allo stochastic puro e meno costosi del batch completo.

---

## Domanda 50

Che cosa indica la convergenza del Gradient Descent?

A. La stabilizzazione della funzione di costo verso un minimo.

B. L'aumento indefinito della loss.

C. Il passaggio da classificazione a regressione.

D. La rimozione dei parametri del modello.

**Risposta corretta:** A

**Spiegazione**

Quando la loss smette di diminuire significativamente, l'ottimizzazione può essere considerata vicina alla convergenza.

---

## Domanda 51

Perché è utile monitorare la loss durante il training?

A. Per capire se il modello sta convergendo, oscillando o divergendo.

B. Per calcolare direttamente il numero di classi.

C. Per sostituire il test set.

D. Per evitare ogni preprocessing.

**Risposta corretta:** A

**Spiegazione**

L'andamento della loss permette di diagnosticare problemi di learning rate, normalizzazione o ottimizzazione.

---

## Domanda 52

Perché la normalizzazione delle feature può aiutare il Gradient Descent?

A. Perché rende la superficie della loss più regolare e migliora la convergenza.

B. Perché elimina tutte le classi minoritarie.

C. Perché sostituisce la funzione di costo.

D. Perché impedisce l'uso di pesi.

**Risposta corretta:** A

**Spiegazione**

Feature su scale molto diverse possono rendere il percorso di ottimizzazione inefficiente e causare traiettorie a zig-zag.

---

## Domanda 53

Quale tra questi algoritmi usa direttamente concetti di Gradient Descent?

A. Logistic Regression.

B. KNN puro.

C. Random Forest.

D. Decision Tree classico.

**Risposta corretta:** A

**Spiegazione**

La Logistic Regression può essere addestrata minimizzando la Log Loss tramite metodi di ottimizzazione basati sul gradiente.

---

## Domanda 54

Che cosa sono Adam, RMSProp e AdaGrad?

A. Ottimizzatori adattivi derivati dall'idea del Gradient Descent.

B. Metriche di classificazione.

C. Algoritmi di clustering.

D. Tecniche di encoding categorico.

**Risposta corretta:** A

**Spiegazione**

Questi ottimizzatori modificano dinamicamente il passo di apprendimento usando informazioni sui gradienti passati.

---

## Domanda 55

Quale affermazione è corretta?

A. Il Gradient Descent è un metodo di ottimizzazione, non un classificatore.

B. Il Gradient Descent è identico a Naive Bayes.

C. Il Gradient Descent non usa mai una loss.

D. Il Gradient Descent serve solo per Random Forest.

**Risposta corretta:** A

**Spiegazione**

Il Gradient Descent è una tecnica generale per minimizzare funzioni di costo e può essere usato in diversi modelli.

---

## Logistic Regression

## Domanda 56

Perché la Logistic Regression è un algoritmo di classificazione nonostante il nome?

A. Perché produce una probabilità di appartenenza a una classe.

B. Perché predice sempre valori continui non limitati.

C. Perché funziona solo con serie temporali.

D. Perché non usa dati etichettati.

**Risposta corretta:** A

**Spiegazione**

La Logistic Regression stima una probabilità e poi applica una soglia per assegnare una classe.

---

## Domanda 57

Quale funzione trasforma il valore lineare `z` in una probabilità tra 0 e 1?

A. Sigmoide.

B. Gini.

C. Entropia.

D. Distanza euclidea.

**Risposta corretta:** A

**Spiegazione**

La funzione sigmoide comprime qualsiasi valore reale nell'intervallo `[0,1]`.

---

## Domanda 58

Qual è la formula concettuale della combinazione lineare nella Logistic Regression?

A. `z = w · x + b`.

B. `K = sqrt(x)`.

C. `Gini = 1 - Σpi²`.

D. `TP / (TP + FP)`.

**Risposta corretta:** A

**Spiegazione**

Il modello calcola prima una combinazione lineare delle feature e poi applica la sigmoide.

---

## Domanda 59

Quale soglia viene spesso usata nella classificazione binaria con Logistic Regression?

A. 0.5.

B. 10.

C. -1.

D. Il numero di feature.

**Risposta corretta:** A

**Spiegazione**

Per default, probabilità maggiori o uguali a 0.5 vengono spesso assegnate alla classe positiva.

---

## Domanda 60

Che cosa rappresenta la decision boundary nella Logistic Regression?

A. Il confine che separa le classi.

B. La matrice delle metriche.

C. Il numero di fold della Cross Validation.

D. Il dataset originale.

**Risposta corretta:** A

**Spiegazione**

La decision boundary è la superficie che separa le regioni assegnate alle diverse classi.

---

## Domanda 61

Quale funzione di costo è tipicamente usata nella Logistic Regression binaria?

A. Binary Cross Entropy.

B. Gini Impurity.

C. Distanza Manhattan.

D. Information Gain.

**Risposta corretta:** A

**Spiegazione**

La Binary Cross Entropy misura l'errore tra probabilità predette e classi reali binarie.

---

## Domanda 62

Perché la MSE non è la scelta ideale per la Logistic Regression?

A. Perché può rendere l'ottimizzazione meno efficace con la sigmoide.

B. Perché non esiste per valori numerici.

C. Perché è usata solo da KNN.

D. Perché richiede sempre Random Forest.

**Risposta corretta:** A

**Spiegazione**

La Log Loss è più adatta alla classificazione probabilistica e penalizza fortemente predizioni sicure ma errate.

---

## Domanda 63

Che cosa indica un coefficiente positivo nella Logistic Regression?

A. Aumenta il log-odds della classe positiva.

B. Elimina la feature dal modello.

C. Riduce sempre l'Accuracy.

D. Indica che la feature è categorica.

**Risposta corretta:** A

**Spiegazione**

Un coefficiente positivo aumenta la probabilità stimata della classe positiva, a parità delle altre variabili.

---

## Domanda 64

Perché la Logistic Regression è considerata interpretabile?

A. Perché i coefficienti indicano il contributo delle feature.

B. Perché non ha parametri.

C. Perché non richiede dati.

D. Perché è sempre non lineare.

**Risposta corretta:** A

**Spiegazione**

I coefficienti permettono di capire come ciascuna feature influenza la probabilità stimata.

---

## Domanda 65

Perché si usa spesso `StandardScaler` con Logistic Regression?

A. Per migliorare la convergenza e rendere confrontabili le feature.

B. Per trasformarla in un Decision Tree.

C. Per eliminare la necessità di metriche.

D. Per creare automaticamente nuove classi.

**Risposta corretta:** A

**Spiegazione**

La Logistic Regression è sensibile alla scala delle feature, soprattutto quando addestrata con metodi iterativi.

---

## Domanda 66

Che cosa controlla il parametro `C` in Logistic Regression di scikit-learn?

A. L'inverso della forza della regolarizzazione.

B. Il numero di classi obbligatorio.

C. La dimensione del test set.

D. Il tipo di encoding testuale.

**Risposta corretta:** A

**Spiegazione**

Valori piccoli di `C` indicano maggiore regolarizzazione; valori grandi indicano minore regolarizzazione.

---

## Domanda 67

Che effetto ha la regolarizzazione L2?

A. Penalizza coefficienti grandi senza portarli necessariamente a zero.

B. Elimina sempre tutte le feature.

C. Aumenta sempre l'overfitting.

D. Disattiva la funzione sigmoide.

**Risposta corretta:** A

**Spiegazione**

La L2 riduce l'ampiezza dei pesi e favorisce modelli più stabili.

---

## Domanda 68

Che effetto ha la regolarizzazione L1?

A. Può portare alcuni coefficienti esattamente a zero.

B. Impedisce la classificazione binaria.

C. Rende la loss non calcolabile.

D. È usata solo nei Decision Tree.

**Risposta corretta:** A

**Spiegazione**

La L1 può agire come selezione automatica delle feature.

---

## Domanda 69

Quale strategia consente alla Logistic Regression di gestire problemi multiclasse?

A. One-vs-Rest o Multinomial Logistic Regression.

B. Solo KNN.

C. Solo Gini Impurity.

D. Solo Bootstrap.

**Risposta corretta:** A

**Spiegazione**

La Logistic Regression può essere estesa alla classificazione multiclasse tramite strategie OvR o multinomiali.

---

## Domanda 70

Quando la Logistic Regression è una buona scelta?

A. Quando serve un modello veloce, interpretabile e probabilistico.

B. Quando il dataset contiene solo immagini ad alta risoluzione.

C. Quando non esistono feature.

D. Quando si vuole evitare qualsiasi valutazione.

**Risposta corretta:** A

**Spiegazione**

La Logistic Regression è spesso una baseline forte e interpretabile per problemi di classificazione lineare o quasi lineare.

---

## Domanda 71

Quando eviteresti Logistic Regression?

A. Quando le relazioni sono fortemente non lineari e complesse.

B. Quando serve interpretabilità.

C. Quando il problema è binario.

D. Quando le feature sono numeriche.

**Risposta corretta:** A

**Spiegazione**

La Logistic Regression ha decision boundary lineare e può non rappresentare bene pattern complessi.

---

## Domanda 72

Che cosa restituisce `predict_proba()`?

A. Le probabilità associate alle classi.

B. Solo il numero di feature.

C. Il training set originale.

D. Il valore di Gini.

**Risposta corretta:** A

**Spiegazione**

`predict_proba()` restituisce la probabilità stimata per ciascuna classe.

---

## Domanda 73

Perché una pipeline è utile con Logistic Regression?

A. Per applicare coerentemente preprocessing e modello in training e inferenza.

B. Per evitare completamente il training.

C. Per sostituire il target.

D. Per impedire l'uso di metriche.

**Risposta corretta:** A

**Spiegazione**

La pipeline riduce il rischio di errori, soprattutto nello scaling applicato ai dati nuovi.

---

## Domanda 74

Quale metrica è utile se il costo dei falsi negativi è elevato?

A. Recall.

B. Solo Accuracy.

C. MSE.

D. R².

**Risposta corretta:** A

**Spiegazione**

La Recall misura la capacità di intercettare i positivi reali.

---

## Domanda 75

Quale metrica è utile se il costo dei falsi positivi è elevato?

A. Precision.

B. RMSE.

C. Numero di epoche.

D. Learning rate.

**Risposta corretta:** A

**Spiegazione**

La Precision indica quanto sono affidabili le predizioni positive.

---

## Domanda 76

Che cosa sono gli odds?

A. Il rapporto tra probabilità dell'evento e probabilità del non evento.

B. Il numero di alberi in una foresta.

C. La distanza tra due punti.

D. Il valore della Recall.

**Risposta corretta:** A

**Spiegazione**

Gli odds sono `p / (1 - p)` e sono alla base dell'interpretazione logit.

---

## Domanda 77

Che cosa indica il logit?

A. Il logaritmo degli odds.

B. La radice quadrata della loss.

C. Il numero di support vectors.

D. La profondità massima di un albero.

**Risposta corretta:** A

**Spiegazione**

La Logistic Regression assume che il logit sia una combinazione lineare delle feature.

---

## Domanda 78

Quale affermazione sulla Logistic Regression è corretta?

A. È un classificatore lineare probabilistico.

B. È sempre un modello non supervisionato.

C. È identica a KNN.

D. Non produce probabilità.

**Risposta corretta:** A

**Spiegazione**

La Logistic Regression modella la probabilità della classe positiva usando una funzione sigmoide applicata a una combinazione lineare.

---

## Domanda 79

Perché può comparire un warning di mancata convergenza in scikit-learn?

A. Perché il numero massimo di iterazioni è insufficiente o i dati non sono ben scalati.

B. Perché Logistic Regression non richiede mai training.

C. Perché il modello non ha coefficienti.

D. Perché la funzione sigmoide non esiste.

**Risposta corretta:** A

**Spiegazione**

Aumentare `max_iter` e scalare le feature può aiutare il solver a convergere.

---

## Domanda 80

Quale ruolo ha la soglia decisionale?

A. Trasforma una probabilità in una classe.

B. Sostituisce la funzione di costo.

C. Elimina i falsi positivi per definizione.

D. Impedisce la valutazione del modello.

**Risposta corretta:** A

**Spiegazione**

La soglia decide da quale probabilità in poi assegnare la classe positiva.

---

## Naive Bayes

## Domanda 81

Su quale principio matematico si basa Naive Bayes?

A. Teorema di Bayes.

B. Gradient Descent.

C. Gini Impurity.

D. Distanza Euclidea.

**Risposta corretta:** A

**Spiegazione**

Naive Bayes usa il Teorema di Bayes per stimare la probabilità di una classe date le feature osservate.

---

## Domanda 82

Perché Naive Bayes viene definito "naive"?

A. Perché assume indipendenza condizionata tra le feature.

B. Perché non usa probabilità.

C. Perché richiede sempre reti neurali.

D. Perché funziona solo con dati non etichettati.

**Risposta corretta:** A

**Spiegazione**

L'ipotesi naive consiste nel considerare le feature indipendenti tra loro una volta nota la classe.

---

## Domanda 83

Che cosa rappresenta la prior probability in Naive Bayes?

A. La probabilità iniziale di una classe prima di osservare le feature.

B. La probabilità finale dopo il deployment.

C. Il numero di parole in un documento.

D. La distanza tra due campioni.

**Risposta corretta:** A

**Spiegazione**

La prior è la probabilità della classe prima di considerare le evidenze fornite dalle feature.

---

## Domanda 84

Che cosa rappresenta la likelihood?

A. La probabilità di osservare le feature data una classe.

B. Il learning rate del modello.

C. La profondità dell'albero.

D. Il numero di epoche.

**Risposta corretta:** A

**Spiegazione**

La likelihood misura quanto le feature osservate siano compatibili con una determinata classe.

---

## Domanda 85

Che cosa rappresenta la posterior probability?

A. La probabilità della classe dopo aver osservato le feature.

B. La probabilità prima di osservare i dati.

C. Il valore del parametro K.

D. Il numero di support vectors.

**Risposta corretta:** A

**Spiegazione**

La posterior è la probabilità aggiornata della classe alla luce delle evidenze osservate.

---

## Domanda 86

In quale ambito Naive Bayes è particolarmente utilizzato?

A. Classificazione testuale.

B. Segmentazione di immagini mediche tramite CNN.

C. Orchestrazione di container.

D. Regressione lineare continua.

**Risposta corretta:** A

**Spiegazione**

Naive Bayes è molto efficace su testi, spam detection e classificazione documentale.

---

## Domanda 87

Perché Naive Bayes è veloce da addestrare?

A. Perché stima probabilità dalle frequenze invece di ottimizzare iterativamente pesi complessi.

B. Perché usa sempre GPU.

C. Perché non richiede etichette.

D. Perché calcola il margine massimo.

**Risposta corretta:** A

**Spiegazione**

Il training consiste principalmente nel calcolo di frequenze/probabilità condizionate.

---

## Domanda 88

Quale variante di Naive Bayes è spesso usata per conteggi di parole?

A. Multinomial Naive Bayes.

B. Gaussian Naive Bayes.

C. Bernoulli Naive Bayes.

D. RBF Naive Bayes.

**Risposta corretta:** A

**Spiegazione**

Multinomial Naive Bayes è adatto a feature che rappresentano conteggi, come le frequenze delle parole.

---

## Domanda 89

Quale variante è adatta a feature continue modellate con distribuzione normale?

A. Gaussian Naive Bayes.

B. Multinomial Naive Bayes.

C. Bernoulli Naive Bayes.

D. Kernel Naive Bayes.

**Risposta corretta:** A

**Spiegazione**

Gaussian Naive Bayes assume che le feature continue seguano una distribuzione gaussiana per ciascuna classe.

---

## Domanda 90

Quale variante è adatta a feature binarie presenza/assenza?

A. Bernoulli Naive Bayes.

B. Gaussian Naive Bayes.

C. Multinomial Naive Bayes.

D. Linear Naive Bayes.

**Risposta corretta:** A

**Spiegazione**

Bernoulli Naive Bayes lavora bene con feature binarie, ad esempio parola presente o assente.

---

## Domanda 91

Perché si usa lo smoothing in Naive Bayes?

A. Per evitare probabilità nulle per feature mai osservate in una classe.

B. Per aumentare il learning rate.

C. Per eliminare il test set.

D. Per calcolare la distanza Manhattan.

**Risposta corretta:** A

**Spiegazione**

Lo smoothing, come Laplace smoothing, impedisce che una singola probabilità zero annulli l'intero prodotto delle probabilità.

---

## Domanda 92

Naive Bayes richiede normalmente feature scaling?

A. Generalmente no.

B. Sempre sì.

C. Solo se si usa Random Forest.

D. Solo se il target è numerico continuo.

**Risposta corretta:** A

**Spiegazione**

Naive Bayes si basa su probabilità e distribuzioni, non su distanze geometriche come KNN o SVM.

---

## Domanda 93

Qual è un limite importante di Naive Bayes?

A. L'ipotesi di indipendenza tra feature è spesso irrealistica.

B. Richiede sempre milioni di dati.

C. Non può fare classificazione.

D. Non produce mai probabilità.

**Risposta corretta:** A

**Spiegazione**

Nella realtà le feature sono spesso correlate, ma il modello può funzionare comunque bene in molti compiti pratici.

---

## Domanda 94

Perché Naive Bayes può funzionare bene anche con l'ipotesi naive non vera?

A. Perché spesso basta ordinare correttamente le classi per probabilità relativa.

B. Perché ignora completamente le feature.

C. Perché usa sempre backpropagation.

D. Perché non usa il target.

**Risposta corretta:** A

**Spiegazione**

Anche se le probabilità assolute non sono perfette, il classificatore può scegliere correttamente la classe più probabile.

---

## Domanda 95

In una classificazione spam/non spam, cosa possono rappresentare le feature?

A. Presenza o frequenza delle parole.

B. Il numero di alberi.

C. Il valore di C della SVM.

D. La profondità massima della rete.

**Risposta corretta:** A

**Spiegazione**

Nel testo, parole o token vengono trasformati in feature numeriche tramite tecniche di vectorization.

---

## Domanda 96

Quale affermazione su Naive Bayes è corretta?

A. È spesso una baseline forte per classificazione testuale.

B. È sempre più lento di una rete neurale profonda.

C. Non può essere usato con dati etichettati.

D. Richiede obbligatoriamente feature scaling.

**Risposta corretta:** A

**Spiegazione**

Naive Bayes è semplice, veloce e spesso sorprendentemente efficace su testo.

---

## Domanda 97

Quale problema può verificarsi senza smoothing?

A. Una probabilità condizionata pari a zero può annullare il prodotto totale.

B. Il modello diventa automaticamente una SVM.

C. Il training set viene duplicato.

D. La prior diventa sempre uguale a uno.

**Risposta corretta:** A

**Spiegazione**

Nel prodotto delle probabilità, un solo fattore zero porta tutta la probabilità della classe a zero.

---

## Domanda 98

Che cosa fa CountVectorizer in un workflow testuale?

A. Trasforma documenti in vettori di conteggi di parole/token.

B. Addestra una Random Forest.

C. Calcola la ROC Curve.

D. Esegue deployment su Kubernetes.

**Risposta corretta:** A

**Spiegazione**

CountVectorizer converte testo grezzo in una matrice numerica utilizzabile dagli algoritmi.

---

## Domanda 99

Che cosa rappresenta TF-IDF?

A. Una pesatura che valorizza parole frequenti in un documento ma non troppo comuni nel corpus.

B. Una metrica di regressione.

C. Una funzione di attivazione.

D. Un algoritmo di clustering.

**Risposta corretta:** A

**Spiegazione**

TF-IDF riduce il peso delle parole troppo comuni e aumenta quello delle parole più informative.

---

## Domanda 100

Quando sceglieresti Naive Bayes?

A. Quando serve un modello veloce per classificazione testuale o una baseline probabilistica.

B. Quando si deve riconoscere immagini complesse con milioni di pixel.

C. Quando serve orchestrare container.

D. Quando il target è sempre continuo.

**Risposta corretta:** A

**Spiegazione**

Naive Bayes è ideale quando semplicità, velocità e buone prestazioni sul testo sono prioritarie.

---

## Support Vector Machine

## Domanda 101

Qual è l'obiettivo principale di una SVM?

A. Trovare l'iperpiano che separa le classi massimizzando il margine.

B. Calcolare frequenze di parole.

C. Costruire sempre molti alberi.

D. Eseguire inferenza tramite API REST.

**Risposta corretta:** A

**Spiegazione**

La SVM cerca il confine decisionale con il margine più ampio tra le classi.

---

## Domanda 102

Che cosa rappresenta il margine in una SVM?

A. La distanza tra l'iperpiano e i support vectors.

B. Il numero di epoche.

C. La probabilità della classe positiva.

D. Il valore della Recall.

**Risposta corretta:** A

**Spiegazione**

Massimizzare il margine rende il classificatore più robusto e meno sensibile a piccole variazioni.

---

## Domanda 103

Che cosa sono i support vectors?

A. I punti più vicini all'iperpiano che determinano il margine.

B. Tutte le feature categoriche.

C. I pesi di una rete neurale.

D. Le metriche di regressione.

**Risposta corretta:** A

**Spiegazione**

I support vectors sono i campioni più importanti per definire posizione e margine dell'iperpiano.

---

## Domanda 104

Perché le SVM richiedono spesso feature scaling?

A. Perché margini, distanze e prodotti scalari sono influenzati dalla scala delle feature.

B. Perché usano sempre alberi decisionali.

C. Perché non accettano dati numerici.

D. Perché eliminano automaticamente il bias.

**Risposta corretta:** A

**Spiegazione**

Feature su scale diverse alterano la geometria dello spazio e possono compromettere la separazione.

---

## Domanda 105

Che cosa controlla il parametro `C` in una SVM?

A. Il compromesso tra margine ampio e penalizzazione degli errori.

B. Il numero di fold della Cross Validation.

C. Il numero di alberi.

D. La dimensione del batch.

**Risposta corretta:** A

**Spiegazione**

Valori alti di `C` penalizzano molto gli errori; valori bassi consentono più violazioni del margine.

---

## Domanda 106

Che effetto tende ad avere un valore molto alto di `C`?

A. Margine più stretto e maggiore rischio di overfitting.

B. Margine sempre infinito.

C. Eliminazione del kernel.

D. Conversione in Naive Bayes.

**Risposta corretta:** A

**Spiegazione**

Un valore alto forza il modello a classificare correttamente più esempi di training, anche a costo di un margine meno robusto.

---

## Domanda 107

Che effetto tende ad avere un valore basso di `C`?

A. Maggiore tolleranza agli errori e margine più ampio.

B. Nessuna tolleranza agli errori.

C. Training nullo.

D. Uso automatico di Random Forest.

**Risposta corretta:** A

**Spiegazione**

Un valore basso consente più violazioni del margine e può favorire una maggiore generalizzazione, se non eccessivo.

---

## Domanda 108

Che cos'è il kernel trick?

A. Un metodo per modellare separazioni non lineari senza trasformare esplicitamente i dati.

B. Una tecnica per eliminare il validation set.

C. Una metrica di classificazione.

D. Un algoritmo di deployment.

**Risposta corretta:** A

**Spiegazione**

Il kernel trick calcola similarità come se i dati fossero in uno spazio più ricco, senza costruirlo esplicitamente.

---

## Domanda 109

Quale kernel è spesso usato per confini non lineari complessi?

A. RBF.

B. Accuracy.

C. Gini.

D. Laplace.

**Risposta corretta:** A

**Spiegazione**

Il kernel RBF è molto usato per modellare decision boundary non lineari.

---

## Domanda 110

Che cosa controlla `gamma` nel kernel RBF?

A. Quanto è locale l'influenza dei singoli punti.

B. Il numero di classi.

C. La dimensione del test set.

D. Il numero di feature categoriche.

**Risposta corretta:** A

**Spiegazione**

Valori alti di gamma rendono il confine più locale e complesso; valori bassi lo rendono più liscio.

---

## Domanda 111

Che rischio comporta un valore molto alto di `gamma`?

A. Overfitting.

B. Underfitting obbligatorio.

C. Assenza di support vectors.

D. Eliminazione del margine.

**Risposta corretta:** A

**Spiegazione**

Un gamma alto può produrre decision boundary troppo frastagliati e aderenti al training set.

---

## Domanda 112

Che rischio comporta un valore molto basso di `gamma`?

A. Underfitting.

B. Overfitting certo.

C. Nessun training.

D. Conversione in KNN.

**Risposta corretta:** A

**Spiegazione**

Un gamma troppo basso può rendere il confine troppo liscio per catturare la struttura dei dati.

---

## Domanda 113

Quale kernel produce una SVM lineare?

A. Linear.

B. RBF.

C. Polynomial solo di grado 10.

D. Softmax.

**Risposta corretta:** A

**Spiegazione**

Il kernel lineare costruisce un iperpiano nello spazio originale delle feature.

---

## Domanda 114

Quando una SVM è spesso una buona scelta?

A. Dataset piccoli o medi con confini complessi.

B. Dataset enormi con milioni di campioni e inferenza ultra-rapida obbligatoria.

C. Solo problemi non supervisionati.

D. Solo dati testuali senza vectorization.

**Risposta corretta:** A

**Spiegazione**

Le SVM possono essere molto efficaci su dataset non enormi e con buona separazione geometrica.

---

## Domanda 115

Qual è uno svantaggio delle SVM?

A. Richiedono tuning accurato e possono essere costose su dataset grandi.

B. Non supportano classificazione.

C. Non hanno iperparametri.

D. Sono sempre più interpretabili di un Decision Tree.

**Risposta corretta:** A

**Spiegazione**

La scelta di kernel, `C` e `gamma` influenza molto le prestazioni.

---

## Domanda 116

Quale affermazione è corretta?

A. Una SVM può usare kernel per gestire dati non linearmente separabili.

B. Una SVM non può mai usare dati numerici.

C. Una SVM è sempre un algoritmo non supervisionato.

D. Una SVM non usa margini.

**Risposta corretta:** A

**Spiegazione**

I kernel permettono di creare separazioni complesse mantenendo la logica del margine massimo.

---

## Domanda 117

Che cosa fa `SVC(probability=True)` in scikit-learn?

A. Abilita la stima delle probabilità, con costo computazionale aggiuntivo.

B. Disattiva il training.

C. Trasforma SVM in Decision Tree.

D. Imposta automaticamente KNN.

**Risposta corretta:** A

**Spiegazione**

Per default SVC non espone sempre probabilità calibrate; abilitarle richiede calcoli aggiuntivi.

---

## Domanda 118

Quale metrica geometrica è centrale nel ragionamento delle SVM?

A. Margine.

B. F1-Score.

C. RMSE.

D. Prior probability.

**Risposta corretta:** A

**Spiegazione**

La SVM è costruita attorno all'idea di massimizzare la distanza dal confine decisionale ai punti più vicini.

---

## Domanda 119

Quando preferiresti Logistic Regression a SVM?

A. Quando servono semplicità, velocità e interpretabilità.

B. Quando il confine è molto non lineare e il dataset è piccolo.

C. Quando si vuole usare kernel RBF.

D. Quando non si hanno feature.

**Risposta corretta:** A

**Spiegazione**

La Logistic Regression è più semplice e interpretabile, spesso adatta come baseline lineare.

---

## Domanda 120

Quando preferiresti SVM a Logistic Regression?

A. Quando servono confini più complessi e il dataset non è troppo grande.

B. Quando serve la massima interpretabilità dei coefficienti.

C. Quando non vuoi fare scaling.

D. Quando il problema è sempre non supervisionato.

**Risposta corretta:** A

**Spiegazione**

Con kernel adeguati, SVM può modellare separazioni non lineari più ricche rispetto alla Logistic Regression.

---

## Domanda 121

Che cosa rappresenta l'iperpiano in una SVM lineare?

A. Il confine decisionale tra le classi.

B. La matrice di confusione.

C. Il valore della loss in Naive Bayes.

D. Il numero di alberi.

**Risposta corretta:** A

**Spiegazione**

L'iperpiano divide lo spazio delle feature in regioni associate alle diverse classi.

---

## Domanda 122

Quale formula rappresenta concettualmente l'iperpiano lineare?

A. `w · x + b = 0`.

B. `TP / (TP + FN)`.

C. `Gini = 1 - Σpi²`.

D. `K = 5`.

**Risposta corretta:** A

**Spiegazione**

L'equazione `w · x + b = 0` definisce il confine decisionale lineare.

---

## Domanda 123

Quale strumento useresti per scegliere `C`, `gamma` e kernel?

A. Grid Search con Cross Validation.

B. Solo test set finale.

C. Confusion Matrix come algoritmo di training.

D. Bootstrap senza metriche.

**Risposta corretta:** A

**Spiegazione**

Gli iperparametri SVM devono essere scelti usando validazione, non il test set finale.

---

## Domanda 124

Quale affermazione sui support vectors è corretta?

A. Sono i punti più influenti nella definizione del confine.

B. Sono sempre tutti i punti del dataset.

C. Sono metriche di regressione.

D. Sono layer di una rete neurale.

**Risposta corretta:** A

**Spiegazione**

La posizione dell'iperpiano dipende in modo particolare dai punti vicini al margine.

---

## Domanda 125

Quale problema può causare una SVM con kernel complesso e tuning errato?

A. Overfitting.

B. Impossibilità di classificare qualsiasi dato.

C. Eliminazione automatica delle feature.

D. Trasformazione in Naive Bayes.

**Risposta corretta:** A

**Spiegazione**

Kernel complessi e iperparametri aggressivi possono produrre confini troppo aderenti al training set.

---

## K-Nearest Neighbors

## Domanda 126

Che tipo di algoritmo è K-Nearest Neighbors?

A. Un algoritmo supervisionato basato sulla distanza.

B. Un algoritmo probabilistico basato su Bayes.

C. Un algoritmo di ottimizzazione basato sul gradiente.

D. Un sistema di orchestrazione container.

**Risposta corretta:** A

**Spiegazione**

KNN classifica un nuovo campione osservando le classi dei K esempi più vicini nel training set.

---

## Domanda 127

Perché KNN viene definito un algoritmo lazy?

A. Perché non costruisce un vero modello durante il training.

B. Perché usa sempre reti neurali.

C. Perché elimina automaticamente il test set.

D. Perché non usa dati etichettati.

**Risposta corretta:** A

**Spiegazione**

KNN memorizza i dati e rimanda il lavoro principale alla fase di predizione.

---

## Domanda 128

Qual è il parametro principale di KNN?

A. K.

B. C.

C. gamma.

D. learning rate.

**Risposta corretta:** A

**Spiegazione**

K indica il numero di vicini considerati per effettuare la predizione.

---

## Domanda 129

Che cosa accade se K è troppo piccolo?

A. Il modello può diventare molto sensibile al rumore.

B. Il modello diventa sempre lineare.

C. Il modello smette di usare le distanze.

D. La probabilità diventa sempre zero.

**Risposta corretta:** A

**Spiegazione**

Un K piccolo rende la decisione dipendente da pochi campioni, aumentando il rischio di overfitting.

---

## Domanda 130

Che cosa accade se K è troppo grande?

A. Il modello può diventare troppo rigido e andare in underfitting.

B. Il modello diventa automaticamente una SVM.

C. La distanza euclidea non può più essere calcolata.

D. Il dataset viene duplicato.

**Risposta corretta:** A

**Spiegazione**

Un K grande rende le decisioni più stabili ma può appiattire troppo la struttura locale dei dati.

---

## Domanda 131

Perché KNN richiede normalmente feature scaling?

A. Perché si basa sul calcolo delle distanze.

B. Perché usa il Teorema di Bayes.

C. Perché costruisce alberi decisionali.

D. Perché non accetta feature numeriche.

**Risposta corretta:** A

**Spiegazione**

Feature con scale molto diverse dominano il calcolo della distanza e alterano la scelta dei vicini.

---

## Domanda 132

Quale distanza è comunemente usata in KNN?

A. Distanza Euclidea.

B. Entropia.

C. Gini Impurity.

D. Binary Cross Entropy.

**Risposta corretta:** A

**Spiegazione**

La distanza euclidea misura la distanza geometrica tra due punti nello spazio delle feature.

---

## Domanda 133

Quale distanza somma le differenze assolute tra coordinate?

A. Manhattan.

B. RBF.

C. Softmax.

D. ROC.

**Risposta corretta:** A

**Spiegazione**

La distanza Manhattan è la somma delle differenze assolute tra le feature dei due campioni.

---

## Domanda 134

Qual è uno svantaggio importante di KNN?

A. Inferenza lenta su dataset grandi.

B. Training estremamente lungo.

C. Impossibilità di classificare.

D. Assenza di bisogno di memoria.

**Risposta corretta:** A

**Spiegazione**

Per predire un nuovo campione, KNN deve confrontarlo con molti esempi memorizzati.

---

## Domanda 135

Perché KNN soffre la curse of dimensionality?

A. In alta dimensionalità le distanze diventano meno informative.

B. Perché può usare solo una feature.

C. Perché non supporta dati numerici.

D. Perché non usa training set.

**Risposta corretta:** A

**Spiegazione**

Con molte dimensioni, i punti tendono a risultare tutti lontani tra loro e la nozione di vicino perde efficacia.

---

## Domanda 136

Quando KNN può essere una buona scelta?

A. Dataset piccoli e bisogno di una baseline semplice.

B. Dataset enormi con latenza di inferenza molto bassa.

C. Produzione distribuita su Kubernetes.

D. Classificazione di immagini complesse senza preprocessing.

**Risposta corretta:** A

**Spiegazione**

KNN è semplice e utile per prototipi o dataset piccoli, ma scala male su grandi volumi.

---

## Domanda 137

In KNN, come viene scelta la classe in un problema di classificazione?

A. Tramite voto di maggioranza dei K vicini.

B. Tramite minimizzazione della Binary Cross Entropy.

C. Tramite Information Gain.

D. Tramite Model Registry.

**Risposta corretta:** A

**Spiegazione**

La classe prevista è spesso quella più frequente tra i K vicini selezionati.

---

## Domanda 138

KNN può essere usato anche per regressione?

A. Sì, usando ad esempio la media dei valori dei vicini.

B. No, può fare solo classificazione binaria.

C. No, è solo un metodo di deployment.

D. Sì, ma solo con reti neurali.

**Risposta corretta:** A

**Spiegazione**

Nel KNN Regressor la predizione può essere ottenuta mediando il target dei vicini.

---

## Domanda 139

Quale affermazione su KNN è corretta?

A. Ha training quasi nullo ma inferenza potenzialmente costosa.

B. Ha training molto costoso ma inferenza sempre immediata.

C. È sempre più interpretabile di un Decision Tree.

D. Non dipende dalla scala delle feature.

**Risposta corretta:** A

**Spiegazione**

KNN non apprende parametri complessi in training, ma deve cercare i vicini al momento della predizione.

---

## Domanda 140

Quale preprocessing è particolarmente importante prima di usare KNN?

A. Standardizzazione o normalizzazione.

B. Calcolo del Gini.

C. Dockerizzazione.

D. Backpropagation.

**Risposta corretta:** A

**Spiegazione**

Lo scaling evita che alcune feature dominino artificialmente il calcolo delle distanze.

---

## Decision Tree

## Domanda 141

Qual è l'idea principale di un Decision Tree?

A. Suddividere ricorsivamente i dati tramite regole decisionali.

B. Calcolare il margine massimo.

C. Stimare probabilità con Bayes.

D. Aggiornare pesi con backpropagation.

**Risposta corretta:** A

**Spiegazione**

Un albero decisionale crea una sequenza di split che conduce a foglie contenenti predizioni.

---

## Domanda 142

Perché un Decision Tree è considerato interpretabile?

A. Perché le decisioni possono essere seguite come regole dalla radice alla foglia.

B. Perché contiene milioni di parametri nascosti.

C. Perché richiede sempre GPU.

D. Perché non usa feature.

**Risposta corretta:** A

**Spiegazione**

Il percorso nell'albero rende esplicite le condizioni che portano alla predizione.

---

## Domanda 143

Quale criterio misura l'impurità di un nodo?

A. Gini Impurity.

B. Learning Rate.

C. Distanza Manhattan.

D. ROC Curve.

**Risposta corretta:** A

**Spiegazione**

Gini misura quanto le classi siano mescolate all'interno di un nodo.

---

## Domanda 144

Che cosa misura l'entropia in un Decision Tree?

A. Il disordine o l'incertezza di un nodo.

B. La latenza di un'API.

C. La distanza tra due punti.

D. Il numero di epoche.

**Risposta corretta:** A

**Spiegazione**

Entropia alta indica maggiore incertezza nella distribuzione delle classi.

---

## Domanda 145

Che cosa rappresenta l'Information Gain?

A. La riduzione di impurità ottenuta da uno split.

B. Il numero di vicini in KNN.

C. La probabilità prior.

D. Il valore della Precision.

**Risposta corretta:** A

**Spiegazione**

L'Information Gain misura quanto uno split migliora la separazione delle classi.

---

## Domanda 146

Qual è un limite tipico dei Decision Tree?

A. Tendono all'overfitting se non controllati.

B. Richiedono sempre feature scaling.

C. Non gestiscono relazioni non lineari.

D. Non producono regole interpretabili.

**Risposta corretta:** A

**Spiegazione**

Un albero troppo profondo può memorizzare il training set invece di generalizzare.

---

## Domanda 147

Decision Tree richiede normalmente feature scaling?

A. No.

B. Sì, sempre.

C. Solo con kernel RBF.

D. Solo con dati testuali.

**Risposta corretta:** A

**Spiegazione**

Gli split sono basati su soglie delle singole feature, quindi la scala ha impatto limitato.

---

## Domanda 148

Quale iperparametro può limitare la complessità di un Decision Tree?

A. `max_depth`.

B. `gamma`.

C. `C`.

D. `learning_rate` di Gradient Descent.

**Risposta corretta:** A

**Spiegazione**

Limitare la profondità dell'albero riduce il rischio di overfitting.

---

## Domanda 149

Che cosa rappresenta una foglia in un Decision Tree?

A. Un nodo terminale che contiene una predizione.

B. Un valore del learning rate.

C. Un vettore TF-IDF.

D. Un container Docker.

**Risposta corretta:** A

**Spiegazione**

Le foglie sono i punti finali del percorso decisionale e restituiscono la classe o il valore predetto.

---

## Domanda 150

Che cosa rappresenta la radice di un Decision Tree?

A. Il primo nodo da cui iniziano gli split.

B. Il test set finale.

C. La funzione sigmoide.

D. Il margine SVM.

**Risposta corretta:** A

**Spiegazione**

La radice è il nodo iniziale dell'albero e contiene il primo split.

---

## Domanda 151

Un Decision Tree può gestire relazioni non lineari?

A. Sì.

B. No, è sempre lineare.

C. Solo se usa la sigmoide.

D. Solo se usa un kernel RBF.

**Risposta corretta:** A

**Spiegazione**

Gli alberi possono creare confini decisionali non lineari tramite split successivi.

---

## Domanda 152

Quale tecnica può ridurre l'overfitting di un Decision Tree?

A. Pruning.

B. Aumento illimitato della profondità.

C. Eliminazione del validation set.

D. Rimozione delle metriche.

**Risposta corretta:** A

**Spiegazione**

Il pruning elimina o limita parti dell'albero per migliorare la generalizzazione.

---

## Domanda 153

Quando useresti un Decision Tree semplice?

A. Quando serve interpretabilità elevata.

B. Quando serve riconoscere immagini complesse.

C. Quando il dataset è enorme e l'inferenza deve essere basata su distanza.

D. Quando vuoi evitare regole decisionali.

**Risposta corretta:** A

**Spiegazione**

Gli alberi sono adatti quando è importante spiegare le decisioni del modello.

---

## Domanda 154

Quale affermazione è corretta?

A. Un albero troppo profondo può generalizzare male.

B. Un albero troppo profondo è sempre migliore.

C. Gli alberi non possono fare classificazione.

D. Gli alberi richiedono obbligatoriamente scaling.

**Risposta corretta:** A

**Spiegazione**

La profondità eccessiva aumenta la capacità di memorizzare rumore e dettagli specifici del training set.

---

## Domanda 155

Decision Tree può essere usato anche per regressione?

A. Sì.

B. No, solo classificazione binaria.

C. No, solo clustering.

D. Solo se combinato con Naive Bayes.

**Risposta corretta:** A

**Spiegazione**

I Decision Tree possono prevedere classi o valori continui a seconda della variante usata.

---

## Random Forest

## Domanda 156

Che cos'è una Random Forest?

A. Un ensemble di molti Decision Tree.

B. Una singola Logistic Regression.

C. Una funzione di attivazione.

D. Una metrica di regressione.

**Risposta corretta:** A

**Spiegazione**

Random Forest combina le predizioni di molti alberi per migliorare robustezza e generalizzazione.

---

## Domanda 157

Quale tecnica usa Random Forest per creare dataset diversi per gli alberi?

A. Bootstrap sampling.

B. Sigmoide.

C. Kernel trick.

D. Softmax.

**Risposta corretta:** A

**Spiegazione**

Ogni albero viene addestrato su un campione bootstrap estratto dal dataset originale.

---

## Domanda 158

Che cosa significa bagging?

A. Addestrare modelli su campioni diversi e aggregarne le predizioni.

B. Aggiornare pesi con Gradient Descent.

C. Calcolare la probabilità condizionata.

D. Esporre un modello tramite FastAPI.

**Risposta corretta:** A

**Spiegazione**

Bagging riduce la varianza combinando modelli addestrati su campioni differenti.

---

## Domanda 159

Perché Random Forest riduce l'overfitting rispetto a un singolo Decision Tree?

A. Perché aggrega molti alberi diversi riducendo la varianza.

B. Perché usa sempre feature scaling.

C. Perché non usa il training set.

D. Perché non fa split.

**Risposta corretta:** A

**Spiegazione**

La media o il voto di molti alberi rende il modello più stabile rispetto a un singolo albero.

---

## Domanda 160

Random Forest richiede normalmente feature scaling?

A. No.

B. Sì, sempre.

C. Solo con kernel RBF.

D. Solo con Logistic Regression.

**Risposta corretta:** A

**Spiegazione**

Come i Decision Tree, Random Forest usa split basati su soglie e non distanze geometriche.

---

## Domanda 161

Come viene prodotta la predizione finale in classificazione?

A. Voto di maggioranza degli alberi.

B. Somma dei learning rate.

C. Calcolo del logit.

D. Scelta del support vector più vicino.

**Risposta corretta:** A

**Spiegazione**

Ogni albero vota una classe e la classe con più voti viene scelta come predizione finale.

---

## Domanda 162

Come viene prodotta la predizione finale in regressione?

A. Media delle predizioni degli alberi.

B. Voto della classe più frequente.

C. Calcolo della sigmoide.

D. Calcolo della prior.

**Risposta corretta:** A

**Spiegazione**

Nel caso di regressione, Random Forest aggrega le predizioni numeriche tramite media.

---

## Domanda 163

Qual è un vantaggio importante di Random Forest?

A. Buone prestazioni su dataset tabellari con poco tuning.

B. Massima interpretabilità rispetto a un singolo albero.

C. Training sempre nullo.

D. Necessità obbligatoria di GPU.

**Risposta corretta:** A

**Spiegazione**

Random Forest è robusta e spesso performante su dati tabellari anche senza tuning molto complesso.

---

## Domanda 164

Qual è uno svantaggio di Random Forest rispetto a Decision Tree?

A. Minore interpretabilità complessiva.

B. Impossibilità di classificare.

C. Necessità di scaling obbligatorio.

D. Assenza di predizioni.

**Risposta corretta:** A

**Spiegazione**

Un insieme di molti alberi è più difficile da spiegare rispetto a un singolo albero.

---

## Domanda 165

Che cosa indica `n_estimators` in Random Forest?

A. Il numero di alberi nella foresta.

B. Il numero di classi.

C. Il learning rate.

D. Il numero di support vectors.

**Risposta corretta:** A

**Spiegazione**

`n_estimators` controlla quanti alberi vengono addestrati e aggregati.

---

## Domanda 166

Che cosa controlla `max_depth` in Random Forest?

A. La profondità massima degli alberi.

B. Il numero di kernel.

C. La dimensione del batch.

D. La soglia ROC.

**Risposta corretta:** A

**Spiegazione**

Limitare la profondità degli alberi aiuta a controllare la complessità del modello.

---

## Domanda 167

Che cosa rappresenta l'Out-of-Bag score?

A. Una stima delle prestazioni usando campioni non inclusi nel bootstrap di ciascun albero.

B. Il learning rate della foresta.

C. Il numero di foglie.

D. La funzione di attivazione finale.

**Risposta corretta:** A

**Spiegazione**

I campioni non selezionati nel bootstrap possono essere usati per valutare l'albero corrispondente.

---

## Domanda 168

Quando sceglieresti Random Forest?

A. Dataset tabellari, buona accuratezza, robustezza e poco preprocessing.

B. Solo immagini ad altissima complessità.

C. Solo deployment API.

D. Solo dati senza target.

**Risposta corretta:** A

**Spiegazione**

Random Forest è una scelta forte e pratica per molti problemi supervisionati su dati tabellari.

---

## Domanda 169

Perché Random Forest introduce casualità nella scelta delle feature?

A. Per decorrelare gli alberi e aumentare la diversità dell'ensemble.

B. Per eliminare il target.

C. Per forzare una decision boundary lineare.

D. Per sostituire la Cross Validation.

**Risposta corretta:** A

**Spiegazione**

Alberi più diversi tra loro producono un ensemble più robusto.

---

## Domanda 170

Quale affermazione è corretta?

A. Random Forest tende a essere più robusta di un singolo Decision Tree.

B. Random Forest è sempre meno accurata di un singolo albero.

C. Random Forest usa solo un albero.

D. Random Forest richiede sempre Gradient Descent.

**Risposta corretta:** A

**Spiegazione**

L'aggregazione di molti alberi riduce la varianza e migliora la stabilità del modello.

---

## Neural Networks

## Domanda 171

Che cos'è una rete neurale artificiale?

A. Un modello composto da neuroni artificiali organizzati in layer.

B. Un insieme di Decision Tree.

C. Un algoritmo di clustering.

D. Un database distribuito.

**Risposta corretta:** A

**Spiegazione**

Una rete neurale è costituita da neuroni artificiali organizzati in layer che apprendono relazioni anche molto complesse tra input e output.

---

## Domanda 172

Che cos'è un neurone artificiale?

A. Un'unità che combina gli input, applica una funzione di attivazione e produce un output.

B. Un nodo di un database.

C. Un algoritmo di ottimizzazione.

D. Un classificatore Bayesiano.

**Risposta corretta:** A

**Spiegazione**

Ogni neurone riceve input, calcola una combinazione lineare, applica una funzione di attivazione e restituisce un valore in uscita.

---

## Domanda 173

Qual è la formula del neurone artificiale prima dell'attivazione?

A. `z = w · x + b`

B. `TP / (TP + FP)`

C. `Gini = 1 − Σpi²`

D. `RMSE = √MSE`

**Risposta corretta:** A

**Spiegazione**

Il neurone calcola una combinazione lineare tra feature, pesi e bias.

---

## Domanda 174

Che cosa rappresentano i pesi (weights)?

A. L'importanza assegnata ai diversi input.

B. Il numero di layer.

C. La probabilità della classe.

D. Il learning rate.

**Risposta corretta:** A

**Spiegazione**

Durante il training la rete modifica i pesi per migliorare le proprie predizioni.

---

## Domanda 175

Qual è il ruolo del bias?

A. Permette di traslare la funzione del neurone indipendentemente dagli input.

B. Riduce automaticamente l'overfitting.

C. Elimina il bisogno della funzione di attivazione.

D. Determina il numero di neuroni.

**Risposta corretta:** A

**Spiegazione**

Il bias offre maggiore flessibilità permettendo al neurone di adattarsi meglio ai dati.

---

## Domanda 176

Perché viene usata una funzione di attivazione?

A. Per introdurre non linearità nel modello.

B. Per aumentare il numero di feature.

C. Per eliminare il training set.

D. Per sostituire il Gradient Descent.

**Risposta corretta:** A

**Spiegazione**

Senza funzioni di attivazione una rete neurale sarebbe equivalente a una semplice trasformazione lineare.

---

## Domanda 177

Quale funzione di attivazione restituisce valori tra 0 e 1?

A. Sigmoid.

B. ReLU.

C. Softmax.

D. Identity.

**Risposta corretta:** A

**Spiegazione**

La Sigmoid è molto usata nell'output dei problemi di classificazione binaria.

---

## Domanda 178

Qual è la formula della funzione Sigmoid?

A. `σ(x)=1/(1+e^-x)`

B. `max(0,x)`

C. `x²`

D. `log(x)`

**Risposta corretta:** A

**Spiegazione**

La Sigmoid comprime qualsiasi numero reale nell'intervallo compreso tra 0 e 1.

---

## Domanda 179

Quale funzione di attivazione è oggi la più usata nei layer nascosti?

A. ReLU.

B. Sigmoid.

C. Step Function.

D. Identity.

**Risposta corretta:** A

**Spiegazione**

ReLU accelera l'addestramento e riduce il problema del vanishing gradient.

---

## Domanda 180

Qual è la formula della ReLU?

A. `max(0,x)`

B. `1/(1+e^-x)`

C. `x²`

D. `sin(x)`

**Risposta corretta:** A

**Spiegazione**

ReLU restituisce zero per valori negativi e mantiene invariati quelli positivi.

---

## Domanda 181

Quale funzione viene spesso utilizzata nell'output di una classificazione multiclasse?

A. Softmax.

B. ReLU.

C. Tanh.

D. Linear.

**Risposta corretta:** A

**Spiegazione**

Softmax converte i punteggi della rete in probabilità che sommano a 1.

---

## Domanda 182

Che cosa produce la Softmax?

A. Una distribuzione di probabilità sulle classi.

B. Una distanza euclidea.

C. Un learning rate.

D. Un Decision Tree.

**Risposta corretta:** A

**Spiegazione**

Ogni valore rappresenta la probabilità assegnata a una delle classi possibili.

---

## Domanda 183

Che cos'è il Forward Propagation?

A. Il passaggio dei dati dall'input fino all'output della rete.

B. L'aggiornamento dei pesi.

C. La fase di validazione.

D. Il deployment del modello.

**Risposta corretta:** A

**Spiegazione**

Durante il forward propagation la rete calcola la predizione utilizzando i pesi correnti.

---

## Domanda 184

Che cosa rappresenta la Loss Function?

A. La misura dell'errore tra predizioni e valori reali.

B. Il numero di layer.

C. Il learning rate.

D. Il numero di epoche.

**Risposta corretta:** A

**Spiegazione**

La Loss Function guida il processo di apprendimento indicando quanto la rete sta sbagliando.

---

## Domanda 185

Perché si minimizza la Loss Function?

A. Per migliorare progressivamente le predizioni della rete.

B. Per aumentare il numero di neuroni.

C. Per eliminare il dataset.

D. Per evitare il preprocessing.

**Risposta corretta:** A

**Spiegazione**

Riducendo la loss la rete apprende pesi sempre più adatti al problema.

## MLOps

## Domanda 201

Che cos'è MLOps?

A. L'insieme di pratiche che automatizzano sviluppo, deploy e gestione dei modelli di Machine Learning.

B. Un algoritmo di classificazione.

C. Una rete neurale.

D. Una metrica di regressione.

**Risposta corretta:** A

**Spiegazione**

MLOps estende i principi DevOps ai progetti di Machine Learning, automatizzando l'intero ciclo di vita del modello.

---

## Domanda 202

Qual è l'obiettivo principale di MLOps?

A. Rendere riproducibile, automatizzato e monitorabile il ciclo di vita dei modelli.

B. Aumentare sempre il numero di feature.

C. Eliminare il training.

D. Evitare la validazione.

**Risposta corretta:** A

**Spiegazione**

MLOps permette di sviluppare, distribuire e mantenere modelli affidabili nel tempo.

---

## Domanda 203

Quale fase viene normalmente per prima nel ciclo di vita di un progetto ML?

A. Raccolta e preparazione dei dati.

B. Deployment.

C. Monitoring.

D. Retraining.

**Risposta corretta:** A

**Spiegazione**

Il workflow parte dalla raccolta dei dati, che vengono poi preparati per il training.

---

## Domanda 204

Quale sequenza rappresenta correttamente un workflow MLOps?

A. Dati → Training → Validazione → Deploy → Monitoring.

B. Deploy → Training → Dataset.

C. Monitoring → Dataset → Training.

D. Training → Eliminazione dati → Deploy.

**Risposta corretta:** A

**Spiegazione**

Questa rappresenta il ciclo di vita tipico di un modello ML.

---

## Domanda 205

Che cos'è una pipeline di Machine Learning?

A. Una sequenza automatizzata di operazioni che porta dai dati al modello.

B. Una rete neurale.

C. Un database.

D. Una metrica.

**Risposta corretta:** A

**Spiegazione**

Le pipeline automatizzano preprocessing, training, validazione e deployment.

---

## Domanda 206

Perché è importante versionare i dataset?

A. Per poter riprodurre gli esperimenti.

B. Per aumentare la RAM.

C. Per ridurre automaticamente la loss.

D. Per eliminare il validation set.

**Risposta corretta:** A

**Spiegazione**

Sapere con quali dati è stato addestrato un modello è fondamentale per la riproducibilità.

---

## Domanda 207

Perché è importante versionare i modelli?

A. Per poter confrontare e ripristinare versioni precedenti.

B. Per aumentare l'Accuracy.

C. Per eliminare il preprocessing.

D. Per sostituire Git.

**Risposta corretta:** A

**Spiegazione**

La versioning permette di gestire l'evoluzione dei modelli nel tempo.

---

## Domanda 208

Che cos'è un Model Registry?

A. Un archivio centralizzato dei modelli addestrati.

B. Un algoritmo di classificazione.

C. Un database SQL.

D. Una funzione di attivazione.

**Risposta corretta:** A

**Spiegazione**

Il Model Registry conserva modelli, versioni e metadati.

---

## Domanda 209

Che cosa contiene normalmente un Model Registry?

A. Modelli, versioni, metriche e metadati.

B. Solo immagini.

C. Solo codice Python.

D. Solo dataset.

**Risposta corretta:** A

**Spiegazione**

Un Registry conserva tutto ciò che serve per identificare un modello.

---

## Domanda 210

Che cos'è il deployment?

A. La pubblicazione del modello in produzione.

B. Il training del modello.

C. La raccolta dati.

D. La normalizzazione delle feature.

**Risposta corretta:** A

**Spiegazione**

Il deployment rende il modello disponibile agli utenti o ad altre applicazioni.

---

## Domanda 211

Quale tecnologia viene spesso utilizzata per esporre un modello come servizio REST?

A. FastAPI.

B. NumPy.

C. Pandas.

D. Matplotlib.

**Risposta corretta:** A

**Spiegazione**

FastAPI permette di creare rapidamente API REST per servire modelli di Machine Learning.

---

## Domanda 212

Perché Docker è molto usato in MLOps?

A. Per creare ambienti di esecuzione riproducibili.

B. Per addestrare automaticamente i modelli.

C. Per sostituire Git.

D. Per calcolare la Loss Function.

**Risposta corretta:** A

**Spiegazione**

Docker racchiude applicazione, librerie e dipendenze in un'immagine eseguibile ovunque.

---

## Domanda 213

Che cos'è una CI/CD Pipeline?

A. Un processo automatico di build, test e rilascio.

B. Una rete neurale.

C. Una funzione di attivazione.

D. Una metrica di classificazione.

**Risposta corretta:** A

**Spiegazione**

CI/CD automatizza integrazione continua e distribuzione continua del software e dei modelli.

---

## Domanda 214

Che cosa significa Continuous Integration (CI)?

A. Integrare frequentemente il codice eseguendo test automatici.

B. Riaddestrare continuamente il modello.

C. Salvare continuamente il dataset.

D. Eseguire solo il deployment.

**Risposta corretta:** A

**Spiegazione**

La CI verifica automaticamente che le modifiche non introducano errori.

---

## Domanda 215

Che cosa significa Continuous Deployment (CD)?

A. Distribuire automaticamente le nuove versioni dopo i controlli.

B. Addestrare continuamente il modello.

C. Calcolare continuamente la Loss.

D. Versionare i dataset.

**Risposta corretta:** A

**Spiegazione**

Il deployment automatico riduce i tempi di rilascio e limita gli errori manuali.

---

## Domanda 216

Che cos'è il Data Drift?

A. Il cambiamento della distribuzione dei dati nel tempo.

B. L'aumento della Loss durante il training.

C. La modifica del learning rate.

D. Il cambiamento dell'algoritmo.

**Risposta corretta:** A

**Spiegazione**

Se i dati cambiano rispetto a quelli usati in training, il modello può perdere accuratezza.

---

## Domanda 217

Che cos'è il Concept Drift?

A. Il cambiamento della relazione tra feature e target.

B. Il cambiamento del numero di feature.

C. La modifica del test set.

D. Il cambio della funzione Sigmoid.

**Risposta corretta:** A

**Spiegazione**

Nel Concept Drift cambia il fenomeno da modellare, non solo la distribuzione dei dati.

---

## Domanda 218

Perché è importante il monitoring in produzione?

A. Per verificare che il modello continui a funzionare correttamente.

B. Per eliminare il training.

C. Per aumentare automaticamente il numero di feature.

D. Per sostituire il Model Registry.

**Risposta corretta:** A

**Spiegazione**

Il monitoring permette di individuare rapidamente degrado delle prestazioni o anomalie.

---

## Domanda 219

Quali metriche vengono spesso monitorate in produzione?

A. Accuracy, latenza, throughput ed error rate.

B. Solo il learning rate.

C. Solo il numero di feature.

D. Solo la dimensione del dataset.

**Risposta corretta:** A

**Spiegazione**

In produzione è importante monitorare sia metriche ML sia metriche operative.

---

## Domanda 220

Quando è opportuno riaddestrare un modello?

A. Quando il monitoring evidenzia un degrado delle prestazioni.

B. Dopo ogni predizione.

C. Mai.

D. Solo quando cambia il codice Python.

**Risposta corretta:** A

**Spiegazione**

Il retraining mantiene il modello aggiornato rispetto ai nuovi dati.

---

## Domanda 221

Qual è il ruolo del Data Scientist?

A. Analizzare i dati e sviluppare modelli di Machine Learning.

B. Gestire esclusivamente i server.

C. Configurare la rete aziendale.

D. Scrivere solo API REST.

**Risposta corretta:** A

**Spiegazione**

Il Data Scientist si occupa principalmente della parte analitica e modellistica.

---

## Domanda 222

Qual è il ruolo del ML Engineer?

A. Portare i modelli in produzione e renderli affidabili.

B. Creare dashboard di marketing.

C. Gestire database relazionali.

D. Scrivere documentazione legale.

**Risposta corretta:** A

**Spiegazione**

L'ML Engineer si concentra sull'integrazione, automazione e scalabilità dei modelli.

---

## Domanda 223

Qual è il ruolo del Data Engineer?

A. Costruire pipeline e infrastrutture per la gestione dei dati.

B. Addestrare esclusivamente reti neurali.

C. Scegliere la funzione di attivazione.

D. Calcolare la Precision.

**Risposta corretta:** A

**Spiegazione**

Il Data Engineer prepara i dati affinché possano essere utilizzati dai modelli.

---

## Domanda 224

Che cos'è il MLOps Maturity Model?

A. Un modello che descrive il livello di maturità dei processi MLOps di un'organizzazione.

B. Un algoritmo di classificazione.

C. Una funzione di perdita.

D. Una rete neurale.

**Risposta corretta:** A

**Spiegazione**

Il Maturity Model descrive il passaggio da processi manuali a pipeline completamente automatizzate.

---

## Domanda 225

Qual è il principale vantaggio di MLOps?

A. Rendere i modelli riproducibili, scalabili e facilmente manutenibili.

B. Eliminare completamente il bisogno di dati.

C. Sostituire tutti gli algoritmi di Machine Learning.

D. Evitare il deployment.

**Risposta corretta:** A

**Spiegazione**

MLOps consente di gestire in modo professionale l'intero ciclo di vita dei modelli, dalla sperimentazione fino al monitoraggio in produzione.

## Quiz misti

## Quiz misti

## Domanda 226

Quale algoritmo richiede quasi sempre il feature scaling?

A. Decision Tree

B. Random Forest

C. KNN

D. Naive Bayes

**Risposta corretta:** C

**Spiegazione**

KNN utilizza distanze tra i campioni; feature con scale diverse influenzano fortemente il risultato.

---

## Domanda 227

Quale algoritmo è generalmente il più interpretabile?

A. Decision Tree

B. Random Forest

C. Neural Network

D. SVM con kernel RBF

**Risposta corretta:** A

**Spiegazione**

Le decisioni possono essere seguite dalla radice fino alle foglie come regole IF-THEN.

---

## Domanda 228

Quale algoritmo utilizza il Teorema di Bayes?

A. Logistic Regression

B. Naive Bayes

C. KNN

D. Random Forest

**Risposta corretta:** B

**Spiegazione**

Naive Bayes applica direttamente il Teorema di Bayes assumendo indipendenza condizionata tra le feature.

---

## Domanda 229

Quale algoritmo cerca di massimizzare il margine tra le classi?

A. Logistic Regression

B. Decision Tree

C. SVM

D. KNN

**Risposta corretta:** C

**Spiegazione**

L'obiettivo della SVM è trovare l'iperpiano con il margine massimo.

---

## Domanda 230

Quale algoritmo viene definito "lazy learner"?

A. Logistic Regression

B. KNN

C. Naive Bayes

D. Decision Tree

**Risposta corretta:** B

**Spiegazione**

KNN non costruisce un modello durante il training ma rinvia il lavoro alla fase di inferenza.

---

## Domanda 231

Quale algoritmo utilizza il voto di maggioranza di più modelli?

A. Logistic Regression

B. Random Forest

C. SVM

D. Naive Bayes

**Risposta corretta:** B

**Spiegazione**

Random Forest aggrega le predizioni di molti alberi decisionali.

---

## Domanda 232

Quale algoritmo produce direttamente probabilità comprese tra 0 e 1 mediante la funzione Sigmoid?

A. Logistic Regression

B. Decision Tree

C. KNN

D. SVM

**Risposta corretta:** A

**Spiegazione**

La Logistic Regression applica la Sigmoid alla combinazione lineare delle feature.

---

## Domanda 233

Quale algoritmo è più indicato come baseline per classificazione testuale?

A. Naive Bayes

B. Random Forest

C. KNN

D. Decision Tree

**Risposta corretta:** A

**Spiegazione**

Naive Bayes è veloce ed efficace su documenti e testo.

---

## Domanda 234

Quale algoritmo è generalmente più robusto di un singolo Decision Tree?

A. Random Forest

B. Logistic Regression

C. KNN

D. SVM lineare

**Risposta corretta:** A

**Spiegazione**

L'ensemble riduce la varianza e migliora la generalizzazione.

---

## Domanda 235

Quale algoritmo utilizza il parametro K?

A. KNN

B. Logistic Regression

C. SVM

D. Naive Bayes

**Risposta corretta:** A

**Spiegazione**

K rappresenta il numero di vicini considerati.

---

## Domanda 236

Quale algoritmo utilizza normalmente il parametro C?

A. Logistic Regression e SVM

B. KNN

C. Decision Tree

D. Naive Bayes

**Risposta corretta:** A

**Spiegazione**

In entrambi controlla la forza della regolarizzazione (o il compromesso con gli errori).

---

## Domanda 237

Quale algoritmo utilizza Bootstrap Sampling?

A. Random Forest

B. Logistic Regression

C. SVM

D. KNN

**Risposta corretta:** A

**Spiegazione**

Ogni albero viene addestrato su un campione bootstrap.

---

## Domanda 238

Quale algoritmo può soffrire maggiormente la Curse of Dimensionality?

A. KNN

B. Decision Tree

C. Random Forest

D. Naive Bayes

**Risposta corretta:** A

**Spiegazione**

Con molte dimensioni le distanze diventano meno informative.

---

## Domanda 239

Quale algoritmo viene addestrato tramite Backpropagation?

A. Neural Network

B. Decision Tree

C. KNN

D. Naive Bayes

**Risposta corretta:** A

**Spiegazione**

Le reti neurali aggiornano i pesi propagando l'errore all'indietro.

---

## Domanda 240

Quale algoritmo richiede tipicamente più dati per ottenere ottime prestazioni?

A. Neural Network

B. Naive Bayes

C. Decision Tree

D. Logistic Regression

**Risposta corretta:** A

**Spiegazione**

Le reti neurali esprimono il loro potenziale soprattutto con dataset grandi.

---

## Domanda 241

Quale tecnica riduce l'overfitting nelle reti neurali?

A. Dropout

B. Bootstrap

C. One-Hot Encoding

D. TF-IDF

**Risposta corretta:** A

---

## Domanda 242

Quale componente conserva le versioni dei modelli in MLOps?

A. Model Registry

B. Docker

C. FastAPI

D. NumPy

**Risposta corretta:** A

---

## Domanda 243

Quale fenomeno indica che la distribuzione dei dati cambia nel tempo?

A. Data Drift

B. Gradient Descent

C. Bagging

D. Dropout

**Risposta corretta:** A

---

## Domanda 244

Quale fenomeno indica che cambia la relazione tra input e target?

A. Concept Drift

B. Feature Scaling

C. Cross Validation

D. ROC Curve

**Risposta corretta:** A

---

## Domanda 245

Quale fase segue normalmente il deployment in MLOps?

A. Monitoring

B. Preprocessing

C. Training

D. Feature Engineering

**Risposta corretta:** A

---

## Domanda 246

Quale algoritmo è generalmente più semplice da spiegare a un cliente?

A. Decision Tree

B. Neural Network

C. Random Forest

D. SVM con kernel RBF

**Risposta corretta:** A

---

## Domanda 247

Quale algoritmo è più adatto quando serve un modello probabilistico facilmente interpretabile?

A. Logistic Regression

B. Random Forest

C. KNN

D. SVM

**Risposta corretta:** A

---

## Domanda 248

Quale algoritmo è spesso una scelta eccellente per dataset tabellari?

A. Random Forest

B. Naive Bayes

C. KNN

D. Sigmoid

**Risposta corretta:** A

---

## Domanda 249

Quale tecnica viene usata per valutare un modello usando più suddivisioni del dataset?

A. Cross Validation

B. Dropout

C. Bootstrap Sampling

D. Backpropagation

**Risposta corretta:** A

---

## Domanda 250

Qual è il principale obiettivo del Machine Learning?

A. Generalizzare su dati mai visti.

B. Memorizzare perfettamente il training set.

C. Eliminare il preprocessing.

D. Massimizzare sempre il numero di feature.

**Risposta corretta:** A

**Spiegazione**

Un buon modello deve apprendere dai dati di training mantenendo prestazioni elevate anche su esempi nuovi.
---

---

## Domanda 251

Hai un dataset di 500 righe, tutte feature numeriche, e il cliente vuole capire come il modello prende le decisioni. Quale algoritmo sceglieresti?

A. Decision Tree.

B. Rete Neurale Profonda.

C. CNN.

D. Transformer.

**Risposta corretta:** A

**Spiegazione**

Un Decision Tree offre un'elevata interpretabilità ed è facilmente spiegabile anche a utenti non tecnici.

---

## Domanda 252

Hai un dataset tabellare di medie dimensioni e vuoi ottenere rapidamente buone prestazioni senza molto tuning. Quale algoritmo sceglieresti?

A. Random Forest.

B. KNN con K=1.

C. Naive Bayes.

D. PCA.

**Risposta corretta:** A

**Spiegazione**

Random Forest rappresenta spesso una delle migliori baseline per dati tabellari.

---

## Domanda 253

Stai sviluppando un filtro antispam basato sul testo delle email. Quale algoritmo proveresti per primo?

A. Naive Bayes.

B. K-Means.

C. Random Forest.

D. Decision Tree.

**Risposta corretta:** A

**Spiegazione**

Naive Bayes è estremamente efficace nella classificazione di documenti e spam.

---

## Domanda 254

Le feature hanno scale molto diverse. Quale algoritmo soffrirà maggiormente se non esegui lo scaling?

A. KNN.

B. Decision Tree.

C. Random Forest.

D. Naive Bayes.

**Risposta corretta:** A

**Spiegazione**

KNN utilizza direttamente le distanze e quindi è molto sensibile alla scala delle feature.

---

## Domanda 255

Il cliente richiede probabilità facilmente interpretabili per ogni predizione. Quale algoritmo è il più indicato?

A. Logistic Regression.

B. KNN.

C. Decision Tree.

D. SVM con kernel RBF.

**Risposta corretta:** A

**Spiegazione**

La Logistic Regression produce probabilità direttamente interpretabili.

---

## Domanda 256

Hai un dataset molto piccolo ma con un confine decisionale non lineare. Quale algoritmo potrebbe funzionare meglio?

A. SVM con kernel RBF.

B. Linear Regression.

C. Decision Stump.

D. PCA.

**Risposta corretta:** A

**Spiegazione**

Le SVM sono molto efficaci su dataset piccoli e confini complessi.

---

## Domanda 257

Il modello ottiene Accuracy del 99% ma ignora completamente la classe minoritaria. Quale metrica controlleresti?

A. Recall.

B. RMSE.

C. MSE.

D. R².

**Risposta corretta:** A

**Spiegazione**

Nei dataset sbilanciati Accuracy può essere fuorviante.

---

## Domanda 258

Durante il training la loss diminuisce, mentre quella di validazione aumenta. Cosa sta succedendo?

A. Overfitting.

B. Underfitting.

C. Data Leakage.

D. Feature Scaling.

**Risposta corretta:** A

**Spiegazione**

Il modello sta memorizzando il training set senza generalizzare.

---

## Domanda 259

In produzione l'Accuracy diminuisce perché i dati sono cambiati rispetto al training. Come si chiama questo fenomeno?

A. Data Drift.

B. Gradient Descent.

C. Dropout.

D. Bagging.

**Risposta corretta:** A

**Spiegazione**

La distribuzione dei dati è cambiata nel tempo.

---

## Domanda 260

Qual è il primo passo corretto di un progetto di Machine Learning?

A. Comprendere il problema e analizzare i dati.

B. Fare subito il deployment.

C. Costruire una rete neurale.

D. Pubblicare l'API.

**Risposta corretta:** A

**Spiegazione**

Ogni progetto ML parte dalla comprensione del dominio e dei dati.

---

## Domanda 261

Hai un dataset con milioni di immagini. Quale famiglia di modelli è generalmente più adatta?

A. Neural Networks.

B. Naive Bayes.

C. Decision Tree.

D. Logistic Regression.

**Risposta corretta:** A

---

## Domanda 262

Vuoi evitare l'overfitting in una rete neurale. Quale tecnica useresti?

A. Dropout.

B. TF-IDF.

C. Bagging.

D. One-Hot Encoding.

**Risposta corretta:** A

---

## Domanda 263

Il cliente vuole sapere quale feature influenza maggiormente la previsione. Quale algoritmo facilita questa spiegazione?

A. Decision Tree.

B. Neural Network.

C. SVM RBF.

D. KNN.

**Risposta corretta:** A

---

## Domanda 264

Un modello viene esposto tramite endpoint `/predict`. In quale fase del ciclo ML ti trovi?

A. Deployment.

B. Training.

C. Validation.

D. Feature Engineering.

**Risposta corretta:** A

---

## Domanda 265

Dopo il deployment osservi errori e prestazioni. Come si chiama questa attività?

A. Monitoring.

B. Bagging.

C. Scaling.

D. Encoding.

**Risposta corretta:** A

---

## Domanda 266

Quale tecnica permette di valutare il modello usando più suddivisioni del dataset?

A. Cross Validation.

B. Backpropagation.

C. Softmax.

D. Bootstrap Aggregation.

**Risposta corretta:** A

---

## Domanda 267

Vuoi ridurre il numero di falsi positivi. Quale metrica monitori?

A. Precision.

B. Recall.

C. RMSE.

D. Accuracy soltanto.

**Risposta corretta:** A

---

## Domanda 268

Vuoi ridurre il numero di falsi negativi. Quale metrica monitori?

A. Recall.

B. Precision.

C. MAE.

D. R².

**Risposta corretta:** A

---

## Domanda 269

Hai bisogno di una baseline semplice e veloce per classificazione binaria. Quale algoritmo scegli?

A. Logistic Regression.

B. CNN.

C. Transformer.

D. GAN.

**Risposta corretta:** A

---

## Domanda 270

Quale algoritmo è più sensibile alla Curse of Dimensionality?

A. KNN.

B. Random Forest.

C. Decision Tree.

D. Naive Bayes.

**Risposta corretta:** A

---

## Domanda 271

Quale algoritmo utilizza il voto della maggioranza?

A. Random Forest.

B. Logistic Regression.

C. Naive Bayes.

D. Gradient Descent.

**Risposta corretta:** A

---

## Domanda 272

Quale algoritmo apprende aggiornando iterativamente pesi e bias?

A. Neural Network.

B. Decision Tree.

C. KNN.

D. Naive Bayes.

**Risposta corretta:** A

---

## Domanda 273

Quale componente MLOps conserva le diverse versioni dei modelli?

A. Model Registry.

B. FastAPI.

C. Docker.

D. Pandas.

**Risposta corretta:** A

---

## Domanda 274

Per rendere un progetto ML riproducibile è importante versionare...

A. Codice, dati e modelli.

B. Solo il codice.

C. Solo il dataset.

D. Solo il modello.

**Risposta corretta:** A

---

## Domanda 275

Qual è l'obiettivo finale di un progetto di Machine Learning?

A. Generalizzare correttamente su dati mai osservati.

B. Ottenere Accuracy del 100% sul training set.

C. Eliminare il validation set.

D. Costruire il modello più complesso possibile.

**Risposta corretta:** A

**Spiegazione**

L'obiettivo è ottenere un modello che funzioni bene anche su dati nuovi, non memorizzare quelli di addestramento.

---

## Domanda 276

Quale tra questi è un esempio di Data Leakage?

A. Utilizzare il Test Set per scegliere gli iperparametri.

B. Applicare StandardScaler solo sul Training Set.

C. Utilizzare Cross Validation.

D. Aumentare il numero di epoche.

**Risposta corretta:** A

**Spiegazione**

Il Test Set deve rimanere completamente indipendente fino alla valutazione finale.

---

## Domanda 277

Un modello ha Accuracy del 99% su un dataset con il 99% di esempi negativi. Quale metrica controlleresti?

A. Precision e Recall.

B. Learning Rate.

C. Numero di feature.

D. Batch Size.

**Risposta corretta:** A

**Spiegazione**

Su dataset sbilanciati Accuracy può essere fuorviante.

---

## Domanda 278

Quale algoritmo è generalmente il meno interpretabile?

A. Decision Tree

B. Logistic Regression

C. Neural Network profonda

D. Naive Bayes

**Risposta corretta:** C

**Spiegazione**

Le reti neurali profonde sono considerate modelli "black box".

---

## Domanda 279

Qual è il principale vantaggio delle Pipeline di scikit-learn?

A. Evitare inconsistenze tra training e inferenza.

B. Eliminare il bisogno di dati.

C. Rendere inutile il preprocessing.

D. Evitare il deployment.

**Risposta corretta:** A

**Spiegazione**

Le Pipeline garantiscono che le stesse trasformazioni vengano applicate sia in training sia in produzione.

---

## Domanda 280

Quale componente conserva le feature già trasformate e riutilizzabili?

A. Feature Store

B. Model Registry

C. Git

D. Docker

**Risposta corretta:** A

**Spiegazione**

Il Feature Store centralizza e riutilizza le feature.

---

## Domanda 281

Quale componente conserva le versioni dei modelli?

A. Model Registry

B. Feature Store

C. FastAPI

D. Kubernetes

**Risposta corretta:** A

**Spiegazione**

Il Model Registry gestisce modelli, versioni e metadati.

---

## Domanda 282

Che cosa monitora principalmente il Monitoring in MLOps?

A. Prestazioni del modello e del servizio.

B. Solo il numero di feature.

C. Solo il codice Python.

D. Solo il dataset originale.

**Risposta corretta:** A

---

## Domanda 283

Che cosa indica il Prediction Drift?

A. Cambia la distribuzione delle predizioni del modello.

B. Cambia il numero di feature.

C. Cambia il learning rate.

D. Cambia il numero di neuroni.

**Risposta corretta:** A

---

## Domanda 284

Quale deployment invia una piccola percentuale di traffico alla nuova versione?

A. Canary Deployment

B. Blue-Green

C. Rolling Back

D. Batch Serving

**Risposta corretta:** A

---

## Domanda 285

Quale deployment mantiene contemporaneamente due ambienti completi?

A. Blue-Green Deployment

B. Canary

C. Shadow

D. Batch

**Risposta corretta:** A

---

## Domanda 286

Quale deployment esegue il nuovo modello senza influenzare gli utenti?

A. Shadow Deployment

B. Rolling Update

C. Canary

D. Blue-Green

**Risposta corretta:** A

---

## Domanda 287

Quale tecnologia permette di creare container?

A. Docker

B. Pandas

C. NumPy

D. Matplotlib

**Risposta corretta:** A

---

## Domanda 288

Quale tecnologia orchestra molti container?

A. Kubernetes

B. FastAPI

C. Git

D. Scikit-learn

**Risposta corretta:** A

---

## Domanda 289

Qual è lo scopo di una Model Card?

A. Documentare caratteristiche e limiti del modello.

B. Addestrare il modello.

C. Versionare il dataset.

D. Monitorare la GPU.

**Risposta corretta:** A

---

## Domanda 290

Che cosa descrive Explainable AI?

A. Tecniche per interpretare le decisioni dei modelli.

B. Tecniche di deployment.

C. Tecniche di compressione.

D. Tecniche di clustering.

**Risposta corretta:** A

---

## Domanda 291

Quale pratica migliora maggiormente la riproducibilità?

A. Versionare codice, dati e modelli.

B. Aumentare il learning rate.

C. Eliminare il validation set.

D. Usare sempre Random Forest.

**Risposta corretta:** A

---

## Domanda 292

Che cosa rappresenta CI?

A. Continuous Integration.

B. Continuous Inference.

C. Continuous Input.

D. Continuous Inspection.

**Risposta corretta:** A

---

## Domanda 293

Che cosa rappresenta CD?

A. Continuous Deployment.

B. Continuous Data.

C. Continuous Drift.

D. Continuous Docker.

**Risposta corretta:** A

---

## Domanda 294

Che cosa rappresenta CT in MLOps?

A. Continuous Training.

B. Continuous Testing.

C. Continuous Tracking.

D. Continuous Target.

**Risposta corretta:** A

---

## Domanda 295

Qual è il principale obiettivo di una API REST che serve un modello?

A. Rendere disponibile l'inferenza ad altri sistemi.

B. Addestrare automaticamente il modello.

C. Versionare il dataset.

D. Calcolare Accuracy.

**Risposta corretta:** A

---

## Domanda 296

Qual è la differenza principale tra Training e Inference?

A. Nel Training il modello apprende; nell'Inference produce predizioni.

B. Sono sinonimi.

C. L'Inference modifica sempre i pesi.

D. Il Training non usa dati.

**Risposta corretta:** A

---

## Domanda 297

Quale tra questi NON è un algoritmo di Machine Learning?

A. FastAPI

B. Random Forest

C. Logistic Regression

D. SVM

**Risposta corretta:** A

---

## Domanda 298

Qual è il primo obiettivo di un buon sistema MLOps?

A. Rendere il ciclo di vita del modello affidabile e automatizzato.

B. Eliminare il preprocessing.

C. Eliminare il monitoring.

D. Eliminare il deployment.

**Risposta corretta:** A

---

## Domanda 299

Quale affermazione è corretta?

A. Nessun algoritmo è il migliore in assoluto.

B. Random Forest è sempre migliore di qualsiasi altro algoritmo.

C. Le Neural Network sono sempre superiori.

D. Logistic Regression è sempre obsoleta.

**Risposta corretta:** A

**Spiegazione**

La scelta del modello dipende dal problema, dai dati, dalle risorse disponibili e dagli obiettivi del progetto.

---

## Domanda 300

Qual è la competenza più importante acquisita durante un percorso di AI Engineering?

A. Saper scegliere, addestrare, valutare, distribuire e monitorare correttamente un modello di Machine Learning.

B. Conoscere a memoria tutte le formule matematiche.

C. Utilizzare esclusivamente reti neurali.

D. Scrivere codice Python senza usare librerie.

**Risposta corretta:** A

**Spiegazione**

L'AI Engineer deve padroneggiare l'intero ciclo di vita del Machine Learning: dalla comprensione del problema fino al monitoraggio del modello in produzione.