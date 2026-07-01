# Cheat Sheet

Ripasso rapido del Master AI Engineering

---

## Come utilizzare questo documento

Questo Cheat Sheet è progettato per un ripasso estremamente rapido.

Non sostituisce i capitoli teorici del repository.

L’obiettivo è fornire, in poche pagine, tutti i concetti essenziali da ricordare prima di un esame, un colloquio tecnico o l’implementazione di un progetto.

---

## Workflow del Machine Learning

Problema
↓
Dataset
↓
Preprocessing
↓
Training
↓
Valutazione
↓
Deployment
↓
Monitoring
↓
Retraining

Ricorda:

- il Machine Learning è un processo;
- l’algoritmo è solo una fase del workflow.

---

## Fondamenti

Dataset

- insieme delle osservazioni

Feature

- variabili di input

Target

- variabile da prevedere

Classificazione

- output discreto

Regressione

- output numerico

Overfitting

- ottimo training
- pessimo test

Underfitting

- pessimo training
- pessimo test

---

## Metriche

| Metrica | Quando usarla |
|---|---|
| Accuracy | dataset bilanciati |
| Precision | ridurre FP |
| Recall | ridurre FN |
| F1 | classi sbilanciate |
| ROC-AUC | confronto classificatori |

Regola pratica:

Accuracy da sola non basta.

---

## Gradient Descent

Obiettivo:

↓

minimizzare la Loss Function

Aggiornamento:

w = w − α∇J(w)

Ricorda:

- α piccolo → lento
- α grande → instabile

---

## Logistic Regression

✔ classificazione

✔ sigmoide

✔ Binary Cross Entropy

✔ Gradient Descent

Richiede:

- scaling

Vantaggi

- semplice
- veloce
- interpretabile

Svantaggi

- relazioni quasi lineari

---

## Naive Bayes

Idea principale

↓

Teorema di Bayes

Ipotesi

↓

feature indipendenti

Ottimo per

- testo
- spam
- dataset piccoli

Generalmente

↓

non richiede scaling

---

## Support Vector Machine

Idea

↓

massimizzare il margine

Richiede

↓

feature scalate

Punti di forza

- dataset piccoli
- alta accuratezza

Parametri

- C
- Kernel

Kernel comuni

- Lineare
- Polinomiale
- RBF

---

## K-Nearest Neighbors (KNN)

Idea

↓

i K vicini più simili votano la classe.

Richiede

- scaling ✔

Parametri

- K
- distanza

Distanze comuni

- Euclidea
- Manhattan

Vantaggi

- semplice
- nessun training reale
- ottima baseline

Svantaggi

- inferenza lenta
- sensibile agli outlier
- soffre l’aumento delle dimensioni

Ottimo per

- dataset piccoli
- prototipi

---

## Decision Tree

Idea

↓

serie di domande (split) fino alla classificazione.

Criteri di split

- Gini
- Entropia
- Information Gain

Richiede

- scaling ✘

Vantaggi

- molto interpretabile
- gestisce feature numeriche e categoriche
- facile da spiegare

Svantaggi

- overfitting
- instabilità

Ottimo per

- analisi esplorativa
- modelli interpretabili

---

## Random Forest

Idea

↓

molti Decision Tree

↓

votazione finale

Richiede

- scaling ✘

Riduce

- overfitting
- varianza

Tecniche utilizzate

- Bagging
- Bootstrap
- Feature Randomness

Vantaggi

- molto accurata
- robusta
- pochi parametri

Svantaggi

- meno interpretabile
- modello più pesante

Ottimo per

- dataset tabellari
- problemi generici

---

## Neural Networks

Idea

↓

molti neuroni

↓

più layer

↓

apprendimento distribuito

Componenti

- Input Layer
- Hidden Layer
- Output Layer

Funzioni di attivazione

- ReLU
- Sigmoid
- Tanh
- Softmax

Training

↓

Forward Propagation

↓

Loss Function

↓

Backpropagation

↓

Gradient Descent

Richiede

- molti dati
- GPU (spesso)
- scaling ✔

Vantaggi

- enorme capacità di rappresentazione
- Computer Vision
- NLP
- Audio

Svantaggi

- poca interpretabilità
- training lungo
- tuning complesso

---

## Quando usare quale algoritmo

| Situazione | Algoritmo |
|---|---|
| Problema lineare | Logistic Regression |
| Testo | Naive Bayes |
| Dataset piccolo | SVM |
| Baseline veloce | KNN |
| Modello interpretabile | Decision Tree |
| Dataset tabellare | Random Forest |
| Immagini | Neural Networks |
| Audio | Neural Networks |
| NLP moderno | Neural Networks |

---

Richiede Feature Scaling?

| Algoritmo | Scaling |
|---|---|
| Logistic Regression | ✔ |
| Naive Bayes | ✘ |
| SVM | ✔ |
| KNN | ✔ |
| Decision Tree | ✘ |
| Random Forest | ✘ |
| Neural Networks | ✔ |

---

## Complessità degli algoritmi

| Algoritmo | Difficoltà |
|---|---|
| Logistic Regression | ⭐⭐☆☆☆ |
| Naive Bayes | ⭐⭐☆☆☆ |
| KNN | ⭐⭐☆☆☆ |
| Decision Tree | ⭐⭐☆☆☆ |
| Random Forest | ⭐⭐⭐☆☆ |
| SVM | ⭐⭐⭐⭐☆ |
| Neural Networks | ⭐⭐⭐⭐⭐ |

---

## Cose da ricordare

- Logistic Regression → probabilità
- Naive Bayes → Teorema di Bayes
- SVM → margine massimo
- KNN → distanza
- Decision Tree → regole
- Random Forest → molti alberi
- Neural Networks → pesi + attivazioni + Gradient Descent

---

## MLOps in una pagina

Lifecycle

Business Problem
        │
        ▼
Data Collection
        │
        ▼
Preprocessing
        │
        ▼
Training
        │
        ▼
Evaluation
        │
        ▼
Deployment
        │
        ▼
Monitoring
        │
        ▼
Retraining

Strumenti principali

| Strumento | Scopo |
|---|---|
| Git | Versionamento |
| Docker | Containerizzazione |
| Kubernetes | Orchestrazione |
| FastAPI | Model Serving |
| Model Registry | Versioni dei modelli |
| Monitoring | Controllo prestazioni |

Ricorda:

- addestrare un modello non conclude il progetto;
- un modello va monitorato e aggiornato nel tempo.

---

## Formule essenziali

Logistic Regression

Sigmoide

σ(z)=1/(1+e^-z)

---

## Gradient Descent

w = w − α∇J(w)

---

## Naive Bayes

P(A|B)=P(B|A)P(A)/P(B)

---

## Gini

1 − Σ pi²

---

## Entropia

− Σ pi log₂(pi)

---

## Accuracy

(TP+TN)/(TP+TN+FP+FN)

---

## Precision

TP/(TP+FP)

---

## Recall

TP/(TP+FN)

---

## F1

2PR/(P+R)

---

## MAE

Media degli errori assoluti.

---

## RMSE

Radice quadrata del MSE.

---

## Errori classici

❌ Accuracy elevata ≠ modello buono.

❌ Dataset grande ≠ dati di qualità.

❌ Neural Network ≠ scelta migliore.

❌ Decision Tree senza controllo → overfitting.

❌ SVM senza scaling.

❌ KNN su dataset enormi.

❌ Addestrare e testare sugli stessi dati.

❌ Dimenticare il preprocessing.

---

## Flowchart rapido

Problema?
│
├── Testo
│       │
│       └── Naive Bayes
├── Dataset tabellare
│       │
│       └── Random Forest
├── Problema lineare
│       │
│       └── Logistic Regression
├── Pochi dati
│       │
│       └── SVM
├── Baseline semplice
│       │
│       └── KNN
└── Immagini / Audio / NLP
        │
        └── Neural Networks

---

## Le 50 cose da ricordare

Fondamenti

✓ Dataset

✓ Feature

✓ Target

✓ Classificazione

✓ Regressione

✓ Bias

✓ Variance

✓ Overfitting

✓ Underfitting

✓ Cross Validation

✓ Train/Test Split

---

## Algoritmi

✓ Logistic Regression → probabilità

✓ Naive Bayes → Bayes

✓ SVM → margine

✓ KNN → distanza

✓ Decision Tree → regole

✓ Random Forest → bagging

✓ Neural Networks → pesi

---

## Metriche

✓ Accuracy

✓ Precision

✓ Recall

✓ F1

✓ ROC

✓ AUC

✓ Confusion Matrix

✓ MAE

✓ RMSE

✓ R²

---

## MLOps

✓ Training

✓ Inference

✓ Deployment

✓ FastAPI

✓ Docker

✓ Kubernetes

✓ Monitoring

✓ Retraining

✓ Data Drift

✓ Concept Drift

---

## Checklist pre-esame (5 minuti)

Se riesci a spiegare senza appunti:

- cos’è il Machine Learning;
- differenza tra classificazione e regressione;
- overfitting e underfitting;
- Gradient Descent;
- Logistic Regression;
- Naive Bayes;
- SVM;
- KNN;
- Decision Tree;
- Random Forest;
- Neural Networks;
- Accuracy, Precision e Recall;
- il workflow MLOps;
- quando scegliere ciascun algoritmo;

allora hai consolidato gli argomenti principali del Master.

---

## Collegamenti rapidi

| Documento | Utilizzo |
|---|---|
| master-summary.md | Ripasso completo |
| comparison.md | Scelta dell’algoritmo |
| knowledge-graph.md | Collegamenti tra concetti |
| formulario.md | Formule |
| glossario.md | Definizioni |
| quiz-complete.md | Quiz a risposta multipla |
| deeptest-complete.md | Domande aperte |

---

## Stato editoriale

Stato: FINAL 1.0

Questo Cheat Sheet costituisce il riepilogo più sintetico del repository.

È progettato per essere consultato rapidamente prima di un esame, un colloquio tecnico o l’implementazione di un progetto di Machine Learning.

Per gli approfondimenti teorici e gli esempi pratici si rimanda ai singoli capitoli e alle appendici del repository.
