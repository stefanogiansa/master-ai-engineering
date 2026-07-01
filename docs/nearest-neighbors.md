# Nearest Neighbors (KNN e Radius Nearest Neighbors)

> Modulo: Machine Learning – Modelli e Algoritmi

---

## Introduzione
L’algoritmo dei Nearest Neighbors (KNN) è una delle tecniche di machine learning più intuitive e utilizzate per problemi di classificazione e regressione. Si basa sull’idea che punti simili nello spazio delle feature abbiano etichette simili. In questa sezione approfondiremo il funzionamento di KNN e della sua variante Radius Nearest Neighbors (RNN), analizzeremo i principali parametri, i vantaggi/svantaggi, e vedremo esempi pratici con Python.

---

## Lazy Learning e Modelli Non Parametrici
KNN è un esempio di **modello di apprendimento pigro (lazy learning)**. Significa che:
- **Non costruisce un modello esplicito durante la fase di addestramento.**
- **Memorizza semplicemente i dati di training.**
- La computazione avviene tutta in fase di predizione, cercando i vicini più prossimi rispetto al punto di test.

Inoltre, KNN è un **modello non parametrico**:
- **Non assume una forma funzionale specifica dei dati.**
- Non apprende parametri interni, ma basa le predizioni sulle relazioni locali nei dati.

---

## Metriche di Distanza
Il cuore di KNN è la misura di similarità tra punti, tipicamente una **distanza** nello spazio delle feature. Le principali metriche sono:

- **Distanza Euclidea** (Minkowski con p=2):
  $$
  d_{eucl}(x, y) = \sqrt{\sum_{i=1}^n (x_i - y_i)^2}
  $$
- **Distanza di Manhattan** (Minkowski con p=1):
  $$
  d_{man}(x, y) = \sum_{i=1}^n |x_i - y_i|
  $$
- **Distanza di Minkowski**:
  $$
  d_{mink}(x, y) = \left( \sum_{i=1}^n |x_i - y_i|^p \right)^{1/p}
  $$
  - Se $p=1$: Manhattan
  - Se $p=2$: Euclidea

La scelta della metrica può influenzare molto le prestazioni del modello.

---

## Algoritmo KNN in Dettaglio
**K-Nearest Neighbors (KNN)** predice l’etichetta di un nuovo punto in base alle etichette dei suoi $K$ vicini più prossimi nel training set.

**Algoritmo:**
1. Scegli il numero $K$ di vicini.
2. Per ogni punto di test:
   - Calcola la distanza da tutti i punti di training.
   - Seleziona i $K$ punti più vicini.
   - Per classificazione: predici la classe più frequente tra i vicini (voto di maggioranza).
   - Per regressione: calcola la media dei valori target dei vicini.

**Nota:** Esistono varianti che pesano i vicini in base alla distanza (vicini più vicini contano di più).

---

## Scelta di $K$
- **$K$ piccolo (es. $K=1$):** modello molto flessibile, rischia di sovradattare (overfitting).
- **$K$ grande:** modello più rigido, può sottostimare la complessità dei dati (underfitting).
- **Scelta tipica:** si usa la cross-validation per trovare il valore ottimale.
  - $K$ deve essere dispari in classificazione binaria per evitare pareggi.

---

## Overfitting e Underfitting
- **Overfitting:** per $K$ troppo basso, il modello si adatta anche al rumore del training set (ad esempio $K=1$ memorizza tutto).
- **Underfitting:** per $K$ troppo alto, il modello ignora le strutture locali e diventa troppo semplice.

---

## Radius Nearest Neighbors (RNN)
**Radius Nearest Neighbors** è una variante di KNN:
- Invece di fissare $K$, si fissa un **raggio $r$**.
- Si considerano tutti i punti di training entro la distanza $r$ dal punto di test.
- La predizione si basa sulle etichette di questi punti (voto di maggioranza o media).
- Se nessun vicino si trova entro il raggio, la predizione può essere lasciata vuota o si può gestire con una strategia di default.

**Differenze principali tra KNN e RNN:**
- KNN: sempre $K$ vicini, anche se lontani.
- RNN: numero di vicini variabile, ma solo se abbastanza vicini.

---

## Complessità Computazionale
- **Training:** O(1) (memorizzazione dati).
- **Predizione:** O($n_{train} \cdot d$) per ogni punto di test, dove $n_{train}$ è il numero di punti di training e $d$ il numero di feature.
- Per dataset grandi, può essere lento. Si usano strutture dati come KD-tree o Ball-tree per accelerare la ricerca dei vicini.

---

## Vantaggi e Svantaggi
**Vantaggi:**
- Semplice da capire e implementare.
- Nessuna assunzione sulla distribuzione dei dati.
- Funziona bene con dataset piccoli e feature informative.

**Svantaggi:**
- Lento in predizione su dataset grandi.
- Sensibile alla scala delle feature e al rumore.
- Soffre la “maledizione della dimensionalità” (performance peggiora con molte feature).

---

## Preprocessing e Feature Scaling
Poiché KNN si basa sulle distanze, **è fondamentale che le feature siano sulla stessa scala**:
- **Standardizzazione** (StandardScaler): media 0, varianza 1.
- **Normalizzazione** (MinMaxScaler): valori tra 0 e 1.
- Feature con scale molto diverse possono dominare la distanza.

---

## Pipeline consigliata

Nella pratica è consigliabile usare una `Pipeline` di scikit-learn per evitare errori di preprocessing.

```python
from sklearn.pipeline import Pipeline
from sklearn.preprocessing import StandardScaler
from sklearn.neighbors import KNeighborsClassifier

pipeline = Pipeline([
    ("scaler", StandardScaler()),
    ("knn", KNeighborsClassifier(n_neighbors=5))
])
```

In questo modo lo stesso preprocessing viene applicato automaticamente sia in training sia in inferenza.

---

## Sezione Pratica: Classificazione con KNN

### 1. Generazione dati di esempio
```python
from sklearn.datasets import make_classification
from sklearn.model_selection import train_test_split

# Genera un dataset di classificazione sintetico
X, y = make_classification(n_samples=1000, n_features=10, n_informative=5, random_state=42)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)
```

### 2. KNeighborsClassifier: sweep su diversi valori di K
```python
from sklearn.neighbors import KNeighborsClassifier
from sklearn.metrics import accuracy_score, log_loss
import numpy as np

K_values = [1,2,3,4,5,10,12,15,20,30,40,50]
results = []

for k in K_values:
    knn = KNeighborsClassifier(n_neighbors=k)
    knn.fit(X_train, y_train)
    y_pred = knn.predict(X_test)
    y_proba = knn.predict_proba(X_test)
    acc = accuracy_score(y_test, y_pred)
    ll = log_loss(y_test, y_proba)
    results.append((k, acc, ll))

for k, acc, ll in results:
    print(f"K={k:2d}  |  Accuracy={acc:.3f}  |  LogLoss={ll:.3f}")
```

### 3. Ispezione dei vicini con kneighbors()
```python
# Prendiamo il primo punto di test e vediamo i suoi vicini
distances, indices = knn.kneighbors(X_test[:1])
print("Distanze:", distances)
print("Indici dei vicini:", indices)
print("Classi dei vicini:", y_train[indices[0]])
```

### 4. RadiusNeighborsClassifier con MinMaxScaler
```python
from sklearn.neighbors import RadiusNeighborsClassifier
from sklearn.preprocessing import MinMaxScaler

# Preprocessing: normalizzazione su [0,1]
scaler = MinMaxScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)

radii = np.linspace(0.2, 1.0, 5)
for r in radii:
    rnn = RadiusNeighborsClassifier(radius=r, outlier_label=None)
    rnn.fit(X_train_scaled, y_train)
    y_pred = rnn.predict(X_test_scaled)
    acc = accuracy_score(y_test, y_pred)
    print(f"Radius={r:.2f} | Accuracy={acc:.3f}")
```
**Nota:** anche i punti di test vanno trasformati con lo stesso scaler!

---

## Confronto con Logistic Regression, SVM e Decision Trees

| Modello                | Tipo            | Parametrico | Complessità Predizione | Sensibile a Scaling | Interpretabilità | Gestione feature non lineari |
|------------------------|-----------------|-------------|-----------------------|--------------------|-----------------|------------------------------|
| KNN                    | Class/Reg       | No          | Alta                  | Sì                 | Bassa           | Sì (locale)                  |
| Logistic Regression    | Classificazione | Sì          | Bassa                 | Sì                 | Alta            | Solo lineari                 |
| SVM                    | Classificazione | Sì          | Media/Alta            | Sì                 | Media           | Sì (con kernel)              |
| Decision Trees         | Class/Reg       | No          | Bassa                 | No                 | Alta            | Sì                           |

- **KNN**: non parametrico, computazionalmente costoso in predizione, adatto a dati con struttura locale.
- **Logistic Regression**: modello lineare, efficiente, interpretabile.
- **SVM**: potente con kernel, ma tuning complesso.
- **Decision Trees**: non richiede scaling, interpretabile, rischia overfitting.

---

## Errori Comuni
- Dimenticare la normalizzazione/scaling delle feature.
- Usare $K$ troppo basso o troppo alto senza cross-validation.
- Applicare KNN a dati ad alta dimensionalità senza riduzione dimensionale.
- Non gestire i punti senza vicini nel caso RNN.
- Non valutare la sensibilità al rumore.
- Usare il test set per scegliere il valore ottimale di `K` invece della cross-validation.
- Dimenticare di applicare lo stesso scaler ai nuovi dati in fase di inferenza.

---

## Quiz di Ripasso
**1. KNN è un modello parametrico o non parametrico?**  
Risposta: Non parametrico.

**2. Perché è importante normalizzare le feature prima di applicare KNN?**  
Risposta: Perché la distanza è sensibile alla scala delle feature.

**3. Cosa succede se scelgo $K=1$?**  
Risposta: Il modello rischia di sovradattare (overfitting).

**4. In cosa differisce Radius Nearest Neighbors da KNN?**  
Risposta: RNN considera tutti i vicini entro un raggio fissato, mentre KNN ne considera sempre $K$.

**5. Qual è la complessità computazionale della predizione in KNN?**  
Risposta: O($n_{train} \cdot d$) per ogni punto di test.

---

## Deeptest: Domande e Risposte Recuperate dal Master
1. **KNN gestisce direttamente la distribuzione dei dati?**  
   No, KNN non fa assunzioni sulla distribuzione dei dati.
2. **Quale metrica di distanza è più robusta agli outlier: Manhattan o Euclidea?**  
   Manhattan.
3. **Cosa rappresenta il parametro $p$ nella distanza di Minkowski?**  
   Il grado della norma: $p=1$ (Manhattan), $p=2$ (Euclidea).
4. **Come si sceglie il valore ottimale di $K$?**  
   Usando la cross-validation.
5. **Quando conviene usare Radius Nearest Neighbors?**  
   Quando la densità dei dati è variabile e si vuole considerare solo vicini “veramente” prossimi.
6. **Qual è il costo computazionale della predizione KNN su $n$ dati di training e $d$ feature?** Risposta: O($n \cdot d$) per ogni predizione.
7. **Cosa succede se un punto di test non ha vicini entro il raggio fissato in RNN?** Risposta: può essere classificato come outlier o si assegna una classe di default.
8. **Qual è il problema principale di KNN in alta dimensionalità?** Risposta: la “maledizione della dimensionalità”: tutte le distanze tendono a essere simili, il modello perde efficacia.
9. **Come si accelera la ricerca dei vicini?** Risposta: usando strutture dati come KD-tree o Ball-tree.
10. **KNN è sensibile al rumore?** Risposta: sì, soprattutto per valori bassi di $K$.
11. **Perché è importante il preprocessing delle feature in KNN?** Risposta: per evitare che feature con scale diverse dominino la distanza.
12. **KNN può essere usato per la regressione?** Risposta: sì, media dei target dei vicini.
13. **Cosa succede se il dataset ha molte feature irrilevanti?** Risposta: KNN può degradare perché le feature inutili “diluiscono” la distanza.
14. **KNN può gestire dati categoriali?** Risposta: solo se si definisce una distanza adatta per le categorie.
15. **Come gestire dataset sbilanciati con KNN?** Risposta: si può pesare il voto dei vicini o usare tecniche di bilanciamento.
16. **Quando preferire un modello parametrico a KNN?** Risposta: se si desidera velocità in predizione o interpretabilità globale.

---

## Exam Summary & Insights dal Master
- KNN è un modello semplice, efficace su dati a bassa dimensionalità e con struttura locale.
- Fondamentale il preprocessing delle feature.
- La scelta di $K$ e della metrica di distanza va ottimizzata con validazione incrociata.
- RNN è utile quando si vuole evitare di considerare vicini troppo lontani.
- KNN non scala bene su dataset molto grandi o ad alta dimensionalità.
- Va confrontato con modelli parametrici (LR, SVM, DT) per scegliere la soluzione più adatta.

---

## Checklist finale di padronanza

Alla fine del capitolo dovresti saper spiegare:

- perché KNN è un algoritmo lazy learning;
- differenza tra modello parametrico e non parametrico;
- ruolo delle metriche di distanza;
- come scegliere il valore di `K`;
- differenza tra KNN e Radius Nearest Neighbors;
- perché lo scaling è fondamentale;
- vantaggi e limiti di KNN;
- quando preferire KNN rispetto a Logistic Regression, SVM o Decision Tree.

---

## Collegamenti consigliati

Per consolidare questo argomento confrontalo con:

- Naive Bayes;
- SVM;
- Decision Tree & Random Forest;
- Neural Networks.

---

## Recovery Status

| Sezione                           | Stato      |
|------------------------------------|------------|
| Introduzione                       | ✅         |
| Lazy learning/non parametrico      | ✅         |
| Metriche di distanza               | ✅         |
| Algoritmo KNN                      | ✅         |
| Scelta K, overfitting/underfitting | ✅         |
| Radius Nearest Neighbors           | ✅         |
| Complessità computazionale         | ✅         |
| Vantaggi/svantaggi                 | ✅         |
| Preprocessing/scaling              | ✅         |
| Pipeline consigliata             | ✅         |
| Esempi pratici Python              | ✅         |
| Confronto altri modelli            | ✅         |
| Errori comuni                      | ✅         |
| Quiz di ripasso                    | ✅         |
| Deeptest domande/risposte          | ✅         |
| Exam summary/insights              | ✅         |
| Checklist finale                 | ✅         |
| Collegamenti                     | ✅         |
| Recovery score                     | **99%**   |

---

## Stato editoriale

**Stato:** FINAL 1.0

Il capitolo è considerato chiuso in prima versione definitiva. Eventuali modifiche future dovranno limitarsi a integrazioni provenienti dal materiale originale del Master o a uniformazioni stilistiche dell'intero repository.
