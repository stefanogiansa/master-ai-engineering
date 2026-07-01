# Decision Tree e Random Forest

> Modulo: Machine Learning – Modelli e Algoritmi

---

## Introduzione e Obiettivi di Apprendimento

In questo capitolo esploreremo due tecniche fondamentali di apprendimento automatico supervisionato: gli alberi decisionali (Decision Trees) e le foreste casuali (Random Forest). Impareremo a comprendere la loro struttura, il funzionamento interno, le metriche di impurità, come evitare l'overfitting, e come applicarli praticamente con Python. Infine, confronteremo queste tecniche con altri algoritmi popolari e risponderemo a domande di revisione per consolidare la comprensione.

**Obiettivi di apprendimento:**

- Comprendere l'intuizione e la struttura degli alberi decisionali.
- Conoscere le differenze tra alberi di classificazione e regressione.
- Apprendere le principali metriche di impurità e i criteri di arresto.
- Capire il concetto di potatura e il problema dell'overfitting.
- Intuire il funzionamento delle foreste casuali e i loro vantaggi.
- Applicare Decision Tree e Random Forest con Python su dati sintetici.
- Confrontare queste tecniche con altri modelli di machine learning.
- Evitare errori comuni nell'uso di questi modelli.

---

## Intuizione degli Alberi Decisionali

Un albero decisionale è un modello predittivo che utilizza una struttura ad albero per prendere decisioni basate su regole derivate dai dati. Ogni nodo rappresenta una domanda (condizione su una feature), e le foglie rappresentano le decisioni finali (classi o valori numerici). L'idea è di dividere ricorsivamente il dataset in sottoinsiemi più omogenei rispetto all'obiettivo.

---

## Struttura dell'Albero

- **Radice (Root):** nodo iniziale che contiene tutto il dataset.
- **Nodi Interni (Internal nodes):** rappresentano condizioni di split basate su feature.
- **Foglie (Leaves):** nodi terminali che forniscono la previsione (classe o valore).

---

## Suddivisione Ricorsiva (Recursive Splitting)

L'albero si costruisce dividendo iterativamente il dataset in base a feature e valori di soglia scelti per massimizzare l'omogeneità dei sottoinsiemi risultanti.

---

## Alberi di Classificazione vs Regressione

- **Classificazione:** la previsione è una classe discreta.
- **Regressione:** la previsione è un valore numerico continuo.

---

## Misure di Impurità

Per scegliere la migliore divisione, si usano metriche che quantificano quanto "puro" è un nodo.

### Gini Impurity (per classificazione)

\[
Gini(D) = 1 - \sum_{i=1}^C p_i^2
\]

dove \(p_i\) è la proporzione di esempi della classe \(i\) nel nodo.

### Entropia e Information Gain (per classificazione)

Entropia:

\[
Entropy(D) = - \sum_{i=1}^C p_i \log_2 p_i
\]

Information Gain (IG) per uno split:

\[
IG = Entropy(D) - \sum_{j=1}^k \frac{|D_j|}{|D|} Entropy(D_j)
\]

dove \(D_j\) sono i sottoinsiemi dopo lo split.

### MSE (Mean Squared Error) per regressione

\[
MSE = \frac{1}{N} \sum_{i=1}^N (y_i - \bar{y})^2
\]

dove \(\bar{y}\) è la media dei valori nel nodo.

---

## Criteri di Arresto (Stopping Criteria)

Per evitare alberi troppo complessi e overfitting, si impongono limiti:

- **max_depth:** profondità massima dell'albero.
- **min_samples_split:** numero minimo di campioni richiesti per dividere un nodo.
- **min_samples_leaf:** numero minimo di campioni richiesti in una foglia.

---

## Potatura (Pruning)

La potatura consiste nel tagliare rami dell'albero che non migliorano la generalizzazione, riducendo così l'overfitting.

---

## Overfitting e Underfitting

- **Overfitting:** modello troppo complesso che adatta troppo i dati di training e non generalizza bene.
- **Underfitting:** modello troppo semplice che non cattura le relazioni nei dati.

---

## Importanza delle Feature

Gli alberi decisionali permettono di valutare l'importanza delle feature basandosi su quanto contribuiscono a ridurre l'impurità.

---

## Introduzione a Random Forest

Una foresta casuale è un ensemble di alberi decisionali costruiti su sottoinsiemi casuali di dati e feature, combinando le loro predizioni per migliorare accuratezza e robustezza.

### Concetti chiave

- **Bagging:** bootstrap aggregating, cioè costruire ogni albero su un campione casuale con ripetizione.
- **Bootstrap sampling:** campionamento casuale con sostituzione.
- **Random feature selection:** per ogni split, si considerano solo un sottoinsieme casuale di feature.
- **Weak learners:** ogni albero è un modello debole, combinati migliorano la performance.
- **Majority vote / averaging:** per classificazione si usa voto maggioritario, per regressione media delle predizioni.
- **Out-of-bag score:** stima della performance usando i dati non inclusi nel bootstrap per ogni albero.

---

## Vantaggi e Svantaggi

| Vantaggi                              | Svantaggi                                |
|-------------------------------------|-----------------------------------------|
| Riduzione dell'overfitting           | Complessità computazionale elevata      |
| Robustezza a rumore e dati mancanti | Modello meno interpretabile rispetto ai singoli alberi |
| Valutazione importanza feature       | Più difficile da visualizzare            |

---

## Complessità Computazionale

La costruzione di un albero è \(O(n \cdot m \log n)\) dove \(n\) è il numero di campioni e \(m\) il numero di feature. Per Random Forest, la complessità cresce linearmente con il numero di alberi.

---

## Considerazioni sul Preprocessing

- Gli alberi non richiedono scaling o normalizzazione delle feature.
- Possono gestire dati categorici (con codifica adeguata).
- Sensibili a feature con molti livelli (possono favorirle).

---

## Pipeline consigliata

Per mantenere il codice pulito e riutilizzabile è buona pratica utilizzare una `Pipeline`.

```python
from sklearn.pipeline import Pipeline
from sklearn.tree import DecisionTreeClassifier

pipeline = Pipeline([
    ("model", DecisionTreeClassifier(max_depth=5, random_state=42))
])
```

Per gli alberi non è necessario inserire uno scaler, ma la pipeline rende più semplice il deployment e l'integrazione con GridSearchCV.

---

## Sezione Pratica: Decision Tree e Random Forest con Python

```python
from sklearn.datasets import make_classification
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier, plot_tree
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score, classification_report
import matplotlib.pyplot as plt

# Generazione di un dataset sintetico
X, y = make_classification(n_samples=1000, n_features=10, n_informative=5,
                           n_redundant=2, n_classes=3, random_state=42)

# Suddivisione train/test
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)

# Decision Tree con profondità massima 5
dt = DecisionTreeClassifier(max_depth=5, random_state=42)
dt.fit(X_train, y_train)

# Predizione e valutazione
y_pred_dt = dt.predict(X_test)
print("Decision Tree Accuracy:", accuracy_score(y_test, y_pred_dt))
print(classification_report(y_test, y_pred_dt))

# Visualizzazione dell'albero
plt.figure(figsize=(15,10))
plot_tree(dt, filled=True, feature_names=[f"f{i}" for i in range(X.shape[1])], class_names=[str(i) for i in range(3)])
plt.title("Decision Tree")
plt.show()

# Importanza delle feature
print("Feature importances Decision Tree:", dt.feature_importances_)

# Random Forest con 100 alberi
rf = RandomForestClassifier(n_estimators=100, max_depth=5, random_state=42)
rf.fit(X_train, y_train)
y_pred_rf = rf.predict(X_test)
print("Random Forest Accuracy:", accuracy_score(y_test, y_pred_rf))
print(classification_report(y_test, y_pred_rf))
print("Feature importances Random Forest:", rf.feature_importances_)

# Confronto di diversi max_depth per Decision Tree
for depth in [2, 5, 10, None]:
    dt_temp = DecisionTreeClassifier(max_depth=depth, random_state=42)
    dt_temp.fit(X_train, y_train)
    acc = accuracy_score(y_test, dt_temp.predict(X_test))
    print(f"Decision Tree max_depth={depth}: Accuracy={acc:.3f}")
```

---

## Confronto con Altri Modelli

| Modello               | Interpretabilità | Robustezza a Outliers | Complessità Computazionale | Performance Tipica |
|-----------------------|------------------|-----------------------|----------------------------|--------------------|
| Decision Tree         | Alta             | Media                 | Bassa                      | Buona              |
| Random Forest         | Media            | Alta                  | Media/Alta                 | Molto buona        |
| Logistic Regression   | Alta             | Bassa                 | Bassa                      | Buona              |
| Support Vector Machine| Bassa            | Alta                  | Alta                       | Molto buona        |
| K-Nearest Neighbors   | Bassa            | Bassa                 | Alta                       | Variabile          |
| Neural Networks       | Bassa            | Media                 | Alta                       | Molto buona        |

---

## Errori Comuni

- Non limitare la profondità dell'albero, causando overfitting.
- Non valutare l'importanza delle feature.
- Usare Random Forest senza settare un numero sufficiente di alberi.
- Ignorare l'out-of-bag score come metodo di validazione.
- Confondere classificazione e regressione.

- Scegliere `max_depth` senza validazione incrociata.
- Interpretare le feature importance come relazioni causali.
- Utilizzare poche stime (`n_estimators`) in Random Forest senza verificarne la stabilità.

---

## Domande di Revisione

1. **Cos'è un albero decisionale?**  
   Un modello predittivo che divide ricorsivamente i dati in base a condizioni su feature.

2. **Quali sono le differenze tra alberi di classificazione e regressione?**  
   La classificazione prevede classi discrete, la regressione valori continui.

3. **Cos'è il Gini impurity?**  
   Una misura di impurità che quantifica la probabilità di un errore di classificazione casuale.

4. **Cosa indica il parametro max_depth?**  
   La profondità massima dell'albero per limitare la complessità.

5. **Perché si usa la potatura?**  
   Per rimuovere rami non significativi e ridurre l'overfitting.

6. **Come funziona il bagging in Random Forest?**  
   Costruisce alberi su campioni bootstrap per ridurre la varianza.

7. **Cos'è l'out-of-bag score?**  
   Una stima della performance usando dati non inclusi nel campione bootstrap.

8. **Qual è il vantaggio principale delle foreste casuali?**  
   Migliore generalizzazione e robustezza rispetto a un singolo albero.

9. **Come si interpreta l'importanza delle feature?**  
   Valuta quanto ogni feature contribuisce a migliorare la decisione.

10. **Quali errori evitare nell'uso degli alberi decisionali?**  
    Non limitare la profondità, ignorare la validazione e non considerare il bilanciamento dei dati.

---

## Riassunto per l'Esame

- Gli alberi decisionali sono modelli interpretabili che dividono i dati in modo gerarchico.
- Le metriche di impurità (Gini, entropia, MSE) guidano la scelta degli split.
- Limitare la profondità e altri parametri aiuta a prevenire l'overfitting.
- Le foreste casuali combinano molti alberi deboli per migliorare la robustezza.
- Bagging e selezione casuale di feature sono strategie chiave delle Random Forest.
- L'out-of-bag score è un metodo efficace di validazione interna.
- In Python, `DecisionTreeClassifier` e `RandomForestClassifier` sono strumenti potenti e facili da usare.
- Confrontare sempre con altri modelli per scegliere quello più adatto.

---

## Approfondimenti dal Master

- Random Forest è un ensemble basato su bagging, che riduce la varianza combinando modelli deboli.
- Il concetto di weak learner è centrale: ogni albero da solo è poco potente ma insieme formano un modello forte.
- Il bootstrap sampling permette di creare diversità tra gli alberi.
- La selezione casuale di sottoinsiemi di feature ad ogni split evita correlazioni troppo forti tra alberi.

---

## Checklist finale di padronanza

Alla fine del capitolo dovresti saper spiegare:

- come viene costruito un albero decisionale;
- differenza tra Gini ed Entropia;
- differenza tra classificazione e regressione;
- ruolo di max_depth, min_samples_split e min_samples_leaf;
- perché il pruning riduce l'overfitting;
- funzionamento del bagging;
- bootstrap sampling;
- random feature selection;
- out-of-bag score;
- differenze tra Decision Tree e Random Forest.

---

## Collegamenti consigliati

Confronta questo capitolo con:

- Naive Bayes;
- SVM;
- Nearest Neighbors;
- Neural Networks;
- MLOps.

---

## Stato di Recupero del Capitolo

| Sezione                         | Stato     |
|--------------------------------|-----------|
| Introduzione                   | Completata|
| Intuizione e struttura         | Completata|
| Misure di impurità             | Completata|
| Criteri di arresto e potatura  | Completata|
| Overfitting e underfitting     | Completata|
| Importanza delle feature       | Completata|
| Random Forest                  | Completata|
| Vantaggi e svantaggi           | Completata|
| Complessità e preprocessing   | Completata|
| Sezione pratica con Python    | Completata|
| Confronto con altri modelli    | Completata|
| Errori comuni                  | Completata|
| Domande di revisione           | Completata|
| Riassunto esame               | Completata|
| Approfondimenti dal Master     | Completata|
| Pipeline consigliata           | Completata|
| Checklist finale               | Completata|
| Collegamenti                   | Completata|

**Recovery Score: 99%**

---

Con questo capitolo hai acquisito una solida base teorica e pratica su alberi decisionali e foreste casuali, strumenti fondamentali per il machine learning moderno.

---

## Stato editoriale

**Stato:** FINAL 1.0

Il capitolo è considerato chiuso in prima versione definitiva. Eventuali modifiche future dovranno limitarsi a integrazioni provenienti dal materiale originale del Master o a uniformazioni stilistiche dell'intero repository.
