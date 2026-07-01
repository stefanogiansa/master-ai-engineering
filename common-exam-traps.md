# Common Exam Traps

> Raccolta delle confusioni e degli errori concettuali più frequenti negli esami di Machine Learning e AI Engineering.

---

## Scopo del documento

Durante un esame di Machine Learning, gli errori più frequenti non derivano dalla mancata conoscenza degli algoritmi, ma dalla confusione tra concetti molto simili.

Ad esempio:

- Precision vs Recall
- Overfitting vs Underfitting
- Bias vs Variance
- Data Drift vs Concept Drift

Lo scopo di questo documento è aiutare a riconoscere rapidamente queste differenze.

Ogni sezione contiene:

- definizione;
- differenze;
- quando usare ciascun concetto;
- errore tipico;
- possibile domanda d'esame.

---

## Come utilizzare questo documento

Durante il ripasso:

1. prova a rispondere mentalmente alla domanda;
2. confronta la tua risposta con la spiegazione;
3. verifica di saper motivare la differenza.

Se non riesci a spiegare il "perché", probabilmente il concetto non è ancora consolidato.

---

## Accuracy vs Precision vs Recall vs F1-Score

## Accuracy

Misura la percentuale di predizioni corrette.

**Formula**

`Accuracy = (TP + TN) / (TP + TN + FP + FN)`

### Quando usarla

È utile quando il dataset è bilanciato.

### Limite

Può essere fuorviante con classi sbilanciate.

---

## Precision

Risponde alla domanda:

> Tra tutti i positivi predetti, quanti erano davvero positivi?

**Formula**

`Precision = TP / (TP + FP)`

È importante quando i falsi positivi sono costosi.

Esempi:

- spam detection;
- diagnosi medica positiva;
- rilevazione frodi.

---

## Recall

Risponde alla domanda:

> Tra tutti i positivi reali, quanti sono stati trovati?

**Formula**

`Recall = TP / (TP + FN)`

È importante quando i falsi negativi sono molto pericolosi.

Esempi:

- diagnosi di tumori;
- rilevazione frodi;
- sistemi di sicurezza.

---

## F1-Score

È la media armonica tra Precision e Recall.

**Formula**

`F1 = 2 × (Precision × Recall) / (Precision + Recall)`

È molto utile nei dataset sbilanciati.

---

## Differenze principali

| Metrica | Domanda a cui risponde |
|----------|------------------------|
| Accuracy | Quante predizioni sono corrette? |
| Precision | Quanti positivi predetti erano davvero positivi? |
| Recall | Quanti positivi reali sono stati trovati? |
| F1-Score | Qual è il miglior compromesso tra Precision e Recall? |

---

## Errore tipico

Pensare che **Accuracy** sia sempre la metrica migliore.

Non è vero.

Con dataset sbilanciati è spesso la metrica meno significativa.

---

## Domanda tipica d'esame

**Domanda**

> In un sistema di diagnosi medica quale metrica privilegeresti?

**Risposta**

Recall.

**Motivazione**

Perdere un paziente realmente malato (falso negativo) è generalmente molto più grave che classificare come malato un paziente sano (falso positivo).

---

## Overfitting vs Underfitting

## Overfitting

Il modello apprende troppo bene il training set.

### Sintomi

- Training Accuracy molto alta.
- Validation Accuracy bassa.
- Ottime prestazioni sul training.
- Scarsa capacità di generalizzazione.

Il modello memorizza i dati invece di imparare il fenomeno.

---

## Underfitting

Il modello è troppo semplice.

### Sintomi

- Training Accuracy bassa.
- Validation Accuracy bassa.
- Prestazioni insufficienti anche sul training set.

Il modello non riesce a catturare la relazione tra feature e target.

---

## Confronto

| Overfitting | Underfitting |
|--------------|--------------|
| Modello troppo complesso | Modello troppo semplice |
| Alta varianza | Alto bias |
| Training ottimo | Training scarso |
| Validation scarsa | Validation scarsa |
| Generalizzazione pessima | Generalizzazione insufficiente |

---

## Come ridurre l'Overfitting

- raccogliere più dati;
- usare Dropout;
- applicare Early Stopping;
- utilizzare regolarizzazione (L1/L2);
- eseguire Cross Validation;
- ridurre la complessità del modello.

---

## Come ridurre l'Underfitting

- aumentare la complessità del modello;
- aggiungere feature informative;
- aumentare il numero di epoche (nelle reti neurali);
- effettuare tuning degli iperparametri.

---

## Domanda tipica d'esame

**Domanda**

> Training Accuracy = 99%
>
> Validation Accuracy = 71%
>
> Che problema presenta il modello?

**Risposta**

Overfitting.

**Motivazione**

Il modello ha imparato molto bene il training set ma non riesce a generalizzare sui dati non visti.

---

## Bias vs Variance

## Bias

Il **Bias** rappresenta l'errore dovuto a ipotesi troppo semplici fatte dal modello.

Un modello con alto Bias tende a non catturare correttamente la relazione tra feature e target.

### Sintomi

- Training Accuracy bassa.
- Validation Accuracy bassa.
- Modello troppo semplice.

Il Bias elevato porta spesso a **Underfitting**.

---

## Variance

La **Variance** rappresenta la sensibilità del modello alle variazioni del training set.

Un modello con alta Variance apprende molto bene i dati di training ma generalizza male.

### Sintomi

- Training Accuracy molto alta.
- Validation Accuracy molto più bassa.
- Modello molto complesso.

La Variance elevata porta spesso a **Overfitting**.

---

## Confronto

| Bias | Variance |
|------|----------|
| Modello troppo semplice | Modello troppo complesso |
| Underfitting | Overfitting |
| Bassa Accuracy sul training | Accuracy molto alta sul training |
| Generalizzazione insufficiente | Generalizzazione scarsa |

---

## Errore tipico

Confondere Bias e Variance con Accuracy.

Bias e Variance descrivono il comportamento del modello, non rappresentano metriche di valutazione.

---

## Domanda tipica d'esame

**Domanda**

> Quale fenomeno è normalmente associato all'Overfitting?

**Risposta**

Alta Variance.

---

## Training Set vs Validation Set vs Test Set

## Training Set

È il dataset utilizzato per addestrare il modello.

Durante questa fase il modello apprende i parametri.

---

## Validation Set

Serve per:

- confrontare modelli;
- effettuare tuning degli iperparametri;
- individuare Overfitting;
- scegliere il modello migliore.

Il modello **non viene addestrato** sul Validation Set.

---

## Test Set

Serve esclusivamente per la valutazione finale.

Il Test Set deve rimanere completamente separato dal training.

Non deve influenzare la scelta del modello.

---

## Confronto

| Dataset | Scopo |
|----------|-------|
| Training | Apprendimento dei parametri |
| Validation | Scelta del modello e tuning |
| Test | Valutazione finale |

---

## Errore tipico

Usare il Test Set per scegliere gli iperparametri.

In questo modo il Test Set smette di rappresentare dati realmente "mai visti".

---

## Domanda tipica d'esame

**Domanda**

> Su quale dataset si esegue normalmente il tuning degli iperparametri?

**Risposta**

Validation Set.

---

## Parameter vs Hyperparameter

## Parameter

I **parametri** vengono appresi automaticamente durante il training.

Esempi:

- pesi della Logistic Regression;
- pesi delle Neural Networks;
- coefficienti del modello.

---

## Hyperparameter

Gli **iperparametri** vengono scelti dal Data Scientist prima dell'addestramento.

Esempi:

- K in KNN;
- max_depth in Decision Tree;
- numero di alberi in Random Forest;
- learning rate nelle Neural Networks;
- C nella SVM.

---

## Confronto

| Parameter | Hyperparameter |
|-----------|----------------|
| Appreso dal modello | Scelto dall'utente |
| Cambia durante il training | Rimane fisso durante il training |
| Ottimizzato automaticamente | Ottimizzato tramite tuning |

---

## Errore tipico

Pensare che il Learning Rate venga appreso automaticamente.

In realtà è un iperparametro.

---

## Domanda tipica d'esame

**Domanda**

> Il numero di vicini in KNN è un parametro o un iperparametro?

**Risposta**

È un iperparametro.

---

## Standardization vs Normalization

Questi due termini vengono spesso confusi.

Entrambi servono a modificare la scala delle feature, ma in modo diverso.

---

## Standardization

Trasforma le feature affinché abbiano:

- media uguale a 0;
- deviazione standard uguale a 1.

Formula

`z = (x - μ) / σ`

È la tecnica più utilizzata con:

- Logistic Regression;
- SVM;
- Neural Networks.

---

## Normalization (Min-Max Scaling)

Trasforma i dati nell'intervallo:

`[0, 1]`

Formula

`x' = (x - min) / (max - min)`

È utile quando serve mantenere un intervallo fisso.

---

## Confronto

| Standardization | Normalization |
|-----------------|---------------|
| Media = 0 | Min = 0 |
| Deviazione standard = 1 | Max = 1 |
| Valori non limitati | Valori compresi tra 0 e 1 |
| StandardScaler | MinMaxScaler |

---

## Errore tipico

Pensare che siano sinonimi.

Non lo sono.

Sono due trasformazioni differenti.

---

## Domanda tipica d'esame

**Domanda**

> Quale tecnica produce feature con media pari a zero?

**Risposta**

Standardization.

---

## Feature Scaling vs Feature Engineering

Questi due concetti vengono spesso confusi.

## Feature Scaling

Consiste nel modificare la scala delle feature esistenti.

Non cambia il significato delle variabili.

Esempi:

- StandardScaler;
- MinMaxScaler.

---

## Feature Engineering

Consiste nel creare nuove feature oppure modificare quelle esistenti per aumentare le informazioni disponibili.

Esempi:

- età → fascia di età;
- data → giorno della settimana;
- reddito e spese → rapporto spese/reddito.

---

## Confronto

| Feature Scaling | Feature Engineering |
|-----------------|---------------------|
| Cambia la scala | Crea nuove informazioni |
| Non aggiunge feature | Può creare nuove feature |
| Preprocessing numerico | Trasformazione del dataset |

---

## Errore tipico

Pensare che StandardScaler sia una tecnica di Feature Engineering.

Non lo è.

È esclusivamente una tecnica di preprocessing.

---

## Domanda tipica d'esame

**Domanda**

> Creare una nuova feature "età media familiare" è Feature Scaling o Feature Engineering?

**Risposta**

Feature Engineering.

---

## Data Leakage vs Overfitting

Questi due concetti vengono spesso confusi perché entrambi possono produrre prestazioni apparentemente eccellenti durante il training.

In realtà rappresentano problemi completamente diversi.

---

## Data Leakage

Il **Data Leakage** si verifica quando il modello riceve informazioni che, nella realtà, non dovrebbe conoscere durante l'addestramento.

In altre parole, il modello "bara" utilizzando dati che appartengono al futuro o al Test Set.

### Esempi

- utilizzare il Test Set durante il training;
- calcolare statistiche (media, deviazione standard) sull'intero dataset prima dello split;
- usare feature disponibili solo dopo l'evento che si vuole prevedere.

---

## Overfitting

L'**Overfitting** si verifica quando il modello apprende troppo bene il Training Set.

Il problema non è la presenza di informazioni aggiuntive, ma il fatto che il modello memorizza il rumore anziché apprendere il fenomeno.

---

## Confronto

| Data Leakage | Overfitting |
|---------------|-------------|
| Informazioni non dovrebbero essere disponibili | Modello troppo complesso |
| Errore metodologico | Errore di generalizzazione |
| Prestazioni artificialmente elevate | Prestazioni elevate solo sul training |
| Si evita con una corretta separazione dei dati | Si riduce con regolarizzazione e tuning |

---

## Errore tipico

Pensare che Accuracy del 100% significhi automaticamente Overfitting.

Potrebbe invece essere presente Data Leakage.

---

## Domanda tipica d'esame

**Domanda**

> Il modello ottiene Accuracy del 100% anche sul Validation Set perché il Test Set è stato utilizzato durante il preprocessing.

**Risposta**

Data Leakage.

---

## Data Drift vs Concept Drift

Entrambi descrivono cambiamenti nel tempo, ma riguardano aspetti differenti.

---

## Data Drift

Nel **Data Drift** cambia la distribuzione delle feature di input.

Il fenomeno da prevedere rimane lo stesso.

### Esempio

Un modello bancario addestrato prima di una crisi economica riceve improvvisamente richieste di prestito con caratteristiche molto diverse.

---

## Concept Drift

Nel **Concept Drift** cambia la relazione tra feature e target.

Il significato stesso del fenomeno evolve nel tempo.

### Esempio

Le strategie usate dai truffatori cambiano continuamente.

Le stesse feature non descrivono più correttamente le frodi.

---

## Confronto

| Data Drift | Concept Drift |
|-------------|---------------|
| Cambiano gli input | Cambia la relazione input-target |
| Le feature hanno distribuzione diversa | Cambia il fenomeno da apprendere |
| Il modello può richiedere retraining | Il modello deve essere aggiornato |

---

## Errore tipico

Pensare che siano sinonimi.

Non lo sono.

---

## Domanda tipica

**Domanda**

> Le vendite online cambiano perché i clienti hanno modificato le proprie abitudini.

Di quale fenomeno si tratta?

**Risposta**

Data Drift (se cambia la distribuzione degli input) oppure Concept Drift (se cambia il comportamento che collega input e target).

Nell'esame è fondamentale leggere con attenzione la descrizione.

---

## Gini vs Entropy

Entrambe sono misure utilizzate dai Decision Tree per scegliere lo split migliore.

---

## Gini Impurity

Misura quanto un nodo contiene campioni appartenenti a classi differenti.

Valori bassi indicano nodi più puri.

Formula

`Gini = 1 - Σ p²`

---

## Entropy

Misura il grado di disordine del nodo.

Formula

`Entropy = - Σ p log₂(p)`

Più l'entropia è alta, maggiore è il disordine.

---

## Confronto

| Gini | Entropy |
|------|----------|
| Più veloce da calcolare | Più costosa |
| Default in Scikit-learn | Basata sulla teoria dell'informazione |
| Produce risultati simili | Produce risultati simili |

---

## Errore tipico

Pensare che uno dei due criteri sia sempre migliore.

Nella pratica producono spesso alberi molto simili.

---

## Domanda tipica

**Domanda**

> Quale criterio utilizza l'Information Gain?

**Risposta**

Entropy.

---

## Sigmoid vs Softmax

Entrambe trasformano valori numerici in probabilità, ma vengono usate in situazioni diverse.

---

## Sigmoid

Produce un solo valore compreso tra 0 e 1.

Formula

`σ(x) = 1 / (1 + e⁻ˣ)`

Viene utilizzata principalmente per:

- classificazione binaria;
- Logistic Regression;
- output binario delle Neural Networks.

---

## Softmax

Trasforma un vettore di valori in una distribuzione di probabilità.

La somma delle probabilità è pari a 1.

Viene utilizzata nella classificazione multiclasse.

---

## Confronto

| Sigmoid | Softmax |
|----------|----------|
| Classificazione binaria | Classificazione multiclasse |
| Una probabilità | Più probabilità |
| Output indipendente | Probabilità normalizzate |

---

## Errore tipico

Usare Softmax per classificazione binaria oppure Sigmoid per problemi multiclasse esclusivi.

---

## Domanda tipica

**Domanda**

> Una rete neurale deve classificare 12 specie di fiori.

Quale funzione di output useresti?

**Risposta**

Softmax.

---

## Classification vs Regression

Sono probabilmente i due problemi supervisionati più importanti.

---

## Classification

L'obiettivo è prevedere una categoria.

Esempi

- spam / non spam;
- cane / gatto;
- cliente solvibile / insolvente.

Metriche tipiche

- Accuracy;
- Precision;
- Recall;
- F1-score;
- ROC-AUC.

---

## Regression

L'obiettivo è prevedere un valore continuo.

Esempi

- prezzo di una casa;
- temperatura;
- consumo energetico;
- fatturato.

Metriche tipiche

- MAE;
- MSE;
- RMSE;
- R².

---

## Confronto

| Classification | Regression |
|----------------|-----------|
| Target categorico | Target numerico |
| Accuracy, F1 | MAE, RMSE |
| Logistic Regression | Linear Regression |

---

## Errore tipico

Pensare che Logistic Regression sia un algoritmo di regressione.

In realtà è un algoritmo di classificazione.

---

## Domanda tipica

**Domanda**

> Prevedere il prezzo di un appartamento è un problema di classificazione o regressione?

**Risposta**

Regressione.


---

## MAE vs MSE vs RMSE

Queste tre metriche vengono utilizzate nei problemi di regressione.

Servono a misurare quanto le predizioni numeriche del modello siano lontane dai valori reali.

---

## MAE

Il **Mean Absolute Error** misura la media degli errori assoluti.

Formula

`MAE = mean(|y - ŷ|)`

### Interpretazione

Indica l'errore medio nella stessa unità di misura del target.

### Quando usarlo

È utile quando vuoi una metrica semplice e meno sensibile agli outlier.

---

## MSE

Il **Mean Squared Error** misura la media degli errori al quadrato.

Formula

`MSE = mean((y - ŷ)²)`

### Interpretazione

Penalizza molto gli errori grandi.

### Quando usarlo

È utile quando gli errori grandi devono pesare molto nella valutazione.

---

## RMSE

Il **Root Mean Squared Error** è la radice quadrata del MSE.

Formula

`RMSE = sqrt(MSE)`

### Interpretazione

Come il MAE, è espresso nella stessa unità del target, ma rimane più sensibile agli errori grandi.

---

## Confronto

| Metrica | Caratteristica principale |
|---------|---------------------------|
| MAE | Errore medio assoluto |
| MSE | Penalizza molto gli errori grandi |
| RMSE | Radice del MSE, stessa unità del target |

---

## Errore tipico

Pensare che MAE, MSE e RMSE siano equivalenti.

Non lo sono.

MSE e RMSE penalizzano maggiormente gli errori grandi rispetto al MAE.

---

## Domanda tipica d'esame

**Domanda**

> Quale metrica di regressione penalizza maggiormente gli errori grandi?

**Risposta**

MSE, e di conseguenza anche RMSE.

---

## ROC Curve vs AUC

ROC Curve e AUC sono concetti collegati, ma non sono la stessa cosa.

---

## ROC Curve

La **ROC Curve** mostra il comportamento di un classificatore binario al variare della soglia decisionale.

Confronta:

- True Positive Rate;
- False Positive Rate.

---

## AUC

La **AUC** è l'area sotto la ROC Curve.

Rappresenta un valore sintetico della capacità del modello di distinguere le classi.

---

## Confronto

| ROC Curve | AUC |
|-----------|-----|
| È una curva | È un numero |
| Mostra diversi valori di soglia | Riassume la curva |
| Utile per analisi dettagliata | Utile per confronto rapido |

---

## Errore tipico

Pensare che ROC e AUC siano sinonimi.

La ROC è la curva.

La AUC è l'area sotto la curva.

---

## Domanda tipica d'esame

**Domanda**

> Che cosa rappresenta la AUC?

**Risposta**

L'area sotto la ROC Curve.

---

## Bagging vs Boosting

Bagging e Boosting sono tecniche di Ensemble Learning.

Entrambe combinano più modelli, ma lo fanno in modo diverso.

---

## Bagging

Nel **Bagging**, più modelli vengono addestrati in parallelo su campioni diversi del dataset.

L'obiettivo principale è ridurre la varianza.

Esempio:

- Random Forest.

---

## Boosting

Nel **Boosting**, i modelli vengono addestrati in sequenza.

Ogni nuovo modello cerca di correggere gli errori dei modelli precedenti.

Esempi:

- AdaBoost;
- Gradient Boosting;
- XGBoost;
- LightGBM.

---

## Confronto

| Bagging | Boosting |
|---------|----------|
| Modelli in parallelo | Modelli in sequenza |
| Riduce la varianza | Riduce bias e/o errori residui |
| Più robusto al rumore | Può essere più sensibile al rumore |
| Esempio: Random Forest | Esempio: Gradient Boosting |

---

## Errore tipico

Pensare che Random Forest sia un algoritmo di Boosting.

Non lo è.

Random Forest è basata su Bagging.

---

## Domanda tipica d'esame

**Domanda**

> Random Forest appartiene al Bagging o al Boosting?

**Risposta**

Bagging.

---

## Batch vs Mini-Batch vs Stochastic Gradient Descent

Questi termini indicano quanti esempi vengono usati per aggiornare i pesi durante il Gradient Descent.

---

## Batch Gradient Descent

Usa tutto il training set per ogni aggiornamento dei pesi.

### Vantaggi

- aggiornamento stabile;
- direzione del gradiente più precisa.

### Svantaggi

- costoso su dataset grandi;
- aggiornamenti lenti.

---

## Stochastic Gradient Descent

Usa un solo esempio alla volta per aggiornare i pesi.

### Vantaggi

- aggiornamenti frequenti;
- può essere più veloce per dataset grandi.

### Svantaggi

- andamento più rumoroso;
- convergenza meno stabile.

---

## Mini-Batch Gradient Descent

Usa piccoli gruppi di esempi.

È il compromesso più utilizzato nelle reti neurali.

---

## Confronto

| Tipo | Esempi usati per aggiornamento |
|------|--------------------------------|
| Batch | Tutto il dataset |
| Stochastic | Un solo esempio |
| Mini-Batch | Un gruppo di esempi |

---

## Errore tipico

Pensare che "batch" ed "epoch" siano sinonimi.

Non lo sono.

Un batch è un sottoinsieme di dati.

Un'epoch è un passaggio completo sull'intero training set.

---

## Epoch vs Iteration

Questi due termini vengono spesso confusi durante lo studio delle reti neurali.

---

## Epoch

Una **epoch** corrisponde a un passaggio completo su tutto il training set.

Se il dataset contiene 10.000 esempi, una epoch significa che il modello ha visto tutti i 10.000 esempi una volta.

---

## Iteration

Una **iteration** corrisponde a un singolo aggiornamento dei pesi.

Se si usa Mini-Batch Gradient Descent, ogni batch produce una iteration.

---

## Esempio

Dataset:

- 10.000 esempi;
- batch size = 100.

Allora:

- 1 epoch = 10.000 esempi visti;
- 1 epoch = 100 iterations.

---

## Confronto

| Epoch | Iteration |
|-------|-----------|
| Passaggio completo sul dataset | Singolo aggiornamento dei pesi |
| Contiene più batch | Coincide con un batch elaborato |
| Dipende dalla dimensione del dataset | Dipende dalla batch size |

---

## Domanda tipica d'esame

**Domanda**

> Se ho 1.000 esempi e batch size 100, quante iteration ci sono in una epoch?

**Risposta**

10 iteration.

---

## Training vs Inference

Training e Inference rappresentano due fasi diverse del ciclo di vita di un modello.

---

## Training

Durante il **training**, il modello apprende dai dati.

In questa fase vengono aggiornati i parametri.

Esempi:

- pesi della Logistic Regression;
- pesi delle Neural Networks;
- split di un Decision Tree.

---

## Inference

Durante l'**inference**, il modello già addestrato viene utilizzato per produrre nuove predizioni.

In questa fase i parametri non vengono aggiornati.

---

## Confronto

| Training | Inference |
|----------|-----------|
| Il modello apprende | Il modello predice |
| I parametri cambiano | I parametri restano fissi |
| Più costoso | Generalmente più veloce |
| Usa dati etichettati | Usa nuovi dati in input |

---

## Errore tipico

Pensare che durante l'inference il modello continui ad apprendere.

Normalmente non è così.

Il modello produce predizioni usando ciò che ha già imparato.

---

## Probability vs Prediction

Nei classificatori probabilistici è importante distinguere tra probabilità e predizione finale.

---

## Probability

La probabilità indica quanto il modello ritiene probabile una classe.

Esempio:

`P(classe positiva) = 0.82`

---

## Prediction

La predizione finale è la classe assegnata dopo aver applicato una soglia.

Esempio:

- probabilità = 0.82;
- soglia = 0.50;
- predizione = classe positiva.

---

## Confronto

| Probability | Prediction |
|-------------|------------|
| Valore continuo | Classe finale |
| Dipende dal modello | Dipende anche dalla soglia |
| Esprime confidenza | Esprime decisione |

---

## Errore tipico

Pensare che una probabilità di 0.51 e una di 0.99 siano equivalenti perché producono la stessa classe.

La predizione è la stessa, ma la confidenza del modello è molto diversa.

---

## Correlation vs Causation

Correlation e Causation sono due concetti fondamentali, ma spesso confusi.

---

## Correlation

Due variabili sono correlate quando variano insieme.

Esempio:

- quando aumenta una variabile, aumenta anche l'altra;
- oppure quando una aumenta, l'altra diminuisce.

---

## Causation

Causation significa che una variabile causa direttamente il cambiamento dell'altra.

---

## Confronto

| Correlation | Causation |
|-------------|-----------|
| Le variabili si muovono insieme | Una variabile causa l'altra |
| Non implica causalità | Implica relazione causa-effetto |
| Può essere casuale o indiretta | Richiede evidenza più forte |

---

## Errore tipico

Pensare che se due variabili sono correlate, allora una causa l'altra.

In Machine Learning questa è una trappola importante: il modello può usare correlazioni utili per predire, ma questo non significa che abbia scoperto cause reali.

---

## Tabella riassuntiva finale

| Trappola | Differenza chiave |
|----------|-------------------|
| Accuracy vs Precision | Accuracy misura tutte le predizioni corrette, Precision misura l'affidabilità dei positivi predetti |
| Precision vs Recall | Precision riduce falsi positivi, Recall riduce falsi negativi |
| Overfitting vs Underfitting | Overfitting = troppo complesso, Underfitting = troppo semplice |
| Bias vs Variance | Bias alto porta a Underfitting, Variance alta porta a Overfitting |
| Training vs Validation vs Test | Training apprende, Validation sceglie, Test valuta |
| Parameter vs Hyperparameter | Parameter appreso, Hyperparameter scelto prima |
| Standardization vs Normalization | Standardization produce media 0, Normalization porta in [0,1] |
| Scaling vs Engineering | Scaling cambia scala, Engineering crea informazione |
| Data Leakage vs Overfitting | Leakage è errore metodologico, Overfitting è eccessiva aderenza al training |
| Data Drift vs Concept Drift | Data Drift cambia input, Concept Drift cambia relazione input-target |
| Gini vs Entropy | Entrambe misurano impurità, Entropy è legata all'information gain |
| Sigmoid vs Softmax | Sigmoid per binario, Softmax per multiclasse |
| Classification vs Regression | Classi discrete vs valori continui |
| MAE vs RMSE | MAE meno sensibile agli outlier, RMSE più sensibile |
| ROC vs AUC | ROC è curva, AUC è area sotto la curva |
| Bagging vs Boosting | Bagging parallelo, Boosting sequenziale |
| Batch vs Mini-Batch vs SGD | Cambia il numero di esempi usati per aggiornare i pesi |
| Epoch vs Iteration | Epoch = dataset completo, Iteration = aggiornamento |
| Training vs Inference | Training apprende, Inference predice |
| Probability vs Prediction | Probabilità continua, predizione discreta |
| Correlation vs Causation | Correlazione non implica causalità |

---

## Checklist finale pre-esame

Prima dell'esame assicurati di saper spiegare senza appunti:

- [ ] Quando Accuracy è fuorviante.
- [ ] Differenza tra Precision e Recall.
- [ ] Differenza tra Overfitting e Underfitting.
- [ ] Differenza tra Bias e Variance.
- [ ] Ruolo di Training, Validation e Test Set.
- [ ] Differenza tra Parameter e Hyperparameter.
- [ ] Differenza tra Standardization e Normalization.
- [ ] Differenza tra Data Leakage e Overfitting.
- [ ] Differenza tra Data Drift e Concept Drift.
- [ ] Differenza tra Gini ed Entropy.
- [ ] Quando usare Sigmoid e quando Softmax.
- [ ] Differenza tra Classification e Regression.
- [ ] Differenza tra MAE, MSE e RMSE.
- [ ] Differenza tra ROC Curve e AUC.
- [ ] Differenza tra Bagging e Boosting.
- [ ] Differenza tra Batch, Mini-Batch e SGD.
- [ ] Differenza tra Epoch e Iteration.
- [ ] Differenza tra Training e Inference.
- [ ] Differenza tra probabilità e predizione.
- [ ] Perché correlation non implica causation.

---

## Stato editoriale

**Stato:** FINAL 1.0

Questo documento raccoglie le principali confusioni concettuali che possono comparire in un esame di Machine Learning e AI Engineering.

L'obiettivo non è sostituire i capitoli teorici, ma fornire una guida rapida per riconoscere le trappole più comuni e rispondere in modo preciso.

Eventuali aggiornamenti futuri potranno includere:

- nuove trappole emerse durante il proseguimento del Master;
- esempi aggiuntivi di domande d'esame;
- confronti con nuovi algoritmi non ancora trattati.