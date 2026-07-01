# Logistic Regression

Modulo: Machine Learning – Modelli e Algoritmi

---

## Obiettivo del capitolo

La Logistic Regression è uno degli algoritmi di classificazione supervisionata più importanti del Machine Learning. Nonostante il nome, non viene utilizzata per problemi di regressione, ma per stimare la probabilità che un’istanza appartenga a una determinata classe.

In questo capitolo verranno approfonditi:

- il funzionamento matematico della Logistic Regression;
- la funzione sigmoide;
- odds e log-odds;
- la funzione di costo (Log Loss);
- l’addestramento tramite Gradient Descent;
- la regolarizzazione;
- la classificazione multiclasse;
- l’implementazione con scikit-learn;
- le metriche di valutazione;
- il confronto con gli altri algoritmi studiati nel Master.

---

## Introduzione

La Logistic Regression è un algoritmo di apprendimento supervisionato utilizzato principalmente per problemi di classificazione.

L’obiettivo non è prevedere un valore numerico continuo, ma stimare la probabilità che un campione appartenga ad una determinata classe.

Esempi tipici sono:

- spam / ham;
- cliente acquisterà / non acquisterà;
- tumore benigno / maligno;
- transazione fraudolenta / lecita.

Per questo motivo la Logistic Regression rappresenta uno dei modelli di riferimento per la classificazione binaria.

---

Perché si chiama “Regression”?

Una delle domande più frequenti durante lo studio è:

Se classifica, perché si chiama Regression?

La risposta è storica.

Il modello nasce come estensione della regressione lineare.

La regressione lineare produce un valore reale:

y = w₁x₁ + w₂x₂ + ... + b

che può assumere qualsiasi valore.

Questo è un problema nella classificazione, perché una probabilità deve appartenere all’intervallo:

0 ≤ p ≤ 1

Per trasformare il risultato della combinazione lineare in una probabilità viene applicata una funzione non lineare:

- la funzione sigmoide.

La regressione avviene quindi sul logaritmo degli odds, mentre il risultato finale è una probabilità.

Da qui deriva il nome Logistic Regression.

---

## Quando utilizzare la Logistic Regression

La Logistic Regression è particolarmente indicata quando:

- il problema è di classificazione supervisionata;
- le classi sono separabili in modo approssimativamente lineare;
- è importante interpretare i coefficienti del modello;
- si desidera ottenere probabilità oltre alla semplice previsione della classe.

È spesso utilizzata come baseline perché:

- è semplice;
- è veloce da addestrare;
- richiede poche risorse;
- è facilmente interpretabile.

---

## Fondamenti matematici

Il modello calcola inizialmente una combinazione lineare delle feature:

z = w · x + b

dove:

- w rappresenta il vettore dei pesi;
- x rappresenta il vettore delle feature;
- b è il bias.

Il valore ottenuto può assumere qualsiasi numero reale.

Per trasformarlo in una probabilità viene utilizzata la funzione logistica.

---

## La funzione Sigmoide

La funzione sigmoide è definita come:

σ(z) = 1 / (1 + e^(-z))

Le sue proprietà principali sono:

- restituisce sempre valori compresi tra 0 e 1;
- è continua e derivabile;
- è monotona crescente;
- permette di interpretare l’output come probabilità.

Il comportamento è intuitivo:

| z | σ(z) |
|---|---|
| molto negativo | circa 0 |
| 0 | 0.5 |
| molto positivo | circa 1 |

La sigmoide comprime qualsiasi valore reale nell’intervallo delle probabilità.

---

## Decision Boundary

Una volta ottenuta la probabilità, il modello deve trasformarla in una classe.

Normalmente viene utilizzata una soglia pari a:

0.5

Quindi:

P(y=1|x) ≥ 0.5  → classe positiva
P(y=1|x) < 0.5  → classe negativa

La superficie che separa le due classi prende il nome di Decision Boundary.

Nel caso della Logistic Regression, la decision boundary è lineare e coincide con:

w · x + b = 0

Questo rende la Logistic Regression un classificatore lineare.

---

## Odds e Log-Odds

La Logistic Regression non modella direttamente la probabilità, ma gli odds.

Gli odds rappresentano il rapporto tra la probabilità che un evento avvenga e quella che non avvenga:

odds = p / (1 - p)

Applicando il logaritmo si ottiene il logit:

log(p / (1-p))

Il modello assume che questo valore possa essere espresso come una combinazione lineare delle feature:

log(p / (1-p)) = w · x + b

Questa relazione è il cuore matematico della Logistic Regression.

---

## Interpretazione dei coefficienti

Uno dei principali vantaggi della Logistic Regression è l’elevata interpretabilità.

Ogni coefficiente indica come varia il log-odds al variare della corrispondente feature.

In generale:

- coefficiente positivo → aumenta la probabilità della classe positiva;
- coefficiente negativo → la diminuisce;
- coefficiente vicino a zero → influenza limitata.

Questa caratteristica rende la Logistic Regression molto utilizzata in ambito medico, finanziario e assicurativo, dove è importante comprendere il contributo delle variabili.

---

## Funzione di costo: Log Loss (Cross Entropy)

Nella regressione lineare la qualità delle previsioni viene spesso misurata tramite la Mean Squared Error (MSE).

Per la Logistic Regression, invece, la MSE non è la scelta ideale perché, combinata con la funzione sigmoide, produce una funzione di costo non convessa e rende più difficile l’ottimizzazione.

Per questo motivo si utilizza la Log Loss, detta anche Binary Cross Entropy.

Intuizione

La Log Loss misura quanto le probabilità previste dal modello siano vicine ai valori reali.

Un buon classificatore dovrebbe assegnare:

- probabilità vicine a 1 per la classe corretta;
- probabilità vicine a 0 per la classe errata.

La funzione di costo penalizza fortemente le previsioni molto sicure ma sbagliate.

Ad esempio:

| Probabilità prevista | Classe reale | Penalità |
|---|---|---|
| 0.99 | positiva | molto bassa |
| 0.80 | positiva | bassa |
| 0.55 | positiva | media |
| 0.01 | positiva | molto elevata |

Questo comportamento rende la Logistic Regression particolarmente adatta ai problemi di classificazione probabilistica.

Formula

La Binary Cross Entropy è definita come:

Loss = - [ y log(p) + (1-y) log(1-p) ]

dove:

- y è la classe reale (0 oppure 1);
- p è la probabilità prevista dal modello.

L’obiettivo dell’addestramento è minimizzare questa funzione di costo.

---

## Addestramento tramite Gradient Descent

La Logistic Regression viene addestrata con lo stesso principio studiato nel capitolo dedicato al Gradient Descent.

Il ciclo di addestramento è il seguente:

1. inizializzazione casuale dei pesi;
2. calcolo della combinazione lineare z = w·x + b;
3. applicazione della funzione sigmoide;
4. calcolo della Log Loss;
5. calcolo dei gradienti;
6. aggiornamento dei pesi;
7. ripetizione per più epoche.

L’algoritmo termina quando la funzione di costo converge oppure quando viene raggiunto il numero massimo di iterazioni.

Learning Rate

Il learning rate controlla l’ampiezza dell’aggiornamento dei parametri.

- Un valore troppo elevato può impedire la convergenza.
- Un valore troppo basso rende l’addestramento molto lento.

Per questo motivo la scelta del learning rate è un compromesso tra velocità e stabilità.

---

## Regolarizzazione

La Logistic Regression può andare incontro a overfitting, soprattutto quando il numero di feature è elevato.

Per limitare questo problema vengono introdotti termini di regolarizzazione.

L2 Regularization (Ridge)

La regolarizzazione L2 aggiunge una penalizzazione proporzionale al quadrato dei coefficienti.

Effetti principali:

- riduce coefficienti molto grandi;
- migliora la generalizzazione;
- mantiene tutte le feature nel modello.

È la modalità predefinita nella maggior parte delle implementazioni di scikit-learn.

L1 Regularization (Lasso)

La regolarizzazione L1 tende invece a portare alcuni coefficienti esattamente a zero.

Questo permette anche di effettuare una selezione automatica delle feature.

È utile quando il dataset contiene molte variabili irrilevanti.

---

## Classificazione multiclasse

La Logistic Regression nasce come classificatore binario.

Per problemi con più classi si possono adottare due strategie.

One-vs-Rest (OvR)

Si costruisce un classificatore binario per ciascuna classe.

Ogni modello distingue:

- una classe;
- tutte le altre.

La previsione finale corrisponde alla probabilità più elevata.

Multinomial Logistic Regression

In alternativa è possibile addestrare un unico modello che gestisce contemporaneamente tutte le classi.

Questa modalità è generalmente preferibile quando supportata dal solver scelto.

---

## Workflow completo

Una pipeline tipica è la seguente:

1. raccolta dei dati;
2. pulizia del dataset;
3. train/test split;
4. standardizzazione delle feature;
5. addestramento della Logistic Regression;
6. valutazione tramite metriche;
7. ottimizzazione degli iperparametri;
8. utilizzo del modello per l’inferenza.

---

## Implementazione con scikit-learn

La Logistic Regression è implementata in scikit-learn tramite la classe LogisticRegression.

L’utilizzo tipico segue il classico workflow:

from sklearn.linear_model import LogisticRegression
model = LogisticRegression()
model.fit(X_train, y_train)
predictions = model.predict(X_test)

Il metodo fit() addestra il modello utilizzando il training set, mentre predict() restituisce la classe prevista.

Quando è necessario conoscere anche la probabilità associata ad ogni previsione si utilizza:

probabilities = model.predict_proba(X_test)

Il risultato contiene, per ogni campione, la probabilità di appartenenza a ciascuna classe.

---

## Pipeline consigliata

Nella pratica è consigliabile utilizzare una Pipeline.

La Logistic Regression è infatti sensibile alla scala delle feature; per questo motivo è buona pratica standardizzare i dati prima dell’addestramento.

from sklearn.pipeline import Pipeline
from sklearn.preprocessing import StandardScaler
from sklearn.linear_model import LogisticRegression
pipeline = Pipeline([
    ("scaler", StandardScaler()),
    ("model", LogisticRegression(random_state=42))
])
pipeline.fit(X_train, y_train)
y_pred = pipeline.predict(X_test)

L’utilizzo della Pipeline garantisce che lo stesso preprocessing venga applicato sia durante il training sia durante l’inferenza.

---

## Hyperparameter Tuning

Gli iperparametri più importanti sono:

| Parametro | Significato |
|---|---|
| C | Intensità della regolarizzazione |
| penalty | Tipo di regolarizzazione (L1, L2, ElasticNet) |
| solver | Algoritmo di ottimizzazione |
| max_iter | Numero massimo di iterazioni |
| class_weight | Gestione di dataset sbilanciati |

Ricordiamo che il parametro C è l’inverso della forza della regolarizzazione.

| Valore di C | Effetto |
|---|---|
| piccolo | maggiore regolarizzazione |
| grande | minore regolarizzazione |

Per scegliere i valori migliori si utilizza normalmente la Grid Search.

from sklearn.model_selection import GridSearchCV
parameters = {
    "model__C": [0.01, 0.1, 1, 10],
    "model__penalty": ["l2"]
}
grid = GridSearchCV(
    pipeline,
    parameters,
    cv=5,
    scoring="accuracy"
)
grid.fit(X_train, y_train)
print(grid.best_params_)

---

## Metriche di valutazione

Come tutti i classificatori, la Logistic Regression deve essere valutata mediante opportune metriche.

Accuracy

Indica la percentuale di classificazioni corrette.

È semplice da interpretare ma può risultare fuorviante in presenza di dataset sbilanciati.

---

## Precision

Risponde alla domanda:

Tra tutte le osservazioni classificate come positive, quante erano realmente positive?

Una precision elevata riduce i falsi positivi.

---

## Recall

Risponde alla domanda:

Tra tutte le osservazioni realmente positive, quante sono state individuate?

Una recall elevata riduce i falsi negativi.

---

## F1-Score

L’F1-Score rappresenta la media armonica tra Precision e Recall.

È particolarmente utile quando le classi sono sbilanciate.

---

## ROC Curve

La ROC Curve mostra il compromesso tra:

- True Positive Rate;
- False Positive Rate.

Un classificatore perfetto passa vicino all’angolo superiore sinistro del grafico.

---

## AUC

L’Area Under the Curve sintetizza la qualità della ROC Curve.

Valori tipici:

| AUC | Interpretazione |
|---|---|
| 0.50 | classificatore casuale |
| 0.70 | discreto |
| 0.80 | buono |
| 0.90 | ottimo |
| 1.00 | perfetto |

---

## Esempio completo

from sklearn.datasets import load_breast_cancer
from sklearn.model_selection import train_test_split
from sklearn.pipeline import Pipeline
from sklearn.preprocessing import StandardScaler
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import classification_report
dataset = load_breast_cancer()
X_train, X_test, y_train, y_test = train_test_split(
    dataset.data,
    dataset.target,
    test_size=0.2,
    random_state=42
)
pipeline = Pipeline([
    ("scaler", StandardScaler()),
    ("model", LogisticRegression(max_iter=1000))
])
pipeline.fit(X_train, y_train)
predictions = pipeline.predict(X_test)
print(classification_report(y_test, predictions))

Questo esempio rappresenta una tipica pipeline utilizzata anche in contesti reali e riassume l’intero workflow di addestramento e valutazione della Logistic Regression.

Confronto con gli altri algoritmi

La Logistic Regression rappresenta un ottimo compromesso tra semplicità, interpretabilità e prestazioni.

| Algoritmo | Punti di forza | Limiti |
|---|---|---|
| Logistic Regression | Veloce, interpretabile, restituisce probabilità | Decision boundary lineare |
| Naive Bayes | Molto veloce, ottimo per NLP | Ipotesi di indipendenza spesso irrealistica |
| SVM | Ottime prestazioni con margine massimo | Richiede tuning accurato dei parametri |
| KNN | Molto semplice | Costoso in fase di inferenza |
| Decision Tree | Molto interpretabile | Facilmente soggetto a overfitting |
| Random Forest | Robusto e accurato | Meno interpretabile |
| Neural Networks | Molto flessibili | Richiedono molti dati e tuning |

---

## Errori comuni

Non standardizzare le feature

La Logistic Regression è sensibile alla scala delle variabili.

Quando le feature hanno ordini di grandezza molto diversi, l’ottimizzazione tramite Gradient Descent può diventare lenta o instabile.

Per questo motivo è consigliabile utilizzare StandardScaler.

---

## Interpretare le probabilità come certezze

Una probabilità pari a:

0.72

non significa che il modello “sa” con certezza che l’osservazione appartenga alla classe positiva.

Significa semplicemente che, secondo il modello appreso, quella è la probabilità stimata.

---

## Usare Accuracy su dataset sbilanciati

Nei problemi con classi molto sbilanciate l’Accuracy può essere fuorviante.

Occorre osservare anche:

- Precision
- Recall
- F1-Score
- ROC AUC

---

## Dimenticare la regolarizzazione

Quando il numero di feature cresce, la regolarizzazione diventa importante per limitare l’overfitting.

---

## Utilizzare pochi valori di max_iter

Se il modello non converge, scikit-learn restituisce un warning.

In questi casi è spesso sufficiente aumentare:

max_iter=1000

---

## Quiz di ripasso

Domanda 1

Perché la Logistic Regression è un classificatore e non un algoritmo di regressione?

Risposta: perché restituisce probabilità di appartenenza alle classi utilizzando la funzione sigmoide.

---

## Domanda 2

Che cosa rappresenta il parametro C?

Risposta: controlla la forza della regolarizzazione. Valori piccoli implicano maggiore regolarizzazione.

---

## Domanda 3

Perché si utilizza la Log Loss invece della MSE?

Risposta: perché è più adatta alla classificazione probabilistica e rende l’ottimizzazione più efficace.

---

## Domanda 4

Quando è utile utilizzare StandardScaler?

Risposta: praticamente sempre quando si utilizza Logistic Regression, perché migliora la convergenza del Gradient Descent.

---

## Domanda 5

Qual è il principale vantaggio della Logistic Regression rispetto a molti altri classificatori?

Risposta: l’elevata interpretabilità dei coefficienti.

---

## Deeptest

Domanda 1

La Logistic Regression utilizza normalmente:

- A. Mean Squared Error
- B. Binary Cross Entropy
- C. Entropia di Shannon
- D. Gini

Risposta corretta: B.

---

## Domanda 2

La funzione sigmoide restituisce valori:

- A. tra -1 e 1
- B. tra 0 e 1
- C. tra 0 e infinito
- D. qualsiasi valore reale

Risposta corretta: B.

---

## Domanda 3

Quale parametro controlla la regolarizzazione?

- A. gamma
- B. K
- C. C
- D. degree

Risposta corretta: C.

---

## Domanda 4

La Logistic Regression è:

- A. un classificatore lineare
- B. un algoritmo non supervisionato
- C. un ensemble
- D. un algoritmo lazy

Risposta corretta: A.

---

## Domanda 5

La Pipeline consigliata comprende normalmente:

- A. PCA e KMeans
- B. StandardScaler e LogisticRegression
- C. DecisionTree e RandomForest
- D. MinMaxScaler e KNN

Risposta corretta: B.

---

## Checklist finale di padronanza

Al termine di questo capitolo dovresti essere in grado di spiegare:

- il principio della Logistic Regression;
- la funzione sigmoide;
- odds e log-odds;
- la Decision Boundary;
- la Binary Cross Entropy;
- il ruolo del Gradient Descent;
- la regolarizzazione L1 e L2;
- il significato del parametro C;
- la classificazione multiclasse;
- il workflow completo con scikit-learn;
- le principali metriche di valutazione.

---

## Collegamenti consigliati

Questo capitolo è strettamente collegato a:

- Gradient Descent
- Naive Bayes
- SVM
- Nearest Neighbors
- Neural Networks
- Decision Tree & Random Forest
- MLOps

---

## Stato del recupero

| Area | Stato |
|---|---|
| Teoria | ✅ |
| Fondamenti matematici | ✅ |
| Sigmoide | ✅ |
| Log Loss | ✅ |
| Gradient Descent | ✅ |
| Regolarizzazione | ✅ |
| Classificazione multiclasse | ✅ |
| Pipeline scikit-learn | ✅ |
| Hyperparameter Tuning | ✅ |
| Metriche | ✅ |
| Codice Python | ✅ |
| Errori comuni | ✅ |
| Quiz | ✅ |
| Deeptest | ✅ |
| Checklist finale | ✅ |
| Collegamenti | ✅ |

Recovery score stimato: 99%

---

## Stato editoriale

Stato: FINAL 1.0

Il capitolo è considerato completo in prima versione definitiva.

Eventuali modifiche future dovranno limitarsi a:

- integrazione di materiale originale del Master;
- uniformazione stilistica con gli altri capitoli;
- correzione di eventuali refusi.
