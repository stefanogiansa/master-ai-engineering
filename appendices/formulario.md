# Formulario di Machine Learning

## Appendice – Formulario

---

## Obiettivo dell’appendice

Questa appendice raccoglie tutte le principali formule matematiche utilizzate durante il percorso del Master AI Engineering.

A differenza di un semplice formulario, ogni formula è accompagnata da:

- definizione;
- interpretazione;
- ambiti di utilizzo;
- capitolo di riferimento.

L’obiettivo è fornire uno strumento di consultazione rapida durante il ripasso e la preparazione all’esame.

---

## Convenzioni matematiche

Nel seguito verranno utilizzati i simboli riportati nella tabella seguente.

| Simbolo | Significato |
|---|---|
| x | Feature (variabile di input) |
| y | Valore reale (target) |
| ŷ | Valore predetto dal modello |
| w | Vettore dei pesi |
| b | Bias (intercetta) |
| p | Probabilità |
| n | Numero di osservazioni |
| α | Learning Rate |
| J | Funzione di costo |
| σ | Funzione sigmoide |
| Σ | Operatore di sommatoria |
| ∇ | Gradiente |

---

## Probabilità

La teoria della probabilità costituisce la base matematica di numerosi algoritmi di Machine Learning, in particolare di Naive Bayes e di tutti i modelli probabilistici.

---

### Probabilità di un evento

#### Formula

P(A)

#### Significato

Indica la probabilità che si verifichi l’evento A.

Il valore è sempre compreso tra:

0 ≤ P(A) ≤ 1

#### Utilizzo

- Modelli probabilistici
- Naive Bayes
- Inferenza statistica

#### Capitolo

→ naive-bayes.md

---

### Probabilità complementare

#### Formula

P(Aᶜ) = 1 − P(A)

#### Significato

Rappresenta la probabilità che A non si verifichi.

#### Proprietà

P(A) + P(Aᶜ) = 1

#### Capitolo

→ naive-bayes.md

---

### Probabilità condizionata

#### Formula

          P(A ∩ B)
P(A|B) = ----------
P(B)

#### Significato

Rappresenta la probabilità che si verifichi A, sapendo che l’evento B è già avvenuto.

La probabilità cambia perché l’informazione disponibile è maggiore.

#### Utilizzo

- Machine Learning probabilistico
- Diagnosi medica
- Sistemi di raccomandazione

#### Capitolo

→ naive-bayes.md

---

### Eventi indipendenti

#### Formula

P(A ∩ B) = P(A) · P(B)

#### Significato

Due eventi sono indipendenti se il verificarsi dell’uno non modifica la probabilità dell’altro.

#### Utilizzo

Questa proprietà rappresenta l’ipotesi fondamentale del classificatore Naive Bayes.

---

### Teorema di Bayes

#### Formula

             P(B|A) · P(A)
P(A|B) = ------------------------
P(B)

#### Significato

Il Teorema di Bayes permette di aggiornare una probabilità iniziale (prior) utilizzando una nuova evidenza.

Il risultato prende il nome di probabilità a posteriori (posterior).

---

#### Componenti

| Termine | Significato |
|---|---|
| P(A) | Prior |
| P(B\|A) | Likelihood |
| P(B) | Evidence |
| P(A\|B) | Posterior |

---

#### Utilizzo

Il Teorema di Bayes viene utilizzato in:

- Naive Bayes;
- classificazione di documenti;
- spam detection;
- diagnosi mediche;
- sistemi esperti.

---

#### Capitolo

→ naive-bayes.md

---

## Statistica descrittiva

Prima di addestrare un modello è fondamentale comprendere la distribuzione dei dati.

---

### Media aritmetica

#### Formula

          Σ xi
μ = -------------
            n

#### Significato

La media rappresenta il valore centrale di un insieme di osservazioni.

#### Utilizzo

- Analisi esplorativa dei dati
- Standardizzazione
- Statistica descrittiva

---

### Varianza

#### Formula

σ² =
Σ (xi − μ)²
-----------
     n

#### Significato

Misura quanto i dati siano dispersi rispetto alla media.

Una varianza elevata indica dati molto distribuiti.

---

### Deviazione standard

#### Formula

σ = √σ²

#### Significato

È la radice quadrata della varianza.

Ha la stessa unità di misura dei dati originali ed è più facilmente interpretabile.

---

### Z-Score

#### Formula

        x − μ
z = -------------
           σ

#### Significato

Indica di quante deviazioni standard un valore si discosta dalla media.

È la base della Standardizzazione utilizzata in molti algoritmi di Machine Learning.

#### Capitoli

→ fondamenti-machine-learning.md

→ logistic-regression.md

→ svm.md

→ nearest-neighbors.md

---

### Min-Max Scaling

#### Formula

        x − xmin
x' = -------------------
      xmax − xmin

#### Significato

Trasforma ogni feature nell’intervallo:

[0,1]

#### Utilizzo

Molto utilizzato nelle reti neurali e negli algoritmi sensibili alla scala delle feature.

---

### Standardizzazione

#### Formula

        x − μ
x' = ------------
          σ

#### Significato

Trasforma ogni feature in modo da avere:

- media uguale a 0;
- deviazione standard uguale a 1.

È il metodo di scaling più utilizzato nel Machine Learning.

---

## Note d’esame

Per il Master è importante ricordare che:

- la probabilità condizionata è alla base di Naive Bayes;
- il Teorema di Bayes aggiorna una probabilità alla luce di nuove evidenze;
- la standardizzazione e il Min-Max Scaling sono tecniche di preprocessing differenti;
- media, varianza e deviazione standard sono strumenti fondamentali per comprendere un dataset prima dell’addestramento di un modello.

---

## Gradient Descent

Il Gradient Descent è l’algoritmo di ottimizzazione più utilizzato nel Machine Learning.

Il suo obiettivo consiste nel minimizzare la funzione di costo aggiornando iterativamente i parametri del modello.

---

### Funzione di costo

#### Formula

J(w)

#### Significato

La funzione di costo misura quanto le predizioni del modello siano lontane dai valori reali.

L’obiettivo dell’addestramento consiste nel trovare il valore dei parametri che minimizza questa funzione.

#### Utilizzo

- Regressione Lineare
- Logistic Regression
- Neural Networks

#### Capitoli

→ gradient-descent.md

→ logistic-regression.md

→ neural-networks.md

---

### Gradiente

#### Formula

∇J(w)

#### Significato

Il gradiente indica la direzione di massima crescita della funzione di costo.

Per minimizzare la funzione è necessario muoversi nella direzione opposta.

---

### Aggiornamento dei pesi

#### Formula

w := w − α · ∇J(w)

#### Significato

Ad ogni iterazione i pesi vengono modificati nella direzione che riduce maggiormente l’errore.

---

### Learning Rate

#### Formula

α

#### Significato

Il Learning Rate controlla la dimensione del passo effettuato durante ogni aggiornamento.

| Valore | Effetto |
|---|---|
| Troppo piccolo | Convergenza molto lenta |
| Adeguato | Convergenza stabile |
| Troppo grande | Possibile divergenza |

---

## Logistic Regression

La Logistic Regression utilizza una funzione logistica per trasformare una combinazione lineare in una probabilità.

---

### Combinazione lineare

#### Formula

z = w · x + b

#### Significato

È il risultato della combinazione tra feature, pesi e bias.

Da solo non rappresenta una probabilità.

---

### Funzione Sigmoide

#### Formula

          1
σ(z) = ----------
        1 + e⁻ᶻ

#### Significato

Trasforma qualsiasi numero reale in una probabilità compresa tra 0 e 1.

---

#### Proprietà

- continua;
- derivabile;
- monotona crescente;
- output nell’intervallo [0,1].

---

### Odds

#### Formula

odds =
p
-------
1 − p

#### Significato

Rappresenta il rapporto tra la probabilità che un evento avvenga e quella che non avvenga.

---

### Logit

#### Formula

        p
log ----------
      1 − p

#### Significato

La Logistic Regression assume che il logaritmo degli odds sia una funzione lineare delle feature.

---

### Decision Boundary

#### Formula

w · x + b = 0

#### Significato

Rappresenta il confine che separa le due classi.

Per una Logistic Regression binaria la soglia corrisponde normalmente a:

p = 0.5

---

## Funzioni di Loss

Le funzioni di loss misurano la distanza tra il valore previsto dal modello e quello reale.

L’obiettivo dell’addestramento consiste nel minimizzare tali funzioni.

---

### Mean Squared Error (MSE)

#### Formula

          1
MSE = --------
         n
      Σ (yi − ŷi)²

#### Utilizzo

- Regressione Lineare
- Problemi di regressione

---

### Binary Cross Entropy

#### Formula

Loss =
− [ y log(p)
+ (1−y) log(1−p) ]

#### Significato

È la funzione di costo utilizzata dalla Logistic Regression.

Penalizza fortemente le previsioni molto sicure ma errate.

---

### Cross Entropy Multiclasse

#### Formula

Loss =
− Σ yi log(pi)

#### Utilizzo

- Neural Networks
- Classificazione multiclasse

---

## Neural Networks

Le reti neurali utilizzano funzioni di attivazione per introdurre non linearità.

---

### ReLU

#### Formula

ReLU(x) =
max(0,x)

#### Proprietà

- molto veloce;
- evita il problema del vanishing gradient;
- è la funzione più utilizzata nelle reti profonde.

---

### Sigmoid

#### Formula

σ(x)=
1
----------
1+e⁻ˣ

#### Utilizzo

- output binario;
- Logistic Regression;
- reti neurali poco profonde.

---

### Tanh

#### Formula

          eˣ − e⁻ˣ
tanh(x)=--------------
          eˣ + e⁻ˣ

#### Proprietà

Restituisce valori compresi tra:

[-1,1]

---

### Softmax

#### Formula

           e^zi
Softmax =
         ----------
          Σ e^zj

#### Significato

Converte i punteggi prodotti dalla rete neurale in una distribuzione di probabilità.

La somma delle probabilità è sempre uguale a:

1

---

## Collegamenti

Le formule presentate in questa sezione vengono approfondite nei capitoli:

- gradient-descent.md
- logistic-regression.md
- neural-networks.md

---

## Note d’esame

È importante ricordare che:

- il Gradient Descent ottimizza i parametri del modello;
- la Sigmoide trasforma valori reali in probabilità;
- la Binary Cross Entropy è la loss della Logistic Regression;
- la Softmax viene utilizzata nei problemi di classificazione multiclasse;
- ReLU è la funzione di attivazione più diffusa nelle reti neurali moderne.

---

## Naive Bayes

Il classificatore Naive Bayes è un algoritmo probabilistico basato sul Teorema di Bayes e sull’ipotesi di indipendenza condizionata tra le feature.

---

### Formula di classificazione

#### Formula

                    P(y) · Π P(xi | y)
P(y | x) = -------------------------------
P(x)

#### Significato

La probabilità che un’osservazione appartenga alla classe y è proporzionale alla probabilità a priori della classe moltiplicata per la probabilità di osservare tutte le feature appartenendo a quella classe.

Poiché P(x) è costante per tutte le classi, durante la classificazione viene normalmente omessa.

---

### Regola decisionale

#### Formula

ŷ = argmax P(y | x)

#### Significato

Il modello assegna il campione alla classe con probabilità a posteriori maggiore.

---

### Ipotesi Naive

#### Formula

P(x1,x2,...,xn | y)
=
Π P(xi | y)

#### Significato

Si assume che tutte le feature siano indipendenti una volta nota la classe.

Questa ipotesi è raramente vera nella realtà, ma rende l’algoritmo estremamente efficiente.

---

#### Capitolo

→ naive-bayes.md

---

## Support Vector Machine (SVM)

L’obiettivo di una Support Vector Machine è trovare l’iperpiano che massimizza il margine tra le classi.

---

### Iperpiano

#### Formula

w · x + b = 0

#### Significato

Rappresenta la superficie di separazione tra le classi.

---

### Regola di classificazione

#### Formula

classe = sign(w · x + b)

#### Significato

Il segno della funzione decisionale determina la classe prevista.

---

### Margine

#### Formula

```text
Margine =
2
-------
||w||
```

#### Significato

Più il margine è grande, migliore è generalmente la capacità di generalizzazione del modello.

---

### Funzione di ottimizzazione (Soft Margin)

#### Formula

min
½ ||w||²
+
C Σ ξi

#### Significato

La funzione obiettivo cerca un compromesso tra:

- massimizzazione del margine;
- penalizzazione degli errori.

---

### Parametro C

#### Formula

C

#### Significato

Controlla il compromesso tra:

- ampiezza del margine;
- numero di errori consentiti.

| Valore di C | Effetto |
|---|---|
| piccolo | margine più ampio, maggiore tolleranza agli errori |
| grande | margine più stretto, minori errori sul training set |

---

### Kernel Trick

#### Formula

K(xi,xj)

#### Significato

Permette di trasformare implicitamente i dati in uno spazio a dimensionalità superiore senza calcolare esplicitamente la trasformazione.

Kernel comuni:

- Lineare
- Polinomiale
- RBF (Gaussian)
- Sigmoid

---

#### Capitolo

→ svm.md

---

## Decision Tree

Gli alberi decisionali suddividono ricorsivamente il dataset scegliendo, ad ogni nodo, la feature che massimizza la separazione tra le classi.

---

### Gini Impurity

#### Formula

## Gini
=
1 − Σ pi²

### Significato

Misura quanto un nodo sia “impuro”.

Valori:

| Gini | Interpretazione |
|---|---|
| 0 | nodo puro |
| vicino a 0 | buona separazione |
| elevato | classi molto mescolate |

---

### Entropia

#### Formula

## Entropy
=
− Σ pi log₂(pi)

### Significato

Misura il livello di disordine presente in un nodo.

Maggiore è l’entropia, maggiore è l’incertezza.

---

### Information Gain

#### Formula

## IG
=
## Entropy(parent)
−
Σ
(weighti × Entropy(childi))

### Significato

Misura quanto una suddivisione riduca l’incertezza.

L’albero seleziona normalmente la feature che produce l’Information Gain maggiore.

---

#### Capitolo

→ decision-tree-random-forest.md

---

## Random Forest

La Random Forest combina numerosi alberi decisionali.

La previsione finale deriva dall’aggregazione delle predizioni dei singoli alberi.

---

### Classificazione

#### Formula

ŷ
=
### Majority Vote

#### Significato

Ogni albero vota una classe.

La previsione finale corrisponde alla classe con il maggior numero di voti.

---

### Regressione

#### Formula

ŷ
=
1
───
T
Σ ŷi

dove:

- T rappresenta il numero di alberi.

#### Significato

Per problemi di regressione la Random Forest restituisce la media delle predizioni.

---

### Bagging

#### Formula

## Training Set
↓
## Bootstrap Sampling
↓
## Tree 1
## Tree 2
...
## Tree N
↓
### Aggregazione

#### Significato

Ogni albero viene addestrato su un diverso campione bootstrap del dataset.

---

### Out Of Bag Error (OOB)

#### Formula

### OOB Error

#### Significato

Errore stimato utilizzando i campioni non selezionati durante il bootstrap.

Permette di valutare il modello senza costruire un validation set separato.

---

#### Capitolo

→ decision-tree-random-forest.md

---

## K-Nearest Neighbors (KNN)

KNN è un algoritmo basato sulla distanza.

La classificazione dipende dai K vicini più prossimi.

---

### Distanza Euclidea

#### Formula

d(x,y)
=
√ Σ (xi − yi)²

#### Significato

È la misura di distanza più utilizzata in KNN.

---

### Distanza Manhattan

#### Formula

d(x,y)
=
Σ |xi − yi|

#### Significato

Somma delle differenze assolute.

È meno sensibile agli outlier rispetto alla distanza euclidea.

---

### Predizione

#### Formula

ŷ
=
### Majority Vote

#### Significato

La classe viene determinata dalla maggioranza dei K vicini.

---

### Parametro K

#### Formula

K

#### Significato

Determina il numero di vicini utilizzati.

| Valore di K | Effetto |
|---|---|
| piccolo | modello più sensibile al rumore |
| grande | modello più stabile ma meno flessibile |

---

#### Capitolo

→ nearest-neighbors.md

---

## Note d’esame

Per gli algoritmi studiati è importante ricordare che:

- Naive Bayes utilizza il Teorema di Bayes e l’ipotesi di indipendenza delle feature.
- SVM cerca l’iperpiano con margine massimo.
- Decision Tree utilizza Gini o Entropia per scegliere gli split.
- Random Forest riduce l’overfitting combinando molti alberi.
- KNN è un algoritmo lazy basato sulla distanza tra osservazioni.

---

## Metriche di classificazione

Le metriche di classificazione permettono di valutare le prestazioni di un modello su problemi di classificazione binaria o multiclasse.

---

## Matrice di Confusione (Confusion Matrix)

La Confusion Matrix riassume il numero di predizioni corrette e errate.

## Classe Reale
## Positiva   Negativa
## Pred Positiva      TP         FP
## Pred Negativa      FN         TN

Dove:

| Simbolo | Significato |
|---|---|
| TP | True Positive |
| TN | True Negative |
| FP | False Positive |
| FN | False Negative |

---

### Accuracy

#### Formula

              TP + TN
Accuracy = -------------------
            TP+TN+FP+FN

#### Significato

Misura la percentuale di classificazioni corrette.

## Limite

Può essere fuorviante in presenza di dataset sbilanciati.

---

### Precision

#### Formula

## TP
Precision = -------
            TP+FP

### Significato

Risponde alla domanda:

Tra tutte le osservazioni classificate come positive, quante erano realmente positive?

---

### Recall

#### Formula

## TP
Recall = -------
         TP+FN

### Significato

Risponde alla domanda:

Tra tutte le osservazioni realmente positive, quante sono state individuate?

---

### F1-Score

#### Formula

             2 · Precision · Recall
F1 = -----------------------------------------
          Precision + Recall

#### Significato

Media armonica tra Precision e Recall.

È molto utilizzata nei problemi con classi sbilanciate.

---

## ROC Curve

La ROC Curve rappresenta il compromesso tra:

- True Positive Rate;
- False Positive Rate.

Un classificatore perfetto passa vicino all’angolo superiore sinistro del grafico.

---

### Area Under the Curve (AUC)

#### Formula

### AUC

#### Significato

L’Area Under the ROC Curve sintetizza la qualità complessiva del classificatore.

| Valore | Interpretazione |
|---|---|
| 0.50 | classificatore casuale |
| 0.70 | discreto |
| 0.80 | buono |
| 0.90 | ottimo |
| 1.00 | perfetto |

---

## Metriche di regressione

---

### Mean Absolute Error (MAE)

#### Formula

          1
MAE = --------
         n
      Σ |yi − ŷi|

#### Significato

Media degli errori assoluti.

È facilmente interpretabile perché mantiene la stessa unità di misura del problema.

---

### Mean Squared Error (MSE)

#### Formula

          1
MSE = --------
         n
      Σ (yi − ŷi)²

#### Significato

Penalizza maggiormente gli errori elevati.

---

### Root Mean Squared Error (RMSE)

#### Formula

RMSE = √MSE

#### Significato

Riporta l’errore nella stessa unità di misura del target.

---

Coefficiente di determinazione (R²)

#### Formula

## SSres
R² = 1 − -----------
### SStot

#### Significato

Misura la capacità del modello di spiegare la variabilità dei dati.

| Valore | Interpretazione |
|---|---|
| 1 | modello perfetto |
| 0 | equivalente alla media |
| <0 | peggiore della media |

---

## Bias–Variance Tradeoff

Uno dei principi fondamentali del Machine Learning consiste nel trovare un equilibrio tra bias e variance.

### Formula

## Errore Totale
=
Bias²
+
## Variance
+
### Rumore

#### Significato

- Bias elevato → Underfitting.
- Variance elevata → Overfitting.
- L’obiettivo è trovare il miglior compromesso.

---

## Mappa delle formule per capitolo

| Capitolo | Formule principali |
|---|---|
| Fondamenti | Media, Varianza, Deviazione Standard, Z-Score, Accuracy, Precision, Recall, F1, MAE, RMSE |
| Gradient Descent | Gradiente, Learning Rate, Aggiornamento dei pesi |
| Logistic Regression | Sigmoide, Odds, Logit, Binary Cross Entropy |
| Naive Bayes | Bayes, Probabilità Condizionata |
| SVM | Iperpiano, Margine, Kernel |
| Nearest Neighbors | Distanza Euclidea, Manhattan |
| Decision Tree | Entropia, Gini, Information Gain |
| Neural Networks | ReLU, Tanh, Softmax, Cross Entropy |

---

## Checklist finale

Al termine di questa appendice dovresti ricordare:

- le principali formule di probabilità;
- il Teorema di Bayes;
- il funzionamento del Gradient Descent;
- la funzione Sigmoide;
- la Binary Cross Entropy;
- le formule di SVM;
- Gini ed Entropia;
- le distanze utilizzate in KNN;
- le funzioni di attivazione delle reti neurali;
- le principali metriche di classificazione;
- le metriche di regressione;
- il Bias–Variance Tradeoff.

---

## Come utilizzare questo formulario

Questa appendice non sostituisce lo studio teorico dei capitoli.

È consigliabile utilizzarla:

- durante il ripasso;
- prima delle esercitazioni;
- durante la preparazione all’esame;
- come riferimento rapido mentre si implementano gli algoritmi.

Ogni formula rimanda al relativo capitolo, nel quale viene spiegata nel dettaglio con esempi e codice.

---

## Stato editoriale

Stato: FINAL 1.0

Questa appendice raccoglie le principali formule matematiche utilizzate durante il Master AI Engineering.

Le formule sono organizzate per argomento e collegate ai capitoli del repository, costituendo un riferimento rapido per lo studio e il ripasso.

Eventuali aggiornamenti futuri riguarderanno esclusivamente l’aggiunta di nuove formule provenienti dal materiale originale del Master o il miglioramento della formattazione.
