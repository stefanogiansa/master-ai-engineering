# Glossario di Machine Learning

## Appendice – Glossario

---

### Obiettivo dell’appendice

Questo glossario raccoglie i principali termini utilizzati nel Machine Learning e in MLOps.

Le definizioni sono volutamente sintetiche ma rigorose e fanno riferimento ai capitoli del repository per gli approfondimenti.

Le voci sono ordinate alfabeticamente.

---

## A

### Accuracy

Percentuale di predizioni corrette effettuate da un classificatore.

È una metrica semplice da interpretare ma può risultare fuorviante in presenza di dataset sbilanciati.

#### Capitoli

- fondamenti-machine-learning.md
- logistic-regression.md

---

### Activation Function

Funzione matematica utilizzata nelle reti neurali per introdurre non linearità.

Le più comuni sono:

- ReLU
- Sigmoid
- Tanh
- Softmax

#### Capitolo

- neural-networks.md

---

### API

(Application Programming Interface)

Insieme di endpoint che permettono ad applicazioni differenti di comunicare.

Nel Master vengono implementate tramite FastAPI.

#### Capitolo

- mlops.md

---

### Artificial Intelligence (AI)

Disciplina che studia sistemi capaci di svolgere compiti normalmente associati all’intelligenza umana.

Il Machine Learning rappresenta uno dei principali sottoinsiemi dell’AI.

#### Capitolo

- fondamenti-machine-learning.md

---

### AUC

(Area Under the Curve)

Area sotto la curva ROC.

Misura la capacità di un classificatore di distinguere tra classi differenti.

Valori vicini a 1 indicano classificatori molto efficaci.

---

## B

### Backpropagation

Algoritmo utilizzato per calcolare il gradiente nelle reti neurali.

Permette di aggiornare i pesi mediante Gradient Descent.

#### Capitolo

- neural-networks.md

---

### Batch

Insieme di osservazioni elaborate contemporaneamente durante il training.

Può coincidere con:

- intero dataset;
- mini-batch;
- singolo campione.

---

### Batch Gradient Descent

Variante del Gradient Descent che utilizza l’intero dataset per ogni aggiornamento dei pesi.

È stabile ma computazionalmente costosa.

#### Capitolo

- gradient-descent.md

---

### Bias

Parametro additivo di un modello oppure errore sistematico nel contesto del Bias–Variance Tradeoff.

Il significato dipende dal contesto.

#### Capitoli

- fondamenti-machine-learning.md
- neural-networks.md

---

### Binary Classification

Problema di classificazione con due sole classi.

Esempi:

- spam / non spam;
- sì / no;
- vero / falso.

---

### Binary Cross Entropy

Funzione di costo utilizzata nella Logistic Regression.

Penalizza fortemente previsioni molto sicure ma errate.

#### Capitolo

- logistic-regression.md

---

## C

### Canary Deployment

Strategia di rilascio che distribuisce inizialmente una nuova versione del modello ad una piccola percentuale di utenti.

Permette di ridurre il rischio durante il deployment.

#### Capitolo

- mlops.md

---

### Classification

Problema di Machine Learning in cui il target appartiene ad un insieme finito di categorie.

Gli algoritmi studiati nel Master sono principalmente classificatori.

---

### Classifier

Algoritmo che assegna un’osservazione ad una classe.

Esempi:

- Logistic Regression;
- Naive Bayes;
- SVM;
- Decision Tree;
- Random Forest.

---

### Concept Drift

Cambiamento della relazione tra input e output nel tempo.

Può rendere progressivamente meno accurato un modello in produzione.

#### Capitolo

- mlops.md

---

### Confusion Matrix

Tabella che riassume il numero di:

- True Positive;
- True Negative;
- False Positive;
- False Negative.

Costituisce la base per il calcolo di Accuracy, Precision e Recall.

---

### Container

Unità software isolata che contiene applicazione, dipendenze e configurazione.

Docker rappresenta la tecnologia di containerizzazione più diffusa.

#### Capitolo

- mlops.md

---

### Cross Entropy

Funzione di perdita utilizzata nei problemi di classificazione.

Nella classificazione binaria prende il nome di Binary Cross Entropy.

---

### Cross Validation

Tecnica utilizzata per stimare in maniera robusta le prestazioni di un modello.

La variante più diffusa è la K-Fold Cross Validation.

#### Capitolo

- fondamenti-machine-learning.md

---

### CUDA

Piattaforma di calcolo parallelo sviluppata da NVIDIA.

Permette di accelerare il training delle reti neurali utilizzando la GPU.

---

### Curva ROC

Grafico che rappresenta il compromesso tra:

- True Positive Rate;
- False Positive Rate.

È uno degli strumenti più utilizzati per valutare classificatori binari.

---

## D

### Data Drift

Fenomeno per cui la distribuzione dei dati in ingresso cambia nel tempo rispetto ai dati utilizzati durante l’addestramento.

Può causare un degrado delle prestazioni del modello anche se quest’ultimo non è cambiato.

#### Capitolo

- mlops.md

---

### Data Engineering

Disciplina che si occupa della raccolta, trasformazione, archiviazione e preparazione dei dati.

Costituisce uno dei pilastri di MLOps insieme a Machine Learning e DevOps.

#### Capitolo

- mlops.md

---

### Data Leakage

Situazione in cui il modello utilizza, durante l’addestramento, informazioni che nella realtà non sarebbero disponibili al momento della previsione.

Produce valutazioni artificialmente ottimistiche.

---

### Data Scientist

Professionista che analizza i dati, costruisce modelli e valuta le prestazioni degli algoritmi.

Collabora con il ML Engineer per il rilascio in produzione.

#### Capitolo

- mlops.md

---

### Dataset

Collezione organizzata di osservazioni utilizzata per addestrare e valutare un modello.

Generalmente è composta da:

- feature;
- target;
- campioni.

#### Capitolo

- fondamenti-machine-learning.md

---

### Decision Boundary

Superficie che separa le classi in un problema di classificazione.

Nella Logistic Regression e nella SVM lineare è un iperpiano.

#### Capitoli

- logistic-regression.md
- svm.md

---

### Decision Tree

Algoritmo supervisionato che costruisce una struttura ad albero scegliendo iterativamente gli split migliori.

Può essere utilizzato sia per classificazione sia per regressione.

#### Capitolo

- decision-tree-random-forest.md

---

### Deep Learning

Sottoinsieme del Machine Learning basato su reti neurali profonde.

È particolarmente efficace in Computer Vision, NLP e Speech Recognition.

#### Capitolo

- neural-networks.md

---

### Deployment

Processo di pubblicazione di un modello in ambiente di produzione.

In MLOps rappresenta una delle fasi fondamentali del ciclo di vita.

#### Capitolo

- mlops.md

---

### Docker

Piattaforma di containerizzazione che consente di distribuire applicazioni e modelli in maniera riproducibile.

È uno degli strumenti fondamentali di MLOps.

#### Capitolo

- mlops.md

---

### Drift

Termine generale che indica un cambiamento nel comportamento dei dati o del modello nel tempo.

Comprende:

- Data Drift;
- Concept Drift.

---

## E

### Early Stopping

Tecnica utilizzata durante l’addestramento per interrompere il training quando le prestazioni sul validation set smettono di migliorare.

Riduce il rischio di overfitting.

#### Capitolo

- neural-networks.md

---

### Entropia

Misura dell’incertezza presente in un insieme di dati.

Negli alberi decisionali viene utilizzata per scegliere gli split migliori.

#### Capitolo

- decision-tree-random-forest.md

---

### Epoch

Passaggio completo dell’intero training set attraverso il modello.

Il training di una rete neurale è normalmente composto da molte epoche.

#### Capitolo

- neural-networks.md

---

### Evaluation

Fase del ciclo di vita del Machine Learning in cui vengono misurate le prestazioni del modello mediante opportune metriche.

#### Capitoli

- fondamenti-machine-learning.md
- mlops.md

---

### Evidence

Nel Teorema di Bayes rappresenta la probabilità dell’evidenza osservata.

È indicata con: P(B)

#### Capitolo

- naive-bayes.md

---

## F

### F1-Score

Metrica ottenuta come media armonica di Precision e Recall.

È particolarmente indicata in presenza di dataset sbilanciati.

#### Capitoli

- fondamenti-machine-learning.md
- logistic-regression.md

---

### False Negative (FN)

Osservazione positiva classificata erroneamente come negativa.

In molti contesti (ad esempio diagnosi medica) rappresenta uno degli errori più gravi.

---

### False Positive (FP)

Osservazione negativa classificata erroneamente come positiva.

Ridurre i falsi positivi aumenta generalmente la Precision.

---

### FastAPI

Framework Python moderno per la realizzazione di API REST.

Nel Master viene utilizzato per pubblicare modelli di Machine Learning in produzione.

#### Capitolo

- mlops.md

---

### Feature

Variabile di input utilizzata dal modello per effettuare una previsione.

Le feature costituiscono la base dell’apprendimento supervisionato.

#### Capitolo

- fondamenti-machine-learning.md

---

### Feature Engineering

Processo di creazione, trasformazione e selezione delle feature.

Una buona attività di Feature Engineering può migliorare significativamente le prestazioni di un modello.

#### Capitolo

- fondamenti-machine-learning.md

---

### Feature Scaling

Tecnica di normalizzazione delle feature per renderle confrontabili.

È particolarmente importante per algoritmi come:

- Logistic Regression;
- SVM;
- KNN;
- Neural Networks.

#### Capitolo

- fondamenti-machine-learning.md

---

### Feature Store

Repository centralizzato utilizzato in MLOps per archiviare e riutilizzare feature coerenti tra training e produzione.

#### Capitolo

- mlops.md

---

### Fine Tuning

Tecnica che consiste nel riaddestrare parzialmente un modello pre-addestrato su un nuovo dataset.

È molto utilizzata con i Large Language Model e i modelli di Hugging Face.

---

### Fold

Una delle partizioni generate durante una K-Fold Cross Validation.

Ogni fold viene utilizzato, a turno, come validation set.

---

### Forward Propagation

Fase della rete neurale in cui gli input attraversano tutti gli strati fino alla produzione dell’output.

Successivamente interviene la Backpropagation per aggiornare i pesi.

---

## G

### Generalizzazione

Capacità di un modello di ottenere buone prestazioni su dati mai osservati durante l’addestramento.

La generalizzazione rappresenta l’obiettivo principale del Machine Learning.

#### Capitolo

- fondamenti-machine-learning.md

---

### Gini Impurity

Misura dell’impurità di un nodo in un albero decisionale.

Valori bassi indicano una buona separazione tra le classi.

Viene utilizzata come criterio di split nei Decision Tree e nelle Random Forest.

#### Capitolo

- decision-tree-random-forest.md

---

### Gradient

Vettore delle derivate parziali della funzione di costo rispetto ai parametri del modello.

Indica la direzione di massima crescita della funzione obiettivo.

Il Gradient Descent procede nella direzione opposta.

#### Capitolo

- gradient-descent.md

---

### Gradient Descent

Algoritmo di ottimizzazione utilizzato per minimizzare la funzione di costo aggiornando iterativamente i pesi del modello.

È alla base della Logistic Regression e delle Neural Networks.

#### Capitoli

- gradient-descent.md
- logistic-regression.md
- neural-networks.md

---

### GPU

(Graphics Processing Unit)

Processore specializzato nell’elaborazione parallela.

Viene utilizzato per accelerare il training delle reti neurali e dei modelli di Deep Learning.

---

## H

### Hidden Layer

Strato intermedio di una rete neurale.

Ogni Hidden Layer applica una trasformazione ai dati mediante pesi, bias e funzioni di attivazione.

#### Capitolo

- neural-networks.md

---

### Hugging Face

Piattaforma dedicata alla condivisione di modelli, dataset e applicazioni di Machine Learning.

Nel Master viene utilizzata per scaricare modelli pre-addestrati e pubblicare applicazioni tramite Spaces.

#### Capitolo

- mlops.md

---

### Hyperparameter

Parametro che controlla il comportamento dell’algoritmo ma non viene appreso automaticamente durante il training.

Esempi:

- Learning Rate;
- numero di epoche;
- numero di alberi;
- valore di K;
- parametro C.

---

### Hyperparameter Tuning

Processo di ricerca della combinazione ottimale di iperparametri.

Tecniche comuni:

- Grid Search;
- Random Search;
- Bayesian Optimization.

#### Capitoli

- logistic-regression.md
- mlops.md

---

## I

### Inference

Fase in cui un modello già addestrato viene utilizzato per effettuare nuove predizioni.

Può essere:

- Batch Inference;
- Online Inference.

Nel progetto del Master l’inferenza viene esposta tramite FastAPI.

#### Capitolo

- mlops.md

---

### Information Gain

Riduzione dell’entropia ottenuta dopo uno split in un Decision Tree.

Lo split con Information Gain maggiore viene generalmente selezionato per costruire il nodo successivo.

#### Capitolo

- decision-tree-random-forest.md

---

### Input Layer

Primo strato di una rete neurale.

Riceve le feature del dataset e le inoltra agli strati successivi.

#### Capitolo

- neural-networks.md

---

## K

### K-Fold Cross Validation

Tecnica di validazione che suddivide il dataset in K parti.

Ogni fold viene utilizzato una volta come validation set e K−1 volte come training set.

Permette di ottenere una stima più robusta delle prestazioni del modello.

#### Capitolo

- fondamenti-machine-learning.md

---

### Kernel

Funzione utilizzata nelle Support Vector Machine per rappresentare implicitamente i dati in uno spazio a dimensionalità superiore.

Kernel comuni:

- Lineare;
- Polinomiale;
- RBF;
- Sigmoid.

#### Capitolo

- svm.md

---

### KNN

(K-Nearest Neighbors)

Algoritmo supervisionato basato sulla distanza tra osservazioni.

La classe viene determinata dai K vicini più prossimi.

#### Capitolo

- nearest-neighbors.md

---

### Kubernetes

Piattaforma di orchestrazione dei container.

Consente di distribuire e gestire applicazioni containerizzate su larga scala.

È uno dei principali strumenti di MLOps.

#### Capitolo

- mlops.md

---

## L

### Label

Valore corretto associato ad una osservazione.

Nel Machine Learning supervisionato coincide con il target.

#### Capitolo

- fondamenti-machine-learning.md

---

### Learning Rate

Parametro che controlla la dimensione dell’aggiornamento dei pesi durante il Gradient Descent.

Un valore troppo elevato può impedire la convergenza, mentre un valore troppo basso rallenta l’addestramento.

#### Capitolo

- gradient-descent.md

---

### Logistic Regression

Algoritmo supervisionato di classificazione che utilizza la funzione sigmoide per stimare la probabilità di appartenenza ad una classe.

Nonostante il nome, è un classificatore.

#### Capitolo

- logistic-regression.md

---

### Log Loss

Funzione di costo utilizzata nella Logistic Regression.

È nota anche come Binary Cross Entropy.

#### Capitolo

- logistic-regression.md

---

### Loss Function

Funzione matematica che misura l’errore commesso dal modello.

L’obiettivo del training consiste nel minimizzarla.

#### Capitoli

- gradient-descent.md
- logistic-regression.md
- neural-networks.md

---

## M

### Machine Learning

Disciplina dell’Intelligenza Artificiale che consente ai sistemi di apprendere automaticamente dai dati.

Comprende algoritmi supervisionati, non supervisionati e di reinforcement learning.

#### Capitolo

- fondamenti-machine-learning.md

---

### Margin

Distanza tra l’iperpiano e i Support Vectors in una SVM.

Massimizzare il margine migliora generalmente la capacità di generalizzazione del modello.

#### Capitolo

- svm.md

---

### Mini-Batch Gradient Descent

Variante del Gradient Descent che aggiorna i pesi utilizzando piccoli gruppi di osservazioni.

Rappresenta il metodo più utilizzato per addestrare reti neurali profonde.

#### Capitolo

- gradient-descent.md

---

### MLOps

Insieme di pratiche che integrano Machine Learning, DevOps e Data Engineering per automatizzare il ciclo di vita dei modelli.

Comprende:

- training;
- deployment;
- monitoring;
- retraining.

#### Capitolo

- mlops.md

---

### Model Registry

Repository centralizzato che conserva le diverse versioni dei modelli addestrati.

Permette di gestire versionamento, tracciabilità e distribuzione.

#### Capitolo

- mlops.md

---

### Monitoring

Attività di controllo continuo delle prestazioni di un modello in produzione.

Comprende il monitoraggio di:

- accuratezza;
- latenza;
- throughput;
- data drift;
- concept drift.

#### Capitolo

- mlops.md

---

## N

### Naive Bayes

Algoritmo probabilistico supervisionato basato sul Teorema di Bayes e sull'ipotesi di indipendenza condizionata tra le feature.

È molto utilizzato nella classificazione testuale, ad esempio nello spam filtering.

#### Capitolo

- naive-bayes.md

---

### Neural Network

Modello di Machine Learning ispirato in modo astratto al funzionamento dei neuroni biologici.

È composto da strati, pesi, bias e funzioni di attivazione.

#### Capitolo

- neural-networks.md

---

### Normalization

Tecnica di preprocessing che trasforma i valori delle feature in un intervallo definito, spesso tra 0 e 1.

#### Capitoli

- fondamenti-machine-learning.md
- nearest-neighbors.md
- neural-networks.md

---

## O

### Overfitting

Fenomeno per cui un modello apprende troppo bene il training set, includendo rumore e dettagli non generalizzabili.

#### Capitoli

- fondamenti-machine-learning.md
- decision-tree-random-forest.md
- neural-networks.md

---

## P

### Pipeline

Sequenza ordinata di passaggi che combina preprocessing, trasformazioni e modello finale.

In scikit-learn consente di evitare errori di preprocessing e rendere il workflow più riproducibile.

#### Capitoli

- logistic-regression.md
- nearest-neighbors.md
- neural-networks.md
- mlops.md

---

### Precision

Metrica di classificazione che misura, tra tutte le osservazioni predette come positive, quante sono realmente positive.

#### Capitoli

- fondamenti-machine-learning.md
- logistic-regression.md

---

### Preprocessing

Insieme delle trasformazioni applicate ai dati prima dell'addestramento del modello.

Comprende pulizia, scaling, encoding, gestione dei valori mancanti e trasformazioni delle feature.

#### Capitolo

- fondamenti-machine-learning.md

---

### Pydantic

Libreria Python utilizzata da FastAPI per definire e validare i modelli dei dati in ingresso e in uscita.

#### Capitolo

- mlops.md

---

## R

### Random Forest

Algoritmo ensemble composto da molti Decision Tree addestrati su campioni bootstrap e sottoinsiemi casuali di feature.

#### Capitolo

- decision-tree-random-forest.md

---

### Recall

Metrica di classificazione che misura, tra tutte le osservazioni realmente positive, quante sono state individuate dal modello.

#### Capitoli

- fondamenti-machine-learning.md
- logistic-regression.md

---

### Regularization

Tecnica utilizzata per limitare l'overfitting penalizzando modelli troppo complessi.

#### Capitoli

- logistic-regression.md
- neural-networks.md
- decision-tree-random-forest.md

---

### ReLU

(Rectified Linear Unit)

Funzione di attivazione molto utilizzata nelle reti neurali.

#### Capitolo

- neural-networks.md

---

### REST API

API progettata secondo i principi REST, basata su risorse, metodi HTTP e rappresentazioni come JSON.

#### Capitolo

- mlops.md

---

### Retraining

Processo di riaddestramento di un modello dopo il deployment.

#### Capitolo

- mlops.md

---

### ROC Curve

Curva che rappresenta il compromesso tra True Positive Rate e False Positive Rate per diverse soglie di classificazione.

#### Capitolo

- logistic-regression.md

---

## S

### Scikit-learn

Libreria Python per Machine Learning classico.

Fornisce algoritmi, preprocessing, metriche, pipeline, train/test split e strumenti di validazione.

#### Capitoli

- logistic-regression.md
- svm.md
- nearest-neighbors.md
- decision-tree-random-forest.md

---

### Sigmoid

Funzione matematica che trasforma un valore reale in un valore compreso tra 0 e 1.

È utilizzata nella Logistic Regression e in alcune reti neurali.

#### Capitoli

- logistic-regression.md
- neural-networks.md

---

### Softmax

Funzione che trasforma un vettore di punteggi in una distribuzione di probabilità.

È utilizzata nei problemi di classificazione multiclasse.

#### Capitolo

- neural-networks.md

---

### Standardization

Tecnica di scaling che trasforma una feature in modo che abbia media 0 e deviazione standard 1.

Formula:

```text
x' = (x - μ) / σ
```

#### Capitolo

- fondamenti-machine-learning.md

---

### Supervised Learning

Paradigma di apprendimento in cui il modello viene addestrato su dati etichettati.

Comprende problemi di classificazione e regressione.

#### Capitolo

- fondamenti-machine-learning.md

---

### Support Vector Machine

Algoritmo supervisionato che cerca l’iperpiano capace di separare le classi massimizzando il margine.

Può gestire problemi non lineari tramite kernel trick.

#### Capitolo

- svm.md

---

## T

### Target

Variabile che il modello deve imparare a prevedere.

#### Capitolo

- fondamenti-machine-learning.md

---

### Test Set

Porzione del dataset utilizzata per valutare le prestazioni finali del modello.

Non deve essere usata durante training o tuning.

#### Capitolo

- fondamenti-machine-learning.md

---

### Training Set

Porzione del dataset utilizzata per addestrare il modello.

#### Capitolo

- fondamenti-machine-learning.md

---

## U

### Underfitting

Fenomeno per cui un modello è troppo semplice per rappresentare la struttura del problema.

#### Capitolo

- fondamenti-machine-learning.md

---

### Unsupervised Learning

Paradigma di apprendimento in cui il modello lavora su dati non etichettati.

#### Capitolo

- fondamenti-machine-learning.md

---

## V

### Validation Set

Porzione del dataset utilizzata per confrontare modelli e scegliere iperparametri.

#### Capitolo

- fondamenti-machine-learning.md

---

### Variance

Nel Bias-Variance Tradeoff indica quanto il modello è sensibile alle variazioni del training set.

#### Capitolo

- fondamenti-machine-learning.md

---

## W

### Weight

Parametro appreso dal modello durante il training.

#### Capitoli

- logistic-regression.md
- neural-networks.md

---

## Z

### Z-Score

Misura di quante deviazioni standard un valore si discosta dalla media.

Formula:

z = (x - μ) / σ

#### Capitolo

- fondamenti-machine-learning.md

---

### Stato editoriale

Stato: FINAL 1.0

Questo glossario raccoglie i principali termini del Master AI Engineering e fornisce un riferimento rapido per lo studio, il ripasso e la consultazione dei capitoli del repository.
