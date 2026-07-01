

# Support Vector Machines (SVM)

> Modulo: Machine Learning – Modelli e Algoritmi

---

## Obiettivo del capitolo

Le **Support Vector Machines (SVM)** sono algoritmi supervisionati utilizzati soprattutto per problemi di classificazione, ma estendibili anche alla regressione.

Nel percorso del Master le SVM rappresentano uno dei passaggi più importanti della parte sui modelli supervisionati, perché introducono tre concetti fondamentali:

1. la separazione delle classi tramite un iperpiano;
2. la massimizzazione del margine;
3. il **kernel trick**, che consente di trattare problemi non linearmente separabili.

L'idea centrale è costruire un confine decisionale che separi le classi nel modo più robusto possibile.

---

## Intuizione geometrica

Immaginiamo un dataset bidimensionale con due classi.

Se le classi sono separabili linearmente, esistono molte rette in grado di dividerle.

La domanda è:

> quale retta scegliamo?

Le SVM scelgono la retta che massimizza la distanza dai punti più vicini delle due classi.

Questa distanza prende il nome di **margine**.

La retta migliore non è quindi una retta qualsiasi, ma quella che lascia il maggiore spazio possibile tra sé e i punti più vicini.

In dimensioni superiori, la retta diventa un **iperpiano**.

---

## Iperpiano

Un iperpiano è la generalizzazione di una retta o di un piano in spazi con più dimensioni.

- In 2D: il separatore è una retta.
- In 3D: il separatore è un piano.
- In n dimensioni: il separatore è un iperpiano.

L'obiettivo della SVM è trovare l'iperpiano che separa le classi massimizzando il margine.

## Formula dell'iperpiano

Nel caso lineare, l'iperpiano può essere scritto come:

```text
w · x + b = 0
```

Dove:

- `w` è il vettore dei pesi;
- `x` è il vettore delle feature;
- `b` è il bias;
- il segno di `w · x + b` determina da quale lato dell'iperpiano si trova il punto.

In classificazione binaria, la decisione può essere vista come:

```text
classe = sign(w · x + b)
```

---

## Margine

Il **margine** è la distanza tra l'iperpiano decisionale e i punti più vicini delle classi.

Più il margine è ampio, più il modello è robusto rispetto a piccole variazioni dei dati.

Un margine ampio indica che il confine decisionale non è troppo vicino agli esempi di training, riducendo il rischio di overfitting.

## Margine e robustezza

Massimizzare il margine significa scegliere un confine decisionale che non sia fragile rispetto a piccole variazioni dei dati.

Due iperpiani possono separare correttamente il training set, ma quello con margine più ampio tende a generalizzare meglio perché lascia più spazio tra le classi.

---

## Support Vectors

I **support vectors** sono i punti del training set più vicini all'iperpiano.

Sono fondamentali perché determinano la posizione del confine decisionale.

Se si rimuovono punti lontani dal margine, l'iperpiano può rimanere invariato.

Se invece si rimuove o modifica un support vector, il confine può cambiare in modo significativo.

Questa caratteristica è stata evidenziata anche nella pratica del Master, dove si visualizzavano i support vectors tramite:

```python
model.support_vectors_
```

---

## Maximal Margin Classifier

Il **Maximal Margin Classifier** è il caso ideale in cui le classi sono perfettamente separabili linearmente.

In questo caso il classificatore cerca l'iperpiano che massimizza il margine senza permettere errori.

## Limite

Questo approccio è troppo rigido per dataset reali, perché:

- i dati possono contenere rumore;
- possono esserci outlier;
- le classi possono non essere perfettamente separabili.

Per questo motivo si introduce il concetto di **soft margin**.

---

## Support Vector Classifier e Soft Margin

Il **Support Vector Classifier (SVC)** generalizza il Maximal Margin Classifier introducendo un margine morbido.

Con il **soft margin**, il modello accetta che alcuni punti:

- cadano dentro il margine;
- siano classificati erroneamente.

Questa flessibilità permette una migliore generalizzazione.

Nel Master è stato sottolineato che il vantaggio principale del Support Vector Classifier rispetto al Maximal Margin Classifier è proprio la possibilità di tollerare errori e violazioni del margine.

---

## Parametro C

Il parametro `C` controlla il compromesso tra margine ampio ed errori di classificazione.

## C alto

Un valore alto di `C` penalizza molto gli errori.

Il modello cerca di classificare correttamente quasi tutti i punti, rischiando però di ottenere un margine più stretto e un maggiore overfitting.

## C basso

Un valore basso di `C` permette più errori.

Il margine tende ad essere più ampio e il modello può generalizzare meglio, ma rischia underfitting se è troppo permissivo.

## Interpretazione sintetica

| Valore di C | Effetto | Rischio |
|---|---|---|
| Alto | penalizza molto gli errori | overfitting |
| Basso | permette più violazioni del margine | underfitting |

`C` non indica direttamente la complessità del kernel, ma il grado di tolleranza verso errori e violazioni del margine.

---

## Problemi non linearmente separabili

Molti dataset reali non possono essere separati con una retta o un iperpiano nello spazio originale.

Un esempio classico è un dataset con classi distribuite in cerchi concentrici.

In due dimensioni non esiste una linea retta capace di separare le classi.

Tuttavia, se i dati vengono proiettati in uno spazio con dimensione maggiore, può diventare possibile separarli con un piano.

Questa idea porta al **kernel trick**.

---

## Kernel Trick

Il **kernel trick** consente alle SVM di lavorare come se i dati fossero stati trasformati in uno spazio ad alta dimensionalità, senza calcolare esplicitamente questa trasformazione.

Invece di trasformare direttamente i dati, il kernel calcola una misura di similarità tra punti nello spazio trasformato.

Questo riduce il costo computazionale e rende praticabile l'uso di trasformazioni non lineari.

Nel Master uno dei deeptest ricordava proprio questo punto:

> per ridurre il costo computazionale della proiezione in spazi ad alta dimensionalità si usa il kernel.

---

## Kernel principali

## Kernel lineare

Il kernel lineare è adatto quando le classi sono linearmente separabili o quasi linearmente separabili.

È il kernel più semplice e spesso rappresenta una buona baseline.

```python
from sklearn.svm import SVC

model = SVC(kernel="linear")
model.fit(X_train, y_train)
```

---

## Kernel polinomiale

Il kernel polinomiale consente di modellare relazioni non lineari introducendo combinazioni polinomiali delle feature.

È controllato principalmente dal grado del polinomio.

```python
model = SVC(kernel="poly", degree=3)
model.fit(X_train, y_train)
```

Un grado troppo alto può portare a overfitting.

---

## Kernel RBF

Il kernel **RBF (Radial Basis Function)** è uno dei kernel più usati nella pratica.

È molto efficace quando il confine decisionale è non lineare e complesso.

```python
model = SVC(kernel="rbf", gamma="scale")
model.fit(X_train, y_train)
```

Nel materiale pratico del Master, il kernel RBF risultava particolarmente efficace sui dataset sintetici con strutture circolari, come `make_circles`.

---

## Kernel sigmoidale

Il kernel sigmoidale è storicamente legato ad alcune analogie con le reti neurali, ma nella pratica moderna è meno usato rispetto a lineare, polinomiale e RBF.

```python
model = SVC(kernel="sigmoid")
model.fit(X_train, y_train)
```

---

## Parametro gamma

Il parametro `gamma` controlla l'influenza dei singoli punti nel kernel, soprattutto nel kernel RBF.

## Gamma basso

Un gamma basso produce un'influenza più ampia dei punti.

Il confine decisionale tende ad essere più liscio.

## Gamma alto

Un gamma alto rende l'influenza dei punti molto locale.

Il confine decisionale può diventare molto complesso, aumentando il rischio di overfitting.

Nel deeptest del Master, gamma veniva descritto come il parametro che controlla l'ampiezza o la portata dell'influenza del kernel.

## Interpretazione sintetica

| Valore di gamma | Effetto | Rischio |
|---|---|---|
| Basso | confine più liscio e globale | underfitting |
| Alto | confine molto locale e complesso | overfitting |

`gamma` è particolarmente importante con kernel RBF: valori troppo alti possono creare decision boundary molto frastagliati.

---

## SVC vs LinearSVC

Nel materiale pratico è stato confrontato `SVC(kernel="linear")` con `LinearSVC`.

## SVC

`SVC` è l'implementazione generale delle Support Vector Machines in scikit-learn.

Con kernel lineare permette di accedere ai support vectors:

```python
model = SVC(kernel="linear")
model.fit(X_train, y_train)

support_vectors = model.support_vectors_
```

## LinearSVC

`LinearSVC` è ottimizzato per il caso lineare, ma non espone direttamente l'attributo `support_vectors_`.

Questo punto è stato evidenziato nella pratica del Master come differenza importante tra le due implementazioni.

---

## Pratica del Master

La pratica sulle SVM ha utilizzato dataset sintetici generati con scikit-learn.

Dataset citati nel materiale consolidato:

- `make_blobs`;
- `make_classification`;
- `make_circles`.

L'obiettivo era visualizzare:

- il decision boundary;
- i margini;
- i support vectors;
- l'effetto dei kernel;
- il comportamento con outlier.

---

## Visualizzazione del decision boundary

Nelle esercitazioni è stata usata la visualizzazione del decision boundary per confrontare i diversi kernel.

Concettualmente:

```python
from sklearn.inspection import DecisionBoundaryDisplay

DecisionBoundaryDisplay.from_estimator(
    model,
    X,
    response_method="predict",
    cmap="coolwarm"
)
```

Per il margine si possono visualizzare i livelli:

```text
-1, 0, +1
```

Dove:

- `0` rappresenta il confine decisionale;
- `-1` e `+1` rappresentano i margini.

---

## Esempio con kernel lineare

```python
from sklearn.datasets import make_blobs
from sklearn.svm import SVC
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

X, y = make_blobs(
    n_samples=100,
    centers=2,
    random_state=0,
    cluster_std=1.2
)

X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=0
)

model = SVC(kernel="linear")
model.fit(X_train, y_train)

y_pred = model.predict(X_test)

print("Accuracy:", accuracy_score(y_test, y_pred))
print("Support vectors:", model.support_vectors_)
```

Questo esempio mostra il caso più semplice: separazione lineare tra due classi.

---

## Esempio con kernel RBF

```python
from sklearn.datasets import make_circles
from sklearn.svm import SVC
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

X, y = make_circles(
    n_samples=300,
    noise=0.1,
    factor=0.5,
    random_state=0
)

X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=0
)

model = SVC(kernel="rbf", gamma="scale")
model.fit(X_train, y_train)

y_pred = model.predict(X_test)

print("Accuracy:", accuracy_score(y_test, y_pred))
```

Nel caso di `make_circles`, il kernel lineare è inadatto, mentre il kernel RBF riesce a costruire un confine non lineare coerente con la struttura dei dati.

---

## Outlier e support vectors

Nel materiale pratico è stato osservato anche l'effetto degli outlier.

Sono stati considerati due approcci:

1. rimozione di un singolo outlier;
2. rimozione di outlier tramite z-score.

Takeaway importante:

> la rimozione di un outlier può non modificare l'iperpiano se quel punto non è un support vector determinante.

Questo rafforza l'idea che non tutti i punti hanno lo stesso ruolo nella SVM.

---

## Probabilità con SVC

Di default, `SVC` produce classi predette ma non probabilità.

Per abilitare le probabilità si usa:

```python
model = SVC(kernel="rbf", probability=True)
model.fit(X_train, y_train)

proba = model.predict_proba(X_test)
```

Nel materiale pratico questa opzione è stata usata anche per visualizzazioni con colormap probabilistiche.

---

## Hyperparameter tuning

Le prestazioni delle SVM dipendono molto dalla scelta degli iperparametri.

I parametri più importanti sono:

- `kernel`;
- `C`;
- `gamma`;
- `degree` per il kernel polinomiale.

Una strategia tipica consiste nell'usare una grid search con cross-validation.

```python
from sklearn.model_selection import GridSearchCV
from sklearn.pipeline import Pipeline
from sklearn.preprocessing import StandardScaler
from sklearn.svm import SVC

pipeline = Pipeline([
    ("scaler", StandardScaler()),
    ("model", SVC())
])

param_grid = {
    "model__kernel": ["linear", "rbf"],
    "model__C": [0.1, 1, 10],
    "model__gamma": ["scale", 0.1, 1]
}

grid = GridSearchCV(
    pipeline,
    param_grid=param_grid,
    cv=5,
    scoring="accuracy"
)

grid.fit(X_train, y_train)

print(grid.best_params_)
print(grid.best_score_)
```

Questa sezione è importante perché nella pratica raramente si sceglie il miglior kernel a priori: lo si confronta sperimentalmente.

---

## Complessità computazionale

Le SVM possono diventare costose su dataset molto grandi.

Il costo cresce soprattutto con:

- numero di campioni;
- numero di feature;
- tipo di kernel;
- ricerca degli iperparametri.

Le SVM con kernel non lineari sono spesso più costose delle versioni lineari.

Per dataset molto grandi, può essere preferibile usare `LinearSVC`, modelli lineari o metodi approssimati.

---

## Quando usare SVM

Le SVM sono utili quando:

- il dataset non è troppo grande;
- il numero di feature è elevato;
- si vogliono provare separazioni non lineari tramite kernel;
- serve un modello robusto per classificazione supervisionata;
- si vuole lavorare con margini e support vectors.

---

## Quando evitare SVM

Le SVM possono non essere la scelta migliore quando:

- il dataset è molto grande;
- serve un modello facilmente interpretabile;
- il training deve essere estremamente rapido;
- il tuning degli iperparametri è troppo costoso;
- si vogliono probabilità ben calibrate senza passaggi aggiuntivi.

---

## Vantaggi

- efficaci in spazi ad alta dimensionalità;
- flessibili grazie ai kernel;
- robuste quando il margine è ben definito;
- utilizzano solo un sottoinsieme di punti critici (support vectors);
- adatte a classificazione lineare e non lineare.

---

## Svantaggi

- costo computazionale elevato su dataset grandi;
- scelta del kernel non sempre immediata;
- sensibilità a `C` e `gamma`;
- richiedono spesso scaling delle feature;
- interpretabilità limitata rispetto a modelli lineari semplici o alberi decisionali.

---

## Preprocessing e scaling

Le SVM sono sensibili alla scala delle feature.

Se una feature ha valori molto più grandi delle altre, può dominare il calcolo del margine e della distanza.

Per questo motivo è buona pratica applicare standardizzazione o normalizzazione.

```python
from sklearn.preprocessing import StandardScaler
from sklearn.pipeline import Pipeline
from sklearn.svm import SVC

pipeline = Pipeline([
    ("scaler", StandardScaler()),
    ("model", SVC(kernel="rbf"))
])

pipeline.fit(X_train, y_train)
```

---

## Confronto con altri algoritmi

## SVM vs Logistic Regression

La regressione logistica è un modello lineare probabilistico.

La SVM cerca invece un iperpiano che massimizza il margine.

Con kernel non lineari, la SVM può modellare confini più complessi.

## SVM vs Naive Bayes

Naive Bayes è probabilistico e si basa su ipotesi di indipendenza tra feature.

SVM è geometrico e lavora sulla separazione tramite margine.

## SVM vs KNN

KNN è lazy e non parametrico: classifica in base ai vicini.

SVM apprende un confine decisionale durante il training.

## SVM vs Decision Tree

Gli alberi decisionali sono più interpretabili.

Le SVM possono essere più efficaci in spazi ad alta dimensionalità, ma risultano meno intuitive da spiegare.

---

## Errori comuni

## Non scalare le feature

Le SVM richiedono spesso scaling. Dimenticare questo passaggio può peggiorare molto le prestazioni.

## Usare sempre RBF senza baseline

Il kernel RBF è potente, ma è buona pratica provare prima un kernel lineare come baseline.

## Confondere C e gamma

`C` controlla la penalizzazione degli errori.

`gamma` controlla l'influenza locale dei punti nel kernel RBF.

## Interpretare tutti i punti come ugualmente importanti

Nelle SVM i punti più importanti sono i support vectors, non tutti i punti del dataset.

## Usare probabilità senza abilitarle

`SVC` non restituisce probabilità con `predict_proba()` se non viene inizializzato con:

```python
SVC(probability=True)
```

Questo passaggio aumenta il costo computazionale, quindi va abilitato solo quando serve davvero.

## Non usare cross-validation

Scegliere `C`, `gamma` e `kernel` guardando solo un singolo train/test split può portare a conclusioni instabili.

Per il tuning è preferibile usare cross-validation.

---

## Quiz di ripasso

## Domanda 1

Qual è l'obiettivo principale di una SVM?

**Risposta:** trovare un iperpiano che separi le classi massimizzando il margine.

## Domanda 2

Cosa sono i support vectors?

**Risposta:** i punti più vicini all'iperpiano, che determinano il margine e il confine decisionale.

## Domanda 3

A cosa serve il kernel trick?

**Risposta:** a lavorare implicitamente in spazi trasformati ad alta dimensionalità senza calcolare esplicitamente la trasformazione.

## Domanda 4

Quale kernel è adatto a dati linearmente separabili?

**Risposta:** il kernel lineare.

## Domanda 5

Quale kernel è spesso efficace su dati non lineari come cerchi concentrici?

**Risposta:** il kernel RBF.


## Domanda 6

Che cosa controlla il parametro `C`?

**Risposta:** controlla quanto il modello penalizza errori e violazioni del margine.

## Domanda 7

Che cosa controlla il parametro `gamma` nel kernel RBF?

**Risposta:** controlla quanto è locale l'influenza dei punti nel calcolo del kernel.

## Domanda 8

Perché le SVM richiedono spesso feature scaling?

**Risposta:** perché margini e distanze sono influenzati dalla scala delle feature.

---

## Deeptest

## Domanda 1

Quando si proiettano dati non linearmente separabili da 2D a 3D, cosa può accadere?

**Risposta:** i dati possono diventare separabili tramite un piano nello spazio trasformato.

## Domanda 2

Come si riduce il costo computazionale della trasformazione esplicita in spazi ad alta dimensionalità?

**Risposta:** usando il kernel trick.

## Domanda 3

Qual è la funzione del kernel?

**Risposta:** calcolare una similarità equivalente alla trasformazione non lineare in uno spazio più elevato.

## Domanda 4

Qual è il vantaggio del Support Vector Classifier rispetto al Maximal Margin Classifier?

**Risposta:** accetta errori nei margini tramite soft margin.

## Domanda 5

Come avviene l'addestramento di una SVM?

**Risposta:** tramite ottimizzazione matematica avanzata.

## Domanda 6

Qual è l'obiettivo di una SVM?

**Risposta:** massimizzare la distanza tra le classi.

## Domanda 7

Quale kernel è utile per dati linearmente separabili?

**Risposta:** il kernel lineare.

## Domanda 8

Che ruolo ha gamma?

**Risposta:** controlla l'ampiezza o la portata dell'influenza del kernel.


## Domanda 9

Un valore molto alto di `C` può portare a:

- A. maggiore tolleranza agli errori;
- B. overfitting;
- C. eliminazione dei support vectors;
- D. impossibilità di usare kernel.

**Risposta corretta:** B.

## Domanda 10

Con kernel RBF, un valore molto alto di `gamma` tende a produrre:

- A. un confine molto liscio;
- B. un confine molto locale e complesso;
- C. un modello equivalente a Naive Bayes;
- D. una regressione lineare.

**Risposta corretta:** B.

## Domanda 11

Perché si usa spesso una pipeline con `StandardScaler` e `SVC`?

- A. perché SVC richiede immagini normalizzate;
- B. perché lo scaling evita che feature con scale diverse dominino margini e distanze;
- C. perché StandardScaler crea automaticamente nuovi kernel;
- D. perché elimina la necessità di train/test split.

**Risposta corretta:** B.

---

## Da ricordare per l'esame

- Le SVM cercano un iperpiano di separazione.
- L'iperpiano scelto è quello che massimizza il margine.
- I support vectors sono i punti che determinano il margine.
- Il Maximal Margin Classifier funziona solo con dati perfettamente separabili.
- Il Support Vector Classifier usa soft margin e tollera errori.
- Il kernel trick consente separazioni non lineari efficienti.
- Kernel principali: lineare, polinomiale, RBF, sigmoidale.
- `C` controlla la penalizzazione degli errori.
- `gamma` controlla l'influenza dei punti nei kernel come RBF.
- Le SVM richiedono spesso scaling delle feature.

---

## Insight maturati durante il Master

Le SVM sono uno dei modelli più importanti per comprendere il passaggio da separazioni lineari a separazioni non lineari.

Il concetto chiave non è semplicemente "separare le classi", ma separarle con il margine massimo possibile.

Il kernel trick è uno dei passaggi teorici più rilevanti: permette di ottenere modelli non lineari senza dover calcolare esplicitamente nuove feature in spazi di dimensione elevata.

Nella pratica, la scelta del kernel e degli iperparametri deve essere fatta con validazione, perché non esiste un kernel universalmente migliore.

---

## Checklist finale di padronanza

Alla fine di questo capitolo dovresti saper spiegare:

- che cosa sono iperpiano, margine e support vectors;
- perché la SVM massimizza il margine;
- differenza tra Maximal Margin Classifier e Support Vector Classifier;
- significato del soft margin;
- ruolo del parametro `C`;
- ruolo del parametro `gamma`;
- che cos'è il kernel trick;
- differenza tra kernel lineare, polinomiale, RBF e sigmoidale;
- perché lo scaling è importante;
- differenza tra `SVC(kernel="linear")` e `LinearSVC`;
- quando usare o evitare una SVM.

---

## Collegamenti consigliati

Per consolidare le SVM, è utile confrontarle con:

- **Naive Bayes**, classificatore probabilistico;
- **Logistic Regression**, modello lineare discriminativo;
- **Nearest Neighbors**, modello basato su distanza;
- **Neural Networks**, modello non lineare appreso tramite gradient descent;
- **Decision Tree / Random Forest**, modelli basati su regole ed ensemble.

---

## Stato del recupero

| Sezione | Stato |
|---|:---:|
| Teoria | Completa |
| Kernel | Completi |
| Pratica Python | Aggiunta |
| Hyperparameter tuning | Aggiunto |
| Complessità computazionale | Aggiunta |
| Checklist finale | Aggiunta |
| Support vectors | Aggiunti |
| Outlier | Aggiunti |
| Quiz | Aggiunti |
| Deeptest | Aggiunti |
| Errori comuni | Aggiunti |
| Collegamenti | Aggiunti |

**Recovery score stimato:** 99%.

Il contenuto copre la teoria, la pratica e i deeptest consolidati nel materiale del Master. Potrebbero mancare dettagli minori presenti solo in conversazioni non più accessibili integralmente.

---

## Stato editoriale

**Stato:** FINAL 1.0

Il capitolo è considerato chiuso in prima versione definitiva. Eventuali interventi futuri dovrebbero essere solo correzioni puntuali, integrazioni da materiale originale aggiuntivo o aggiornamenti di stile globali del repository.
