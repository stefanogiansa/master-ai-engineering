# Knowledge Graph del Master AI Engineering

## Appendice – Knowledge Graph

---

## Obiettivo

Questo documento rappresenta la mappa concettuale dell’intero repository.

L’obiettivo è mostrare le relazioni tra gli argomenti studiati durante il Master AI Engineering, evidenziando come i diversi concetti si collegano tra loro.

Ogni nodo del grafo rimanda ai relativi capitoli del repository.

---

## Visione d’insieme

```mermaid
graph TD
      AI --> ML[Machine Learning]
      AI --> DL[Deep Learning]
      DL --> NN[Neural Networks]
      ML --> SL[Supervised Learning]
      ML --> UL[Unsupervised Learning]
```

---

## Il dominio principale

Il repository ruota attorno a quattro macro-aree.

```mermaid
graph TD
      ML[Machine Learning] --> F[Fondamenti]
      ML --> A[Algoritmi]
      ML --> V[Valutazione]
      ML --> M[MLOps]
```

---

## Fondamenti

I fondamenti rappresentano la base teorica su cui si costruiscono tutti gli algoritmi successivi.

```mermaid
graph TD
      F[Fondamenti] --> Dataset
      F --> Feature
      F --> Target
      F --> Split[Train/Test Split]
      F --> Bias
      F --> Variance
      F --> Overfitting
      F --> Underfitting
      F --> Metriche
      F --> CV[Cross Validation]
```

Capitolo:

- fondamenti-machine-learning.md

---

## Machine Learning supervisionato

Gli algoritmi supervisionati apprendono da dati etichettati.

```mermaid
graph TD
      SL[Supervised Learning] --> LR[Logistic Regression]
      SL --> NB[Naive Bayes]
      SL --> SVM[SVM]
      SL --> KNN[KNN]
      SL --> DT[Decision Tree]
      SL --> RF[Random Forest]
      SL --> NN[Neural Networks]
```

Tutti gli algoritmi presenti nel repository appartengono a questa categoria.

---

## Relazioni tra gli algoritmi

```mermaid
graph TD
      ML[Machine Learning] --> Prob[Modelli probabilistici]
      ML --> Lin[Modelli lineari]
      ML --> Dist[Algoritmi basati sulla distanza]
      ML --> Margin[Massimo margine]
      ML --> Trees[Alberi decisionali]
      ML --> DL[Deep Learning]

      Prob --> NB[Naive Bayes]
      Lin --> LR[Logistic Regression]
      Dist --> KNN[KNN]
      Margin --> SVM[SVM]
      Trees --> DT[Decision Tree]
      Trees --> RF[Random Forest]
      DL --> NN[Neural Networks]
```

---

## Relazione tra preprocessing e algoritmi

```mermaid
graph TD
      P[Preprocessing] --> S[Standardizzazione]
      P --> N[Normalizzazione]
      P --> E[Encoding]
      P --> FE[Feature Engineering]
      FE --> AML[Algoritmi ML]
```

Non tutti gli algoritmi hanno le stesse esigenze.

| Algoritmo | Scaling consigliato |
|---|---|
| Logistic Regression | ✔ |
| SVM | ✔ |
| KNN | ✔ |
| Neural Networks | ✔ |
| Decision Tree | ✘ |
| Random Forest | ✘ |
| Naive Bayes | generalmente no |

---

## Collegamenti

Questa sezione si collega direttamente ai capitoli:

- fondamenti-machine-learning.md
- logistic-regression.md
- naive-bayes.md
- svm.md
- nearest-neighbors.md
- decision-tree-random-forest.md
- neural-networks.md

---

## Grafo delle dipendenze

Uno dei modi migliori per comprendere il Machine Learning consiste nell’osservare come ogni argomento costruisca le basi per il successivo.

Il seguente grafo rappresenta le principali dipendenze concettuali presenti nel repository.

---

## Dal dato al modello

```mermaid
flowchart TD
      D[Dataset] --> F[Feature]
      D --> T[Target]
      D --> P[Preprocessing]
      P --> MV[Missing Values]
      P --> E[Encoding]
      P --> S[Standardization]
      P --> N[Normalization]
      P --> ML[Machine Learning]
```

Prima di poter addestrare un modello è necessario preparare correttamente i dati.

Questa fase influenza direttamente le prestazioni di tutti gli algoritmi.

---

## Dalle probabilità a Naive Bayes

```mermaid
graph TD
      P[Probabilità] --> PC[Probabilità Condizionata]
      P --> TB[Teorema di Bayes]
      TB --> NB[Naive Bayes]
```

Dipendenze principali:

- probabilità;
- probabilità condizionata;
- prior;
- posterior;
- indipendenza condizionata.

Capitolo:

- naive-bayes.md

---

## Dal gradiente alle reti neurali

```mermaid
graph TD
      C[Funzione di costo] --> D[Derivata]
      C --> G[Gradiente]
      C --> LR[Learning Rate]
      G --> GD[Gradient Descent]
      GD --> LRR[Logistic Regression]
      GD --> NN[Neural Networks]
```

Il Gradient Descent rappresenta il collegamento naturale tra la Logistic Regression e le reti neurali.

Entrambi gli algoritmi apprendono aggiornando iterativamente i pesi.

---

## Evoluzione dei classificatori

```mermaid
graph TD
      C[Classificazione] --> LR[Logistic Regression]
      C --> NB[Naive Bayes]
      C --> SVM[SVM]
      C --> KNN[KNN]
      C --> DT[Decision Tree]
      C --> RF[Random Forest]
```

Ogni algoritmo affronta il problema della classificazione con una strategia differente:

| Algoritmo | Idea principale |
|---|---|
| Logistic Regression | modello lineare probabilistico |
| Naive Bayes | probabilità |
| SVM | margine massimo |
| KNN | vicini più prossimi |
| Decision Tree | regole decisionali |
| Random Forest | insieme di alberi |

---

## Alberi decisionali

```mermaid
graph TD
      E[Entropia] --> G[Gini Impurity]
      E --> IG[Information Gain]
      E --> DT[Decision Tree]
      DT --> RF[Random Forest]
```

La Random Forest estende il Decision Tree combinando molti alberi addestrati su campioni differenti.

---

## Dipendenze delle reti neurali

```mermaid
graph TD
      P[Perceptron] --> N[Neurone]
      P --> W[Pesi]
      P --> B[Bias]
      P --> AF[Funzione di Attivazione]
      AF --> R[ReLU]
      AF --> S[Sigmoid]
      AF --> T[Tanh]
      AF --> SM[Softmax]
      P --> FP[Forward Propagation]
      P --> L[Loss Function]
      P --> BP[Backpropagation]
      BP --> NN[Neural Network]
```

Le reti neurali rappresentano il punto di convergenza di numerosi concetti introdotti nei capitoli precedenti.

---

## Metriche di valutazione

```mermaid
graph TD
      P[Predizioni] --> CM[Confusion Matrix]
      P --> A[Accuracy]
      P --> PR[Precision]
      P --> R[Recall]
      P --> F1[F1-Score]
      P --> VM[Valutazione del modello]
```

Le metriche vengono utilizzate indipendentemente dall’algoritmo scelto.

Sono quindi un livello trasversale dell’intero repository.

---

## Il ruolo di MLOps

```mermaid
graph TD
      T[Training] --> MR[Model Registry]
      T --> D[Deployment]
      T --> API[API]
      T --> M[Monitoring]
      T --> DD[Data Drift]
      T --> CD[Concept Drift]
      T --> RT[Retraining]
```

MLOps non introduce nuovi algoritmi di Machine Learning.

Il suo ruolo consiste nel gestire il ciclo di vita dei modelli una volta completato l’addestramento.

---

## Relazioni principali

Le dipendenze fondamentali del repository possono essere riassunte come segue:

| Concetto | Porta a |
|---|---|
| Probabilità | Naive Bayes |
| Gradient Descent | Logistic Regression, Neural Networks |
| Entropia | Decision Tree |
| Decision Tree | Random Forest |
| Distanza Euclidea | KNN |
| Margine | SVM |
| Metriche | Valutazione |
| Deployment | MLOps |

---

## Percorso di apprendimento consigliato

L’ordine dei capitoli del repository segue una progressione naturale:

```mermaid
flowchart TD
    F[Fondamenti] --> GD[Gradient Descent] --> LR[Logistic Regression]
    LR --> NB[Naive Bayes]
    LR --> SVM[SVM]
    LR --> KNN[KNN]
    LR --> DT[Decision Tree]
    DT --> RF[Random Forest]
    LR --> NN[Neural Networks]
    NN --> MLOps[MLOps]
```

Questa sequenza permette di acquisire gradualmente le conoscenze necessarie, costruendo ogni nuovo argomento sulle basi di quelli precedenti.

---

## Grafo completo del repository

L'intero repository può essere rappresentato come una rete di conoscenze nella quale ogni capitolo dipende dai precedenti e costituisce la base per quelli successivi.

```mermaid
graph TD
      AI --> ML[Machine Learning]
      AI --> DL[Deep Learning]
      DL --> NN[Neural Networks]

      ML --> F[Fondamenti]
      ML --> A[Algoritmi]
      ML --> V[Valutazione]
      ML --> M[MLOps]

      A --> LR[Logistic Regression]
      LR --> GD[Gradient Descent]
      GD --> NN
      LR --> NB[Naive Bayes]
      LR --> SVM[SVM]
      LR --> KNN[KNN]
      LR --> DT[Decision Tree]
      DT --> RF[Random Forest]

      V --> Metrics[Metriche comuni]
```

---

## Mappa delle dipendenze

La seguente tabella mostra le dipendenze principali tra i capitoli.

| Capitolo | Prerequisiti | Concetti acquisiti |
|----------|--------------|--------------------|
| Fondamenti | Nessuno | Dataset, Feature, Target, Metriche |
| Gradient Descent | Fondamenti | Ottimizzazione |
| Logistic Regression | Gradient Descent | Classificazione probabilistica |
| Naive Bayes | Probabilità | Classificazione probabilistica |
| SVM | Fondamenti | Margine massimo |
| KNN | Fondamenti | Algoritmi basati sulla distanza |
| Decision Tree | Entropia, Gini | Alberi decisionali |
| Random Forest | Decision Tree | Ensemble Learning |
| Neural Networks | Gradient Descent | Deep Learning |
| MLOps | Tutti gli algoritmi | Produzione e monitoraggio |

---

## Concetti condivisi

Molti concetti sono trasversali a più capitoli.

## Preprocessing

```mermaid
graph TD
      P[Preprocessing] --> LR[Logistic Regression]
      P --> SVM[SVM]
      P --> KNN[KNN]
      P --> NN[Neural Networks]
```

---

## Gradient Descent

```mermaid
graph TD
      GD[Gradient Descent] --> LR[Logistic Regression]
      GD --> NN[Neural Networks]
```

---

## Probabilità

```mermaid
graph TD
      P[Probabilità] --> NB[Naive Bayes]
```

---

## Entropia

```mermaid
graph TD
      E[Entropia] --> DT[Decision Tree]
      DT --> RF[Random Forest]
```

---

## Metriche

```mermaid
graph TD
      M[Metriche] --> LR[Logistic Regression]
      M --> NB[Naive Bayes]
      M --> SVM[SVM]
      M --> KNN[KNN]
      M --> DT[Decision Tree]
      M --> RF[Random Forest]
      M --> NN[Neural Networks]
```

Le metriche rappresentano uno degli elementi maggiormente condivisi tra tutti gli algoritmi studiati.

---

## Percorsi di studio consigliati

Il repository può essere affrontato seguendo percorsi differenti in funzione dell'obiettivo.

## Primo studio

```mermaid
flowchart TD
    F[Fondamenti] --> GD[Gradient Descent] --> LR[Logistic Regression] --> NB[Naive Bayes] --> SVM[SVM] --> KNN[KNN] --> DT[Decision Tree] --> RF[Random Forest] --> NN[Neural Networks] --> MLOps[MLOps]
```

---

## Ripasso rapido

```mermaid
flowchart TD
    F[Fondamenti] --> A[Algoritmi] --> M[Metriche] --> MLOps[MLOps]
```

---

## Preparazione all'esame

```mermaid
flowchart TD
    F[Fondamenti] --> FO[Formulario] --> G[Glossario] --> KG[Knowledge Graph] --> CA[Confronto algoritmi]
```

---

## Collegamenti con le appendici

Questo documento si integra con:

| Documento | Scopo |
|-----------|-------|
| formulario.md | Raccoglie tutte le formule |
| glossario.md | Definisce i principali termini |
| comparison.md | Confronta gli algoritmi |
| cheat-sheet.md | Ripasso rapido |
| exam-simulation.md | Simulazione dell'esame |

---

## Come utilizzare il Knowledge Graph

Questo documento può essere consultato in diversi momenti dello studio:

- all'inizio, per comprendere la struttura complessiva del corso;
- durante lo studio, per individuare le dipendenze tra gli argomenti;
- prima dell'esame, come mappa concettuale di ripasso;
- dopo il Master, come indice generale del repository.

L'obiettivo non è sostituire i singoli capitoli, ma mostrare come essi si collegano tra loro.

---

## Checklist finale

Al termine della lettura dovresti essere in grado di:

- comprendere la struttura dell'intero repository;
- identificare le dipendenze tra i capitoli;
- distinguere i concetti fondamentali da quelli avanzati;
- individuare rapidamente il capitolo in cui approfondire un argomento;
- scegliere un percorso di studio in funzione dell'obiettivo.

---

## Stato editoriale

**Stato:** FINAL 1.0

Il Knowledge Graph rappresenta la mappa concettuale dell'intero repository.

Il documento mostra le relazioni tra i principali argomenti del Master AI Engineering e costituisce il punto di collegamento tra i capitoli teorici e le appendici di supporto.

Eventuali aggiornamenti futuri riguarderanno esclusivamente:

- l'aggiunta di nuovi capitoli;
- l'inserimento di nuove relazioni tra i concetti;
- il miglioramento della rappresentazione grafica.
