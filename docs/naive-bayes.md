
# Naive Bayes

> Modulo: Machine Learning – Modelli e Algoritmi

---

## Obiettivo del capitolo

Questo capitolo raccoglie teoria, pratica ed esercitazioni del Master dedicate a Naive Bayes. Verranno analizzati il teorema di Bayes, l'ipotesi di indipendenza condizionata, le principali varianti dell'algoritmo e l'esercitazione completa di spam filtering con SMS Spam Collection.

---

## Introduzione
Naive Bayes è una famiglia di classificatori supervisionati probabilistici basati sul teorema di Bayes, con l’assunzione (naive, cioè ingenua) che le caratteristiche siano condizionatamente indipendenti tra loro dato il target. È un algoritmo semplice ma molto efficace per problemi di classificazione, specialmente quando il numero di feature è elevato.

## Teorema di Bayes
Il teorema di Bayes consente di calcolare la probabilità di un’ipotesi dato un insieme di dati osservati. La formula è:

```text
P(A|B) = (P(B|A) * P(A)) / P(B)
```

**Dove:**
- **P(A|B)**: probabilità posteriore, probabilità dell’ipotesi A dato che si è osservato B.
- **P(B|A)**: verosimiglianza (likelihood), probabilità di osservare B se A è vera.
- **P(A)**: probabilità a priori dell’ipotesi A.
- **P(B)**: probabilità marginale (evidenza) di osservare B.

Nel contesto della classificazione, A rappresenta la classe e B le feature osservate.

## Assunzione di indipendenza
Si parla di "naive" (ingenuo) perché il modello assume che tutte le feature siano indipendenti tra loro dato il target. Questa ipotesi raramente è vera nei dati reali, ma semplifica molto i calcoli e spesso produce comunque buoni risultati.

**Punti di forza:** semplicità, velocità, robustezza anche se l’assunzione di indipendenza non è pienamente soddisfatta.

**Limitazioni:** se le feature sono fortemente correlate, le probabilità predette possono essere distorte.

## Varianti

### Gaussian Naive Bayes
Usato quando le feature sono continue e si assume che seguano una distribuzione normale (gaussiana). Esempio: classificazione di dati biometrici.

### Multinomial Naive Bayes
Adatto a feature discrete che rappresentano conteggi, come la frequenza di parole nei documenti (text classification).

### Bernoulli Naive Bayes
Indicato quando le feature sono binarie (0 o 1), ad esempio presenza/assenza di una parola in un documento.

### Complement Naive Bayes
Variante del Multinomial, progettata per gestire meglio classi sbilanciate (unbalanced), spesso usata nel text classification.

### Categorical Naive Bayes
Per feature categoriche non ordinate. Utile quando le variabili non sono numeriche ma categorie distinte.

## Vantaggi e svantaggi

**Vantaggi:**
- Semplice da implementare e interpretare
- Veloce sia nell’addestramento che nella predizione
- Richiede pochi dati per stimare i parametri
- Funziona bene con molte feature
- Robusto al rumore

**Svantaggi:**
- L’assunzione di indipendenza raramente è vera
- Può produrre probabilità poco realistiche se le feature sono correlate
- Non adatto a feature numeriche che non seguono la distribuzione presunta (ad es. non gaussiane nel Gaussian NB)

## Workflow di addestramento

```mermaid
flowchart LR
    A[Preprocessing] --> B[Stima delle probabilità]
    B --> C[Teorema di Bayes]
    C --> D[Predizione]
```

Preprocessing: pulizia e trasformazione dei dati, ad esempio tokenizzazione del testo, normalizzazione dei numeri e encoding delle categorie.

Stima delle probabilità: calcolo delle probabilità a priori delle classi e delle probabilità condizionate delle feature per ciascuna classe.

Applicazione del teorema di Bayes: calcolo della probabilità posteriore per ciascuna classe dato un nuovo esempio.

Predizione: assegnazione della classe con probabilità posteriore più alta.

## Applicazioni
- Filtro antispam (spam filtering)
- Analisi del sentiment
- Classificazione di documenti
- Diagnosi medica automatizzata

## Collegamenti con il Master
Nel corso il Naive Bayes è stato collegato in modo particolare alla classificazione testuale, culminando nell'esercitazione sullo **spam filtering** con il dataset SMS Spam Collection.

Il modulo è collegato anche ad altri algoritmi di classificazione supervisionata:

- **Logistic Regression**, come modello discriminativo lineare;
- **SVM**, come modello geometrico basato su margine;
- **Nearest Neighbors**, come approccio non parametrico basato su distanza.

## Mini-checklist iniziale
- Definizione e ipotesi di base del Naive Bayes
- Formula del teorema di Bayes e significato dei termini
- Differenze tra le varianti principali (Gaussian, Multinomial, Bernoulli, Complement, Categorical)
- Vantaggi e limiti dell’algoritmo
- Applicazioni tipiche
- Fasi principali del workflow di addestramento e predizione

---

## Fondamenti probabilistici

Naive Bayes appartiene alla famiglia dei modelli probabilistici: invece di cercare direttamente un confine decisionale, stima la probabilità che un'osservazione appartenga a ciascuna classe.

Dato un insieme di feature `x = (x1, x2, ..., xn)` e una classe `Ck`, l'obiettivo è calcolare:

```text
P(Ck | x1, x2, ..., xn)
```

La classe predetta è quella con probabilità posteriore massima:

```text
classe_predetta = argmax P(Ck | x1, x2, ..., xn)
```

Applicando il teorema di Bayes:

```text
P(Ck | x) = P(x | Ck) * P(Ck) / P(x)
```

Nel confronto tra classi, `P(x)` è uguale per tutte e può essere ignorato. Il classificatore sceglie quindi la classe che massimizza:

```text
P(x | Ck) * P(Ck)
```

Con l'assunzione naive di indipendenza condizionata:

```text
P(x | Ck) = P(x1 | Ck) * P(x2 | Ck) * ... * P(xn | Ck)
```

Quindi:

```text
P(Ck | x) ∝ P(Ck) * ∏ P(xi | Ck)
```

Questa è la formula operativa alla base del Naive Bayes.

---

## Interpretazione intuitiva

L'intuizione del Naive Bayes è semplice: per classificare un nuovo esempio, il modello guarda quanto ciascuna classe era frequente nel training set e quanto le feature osservate sono compatibili con ciascuna classe.

Nel caso dello spam filtering, ad esempio, il modello impara che alcune parole compaiono spesso nei messaggi spam e raramente nei messaggi legittimi. Quando arriva un nuovo messaggio, calcola quale classe rende più probabile la presenza delle parole osservate.

Esempio intuitivo:

- parole come `free`, `win`, `prize`, `urgent` possono aumentare la probabilità di spam;
- parole più neutre o personali possono aumentare la probabilità di messaggio legittimo.

Il modello non capisce il significato del testo: ragiona statisticamente sulla distribuzione delle parole.

---

## Esempio didattico: classificazione spam/ham

Supponiamo di voler classificare un messaggio come `spam` o `ham`.

Il modello calcola due quantità:

```text
P(spam | messaggio)
P(ham | messaggio)
```

Poi sceglie la classe con probabilità maggiore.

Se il messaggio contiene parole come:

```text
free, win, urgent, prize
```

il modello può assegnare una probabilità più alta alla classe `spam`, perché durante l'addestramento ha osservato che queste parole compaiono più frequentemente nei messaggi indesiderati.

Se invece il messaggio contiene parole comuni in conversazioni personali, la probabilità della classe `ham` può risultare maggiore.

---

## Laplace Smoothing

Un problema classico del Naive Bayes è la probabilità zero.

Se una parola non appare mai nei documenti di una certa classe durante il training, la probabilità condizionata diventa zero:

```text
P(parola | classe) = 0
```

Poiché il modello moltiplica molte probabilità tra loro, una sola probabilità pari a zero annulla l'intero prodotto.

Per evitare questo problema si usa lo **smoothing di Laplace**, che aggiunge una piccola quantità ai conteggi.

Formula concettuale:

```text
P(xi | Ck) = (count(xi, Ck) + α) / (count(Ck) + α * n_features)
```

Dove:

- `α` è il parametro di smoothing;
- `count(xi, Ck)` è il numero di occorrenze della feature `xi` nella classe `Ck`;
- `n_features` è il numero totale di feature.

In scikit-learn il parametro `alpha` controlla proprio questo comportamento.

---

## Probabilità in log-space

Naive Bayes moltiplica molte probabilità piccole. Questo può causare problemi numerici di **underflow**, cioè valori così piccoli da diventare indistinguibili da zero per il computer.

Per questo motivo le implementazioni pratiche lavorano spesso in logaritmi.

Il prodotto diventa una somma:

```text
log(P(Ck) * ∏ P(xi | Ck)) = log(P(Ck)) + Σ log(P(xi | Ck))
```

Questo rende i calcoli più stabili e più efficienti.

---

## Complessità computazionale

Naive Bayes è generalmente molto efficiente.

Durante il training il modello deve stimare:

- le probabilità a priori delle classi;
- le probabilità condizionate delle feature rispetto alle classi.

Durante la predizione deve calcolare, per ogni classe, il prodotto o la somma logaritmica delle probabilità associate alle feature osservate.

Questo rende Naive Bayes particolarmente adatto a:

- dataset testuali;
- classificazione con molte feature;
- problemi in cui serve una baseline rapida;
- scenari in cui il training deve essere molto veloce.

---

## Confronto tra varianti

| Variante | Tipo di feature | Caso d'uso tipico | Note |
|---|---|---|---|
| GaussianNB | Continue | dati numerici continui | assume distribuzione normale |
| MultinomialNB | Conteggi | text classification | ottimo con CountVectorizer |
| BernoulliNB | Binarie | presenza/assenza parole | utile con feature 0/1 |
| ComplementNB | Conteggi sbilanciati | text classification con classi sbilanciate | più robusto su dataset imbalance |
| CategoricalNB | Categoriche | feature discrete non ordinate | richiede categorie codificate |

## Gaussian Naive Bayes

GaussianNB modella ogni feature continua tramite una distribuzione normale per ciascuna classe.

È adatto quando le feature sono numeriche e approssimativamente gaussiane.

Non è la scelta naturale per testi rappresentati come conteggi di parole.

## Multinomial Naive Bayes

MultinomialNB è una delle varianti più usate per la classificazione testuale.

Funziona bene quando le feature rappresentano conteggi, ad esempio quante volte una parola appare in un documento.

È particolarmente adatto insieme a `CountVectorizer`.

## Bernoulli Naive Bayes

BernoulliNB usa feature binarie.

Nel text classification non considera quante volte una parola appare, ma solo se è presente o assente.

È utile quando la presenza di una parola è più informativa della sua frequenza.

## Complement Naive Bayes

ComplementNB è una variante pensata per migliorare la classificazione quando le classi sono sbilanciate.

Nel materiale pratico del Master è stato confrontato con MultinomialNB nel contesto dello spam filtering.

## Categorical Naive Bayes

CategoricalNB è adatto a feature categoriche discrete, ad esempio colore, tipo, categoria, marca o altre variabili non ordinate.

Non è la variante più usata nei problemi testuali, ma completa il quadro delle principali implementazioni disponibili in scikit-learn.

---

## Pratica: Spam filtering con Naive Bayes

Nel Master è stata svolta un'esercitazione pratica di classificazione spam/ham usando un dataset reale di SMS.

Il dataset di riferimento è il **Kaggle SMS Spam Collection**, composto da messaggi testuali etichettati come:

- `ham`: messaggio legittimo;
- `spam`: messaggio indesiderato.

L'obiettivo è addestrare un classificatore capace di distinguere automaticamente i messaggi spam dai messaggi legittimi.

---

## Caricamento e pulizia del dataset

Nel materiale recuperato il dataset viene caricato specificando l'encoding `ISO-8859-1`, perché il file contiene caratteri non sempre compatibili con l'encoding UTF-8 standard.

```python
import pandas as pd

sms = pd.read_csv("spam.csv", encoding="ISO-8859-1")
```

Dopo il caricamento, il dataset contiene colonne aggiuntive non utili. La pulizia consiste nel mantenere solo:

- il testo del messaggio;
- l'etichetta spam/ham.

Esempio:

```python
sms = sms[["v1", "v2"]]
sms.columns = ["label", "message"]
```

Poi si converte la label in formato numerico:

```python
sms["spam"] = sms["label"].map({"ham": 0, "spam": 1})
```

---

## Split train/test

Come nelle altre esercitazioni del Master, il dataset viene diviso in training set e test set.

```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    sms["message"],
    sms["spam"],
    test_size=0.2,
    random_state=0,
    stratify=sms["spam"]
)
```

L'opzione `stratify` è utile perché mantiene proporzioni simili di spam e ham tra train e test.

---

## Rappresentazione del testo

Gli algoritmi di Machine Learning non lavorano direttamente su stringhe di testo. È necessario trasformare i messaggi in vettori numerici.

Nel materiale pratico sono stati usati due approcci principali:

- `HashingVectorizer`;
- `CountVectorizer`.

## CountVectorizer

`CountVectorizer` costruisce un vocabolario e rappresenta ogni messaggio tramite il conteggio delle parole.

```python
from sklearn.feature_extraction.text import CountVectorizer

vectorizer = CountVectorizer()
X_train_vec = vectorizer.fit_transform(X_train)
X_test_vec = vectorizer.transform(X_test)
```

Questa rappresentazione è particolarmente adatta a `MultinomialNB` e `ComplementNB`.

## HashingVectorizer

`HashingVectorizer` trasforma il testo usando una funzione hash invece di costruire esplicitamente un vocabolario.

```python
from sklearn.feature_extraction.text import HashingVectorizer

vectorizer = HashingVectorizer(binary=True, alternate_sign=False)
X_train_vec = vectorizer.transform(X_train)
X_test_vec = vectorizer.transform(X_test)
```

Nel materiale recuperato viene associato in particolare a `BernoulliNB`, usando feature binarie.

## CountVectorizer vs HashingVectorizer

| Aspetto | CountVectorizer | HashingVectorizer |
|---|---|---|
| Vocabolario esplicito | Sì | No |
| Interpretabilità feature | Alta | Bassa |
| Memoria | Può crescere molto | Più stabile |
| Fit necessario | Sì | No |
| Uso tipico nel Master | MultinomialNB / ComplementNB | BernoulliNB |

`CountVectorizer` è più interpretabile perché mantiene una mappa tra parole e colonne della matrice.

`HashingVectorizer` è più adatto a scenari grandi o streaming, ma rende più difficile ispezionare direttamente quali parole corrispondono alle feature.

---

## Multinomial Naive Bayes

```python
from sklearn.naive_bayes import MultinomialNB
from sklearn.metrics import accuracy_score, classification_report

model = MultinomialNB()
model.fit(X_train_vec, y_train)

y_pred = model.predict(X_test_vec)

print("Accuracy:", accuracy_score(y_test, y_pred))
print(classification_report(y_test, y_pred))
```

Nel materiale consolidato, MultinomialNB ottiene risultati molto buoni sullo spam filtering, con accuratezza indicativamente nell'intervallo **0.98-0.99**.

---

## Complement Naive Bayes

```python
from sklearn.naive_bayes import ComplementNB

model = ComplementNB()
model.fit(X_train_vec, y_train)

y_pred = model.predict(X_test_vec)

print("Accuracy:", accuracy_score(y_test, y_pred))
print(classification_report(y_test, y_pred))
```

ComplementNB è utile quando le classi sono sbilanciate. Nel dataset SMS Spam Collection la classe `ham` è molto più frequente della classe `spam`, quindi questa variante è particolarmente interessante.

Nel materiale recuperato ComplementNB raggiunge un'accuratezza leggermente inferiore a MultinomialNB, indicativamente intorno a **0.96**, ma rimane molto valido.

---

## Bernoulli Naive Bayes

```python
from sklearn.feature_extraction.text import HashingVectorizer
from sklearn.naive_bayes import BernoulliNB

vectorizer = HashingVectorizer(binary=True, alternate_sign=False)
X_train_hash = vectorizer.transform(X_train)
X_test_hash = vectorizer.transform(X_test)

model = BernoulliNB()
model.fit(X_train_hash, y_train)

y_pred = model.predict(X_test_hash)
```

BernoulliNB lavora bene quando conta la presenza o assenza delle parole, più che la loro frequenza.

---

## Funzione di inferenza

Un passaggio importante dell'esercitazione consiste nel creare una funzione capace di classificare nuovi messaggi.

```python
def predict_message(message, vectorizer, model):
    message_vec = vectorizer.transform([message])
    prediction = model.predict(message_vec)[0]
    probability = model.predict_proba(message_vec)[0]

    label = "spam" if prediction == 1 else "ham"

    return label, probability
```

Esempio d'uso:

```python
predict_message("Congratulations! You won a free prize", vectorizer, model)
```

Questa funzione rappresenta il passaggio dal modello addestrato ad un uso pratico su nuovi dati.

---

## Confronto pratico tra varianti

| Modello | Vectorizer tipico | Tipo feature | Risultato recuperato |
|---|---|---|---|
| BernoulliNB | HashingVectorizer binary | presenza/assenza | buono |
| MultinomialNB | CountVectorizer | conteggi | circa 0.98-0.99 accuracy |
| ComplementNB | CountVectorizer | conteggi sbilanciati | circa 0.96 accuracy |

Il miglior risultato pratico nel materiale recuperato è associato a **MultinomialNB**, ma ComplementNB rimane importante perché progettato per dataset sbilanciati.

---

## Metriche di valutazione nello spam filtering

Nel caso dello spam filtering non basta osservare l'accuracy.

Il dataset è sbilanciato: i messaggi `ham` sono molti più dei messaggi `spam`.

Per questo motivo è importante valutare anche:

- **precision**: tra i messaggi classificati come spam, quanti erano davvero spam;
- **recall**: tra tutti gli spam reali, quanti sono stati intercettati;
- **F1-score**: media armonica tra precision e recall.

In un filtro antispam reale, entrambi gli errori hanno impatti diversi:

- falso positivo: un messaggio legittimo finisce nello spam;
- falso negativo: uno spam arriva nella posta in arrivo.

---

## Pipeline completa dell'esercitazione

Una pipeline tipica per l'esercitazione del Master è:

```python
from sklearn.pipeline import Pipeline
from sklearn.feature_extraction.text import CountVectorizer
from sklearn.naive_bayes import MultinomialNB
from sklearn.metrics import classification_report

pipeline = Pipeline([
    ("vectorizer", CountVectorizer()),
    ("model", MultinomialNB())
])

pipeline.fit(X_train, y_train)

y_pred = pipeline.predict(X_test)

print(classification_report(y_test, y_pred))
```

Il vantaggio della pipeline è che preprocessing e modello vengono trattati come un unico oggetto.

Questo riduce il rischio di errori, soprattutto quando il modello viene poi usato su nuovi messaggi.

---

## Errori comuni

## Usare GaussianNB su testo vettorializzato come conteggi

GaussianNB non è la scelta naturale per dati testuali rappresentati come conteggi sparsi.

Per text classification sono generalmente più adatti MultinomialNB, BernoulliNB o ComplementNB.

## Dimenticare lo smoothing

Senza smoothing, una parola mai vista in una classe può annullare la probabilità dell'intera classe.

## Confondere CountVectorizer e HashingVectorizer

`CountVectorizer` costruisce un vocabolario esplicito.

`HashingVectorizer` usa una funzione hash e non mantiene un vocabolario interpretabile nello stesso modo.

## Valutare solo l'accuracy

Nel caso dello spam filtering, l'accuracy può essere fuorviante se le classi sono sbilanciate. È importante guardare anche precision, recall e F1-score.

## Applicare `fit_transform` anche sul test set

Il vectorizer deve essere addestrato solo sul training set.

Sul test set bisogna usare `transform`, non `fit_transform`.

Corretto:

```python
X_train_vec = vectorizer.fit_transform(X_train)
X_test_vec = vectorizer.transform(X_test)
```

Errato:

```python
X_test_vec = vectorizer.fit_transform(X_test)
```

Il secondo approccio crea un vocabolario diverso per il test set e invalida la valutazione.

## Ignorare lo sbilanciamento delle classi

Nel dataset SMS Spam Collection i messaggi `ham` sono molti più degli `spam`.

Per questo motivo bisogna leggere con attenzione precision, recall e F1-score, non solo l'accuracy.

---

## Collegamenti con altri algoritmi

## Logistic Regression

La regressione logistica è discriminativa: modella direttamente il confine tra classi.

Naive Bayes è generativo/probabilistico: modella la probabilità delle feature dato ciascuna classe.

## SVM

Le SVM cercano un iperpiano che massimizza il margine tra classi.

Naive Bayes, invece, sceglie la classe più probabile secondo il teorema di Bayes.

## Nearest Neighbors

KNN è non parametrico e lazy: classifica in base alla vicinanza tra esempi.

Naive Bayes apprende invece statistiche aggregate sulle feature e sulle classi.

---

## Quiz di ripasso

## Domanda 1

Su quale teorema si basa Naive Bayes?

**Risposta:** sul teorema di Bayes.

## Domanda 2

Perché l'algoritmo si chiama "naive"?

**Risposta:** perché assume che le feature siano indipendenti tra loro dato il target.

## Domanda 3

Quale variante è tipicamente usata per conteggi di parole?

**Risposta:** Multinomial Naive Bayes.

## Domanda 4

Quale variante è adatta a feature binarie?

**Risposta:** Bernoulli Naive Bayes.

## Domanda 5

A cosa serve lo smoothing di Laplace?

**Risposta:** a evitare probabilità pari a zero per feature mai osservate in una classe.

## Domanda 6

Perché nel text classification si usa spesso MultinomialNB?

**Risposta:** perché lavora bene con feature che rappresentano conteggi, come le frequenze delle parole prodotte da CountVectorizer.

## Domanda 7

Qual è il rischio di una probabilità condizionata pari a zero?

**Risposta:** una sola probabilità zero può annullare il prodotto di tutte le probabilità e rendere impossibile assegnare correttamente una classe.

## Domanda 8

Perché nel filtro antispam è importante guardare precision e recall?

**Risposta:** perché le classi sono sbilanciate e i falsi positivi e falsi negativi hanno conseguenze diverse.

---

## Deeptest

## Domanda 1

Naive Bayes è particolarmente efficace quando:

- A. il numero di feature è elevato;
- B. il dataset contiene solo immagini;
- C. le classi sono sempre perfettamente bilanciate;
- D. non esistono feature categoriche.

**Risposta corretta:** A.

## Domanda 2

L'assunzione principale di Naive Bayes riguarda:

- A. la linearità delle feature;
- B. l'indipendenza condizionata delle feature;
- C. la presenza di kernel;
- D. la distanza euclidea.

**Risposta corretta:** B.

## Domanda 3

Per il text classification con conteggi di parole è spesso adatto:

- A. GaussianNB;
- B. MultinomialNB;
- C. KMeans;
- D. PCA.

**Risposta corretta:** B.

## Domanda 4

ComplementNB è utile soprattutto quando:

- A. le feature sono immagini RGB;
- B. le classi sono sbilanciate;
- C. il modello deve usare un kernel RBF;
- D. non si dispone di label.

**Risposta corretta:** B.

## Domanda 5

Nel filtro antispam, la classe `spam` viene spesso codificata come:

- A. -1;
- B. 0;
- C. 1;
- D. NaN.

**Risposta corretta:** C.

## Domanda 6

Lo smoothing di Laplace serve a:

- A. ridurre la dimensionalità;
- B. evitare probabilità nulle;
- C. normalizzare le feature tra 0 e 1;
- D. calcolare il margine massimo.

**Risposta corretta:** B.

## Domanda 7

Nel text classification, `CountVectorizer` produce:

- A. immagini normalizzate;
- B. coordinate geometriche;
- C. conteggi di parole;
- D. support vectors.

**Risposta corretta:** C.

## Domanda 8

Naive Bayes è spesso efficace nella classificazione testuale perché:

- A. usa sempre reti neurali profonde;
- B. gestisce bene molte feature sparse;
- C. non richiede dati etichettati;
- D. usa distanze euclidee.

**Risposta corretta:** B.

---

## Da ricordare per l'esame

- Naive Bayes è un classificatore probabilistico supervisionato.
- Si basa sul teorema di Bayes.
- L'ipotesi naive è l'indipendenza condizionata delle feature dato il target.
- GaussianNB è adatto a feature continue gaussiane.
- MultinomialNB è adatto a conteggi, soprattutto nel text classification.
- BernoulliNB è adatto a feature binarie.
- ComplementNB è utile con classi sbilanciate.
- CategoricalNB è adatto a feature categoriche discrete.
- Lo smoothing evita probabilità nulle.
- In pratica si lavora spesso in log-space.
- Nel Master Naive Bayes è stato applicato allo spam filtering con SMS Spam Collection.

---

## Checklist finale di padronanza

Alla fine di questo capitolo dovresti saper spiegare:

- perché Naive Bayes è un classificatore probabilistico;
- come si interpreta il teorema di Bayes nel contesto della classificazione;
- perché l'assunzione di indipendenza è detta "naive";
- quando usare GaussianNB, MultinomialNB, BernoulliNB, ComplementNB e CategoricalNB;
- perché MultinomialNB è particolarmente adatto alla classificazione testuale;
- a cosa serve lo smoothing di Laplace;
- perché si usano probabilità in log-space;
- come trasformare testo in feature numeriche con CountVectorizer o HashingVectorizer;
- perché nello spam filtering non basta guardare solo l'accuracy;
- come costruire una pipeline scikit-learn completa per inferenza su nuovi messaggi.

---

## Collegamenti consigliati

Per consolidare Naive Bayes, è utile confrontarlo con:

- **Logistic Regression**: modello discriminativo lineare;
- **SVM**: classificatore geometrico basato su margine;
- **Nearest Neighbors**: modello non parametrico basato su distanza;
- **Decision Tree / Random Forest**: modelli basati su regole e ensemble;
- **MLOps**: fase in cui il modello viene servito, monitorato e aggiornato.

---

## Riepilogo finale

Naive Bayes è un algoritmo semplice, veloce e sorprendentemente efficace. Pur basandosi su un'assunzione forte e spesso irrealistica, funziona molto bene in molti problemi reali, soprattutto nella classificazione testuale.

Nel percorso del Master rappresenta un passaggio importante perché collega probabilità, classificazione supervisionata, preprocessing del testo e valutazione pratica dei modelli.

---

## Stato del recupero

| Sezione | Stato |
|---|:---:|
| Teoria | Completa |
| Varianti | Completa |
| Pratica spam filtering | Recuperata |
| Codice Python | Aggiunto |
| Pipeline scikit-learn | Aggiunta |
| Metriche spam filtering | Aggiunte |
| CountVectorizer vs HashingVectorizer | Aggiunto |
| Quiz | Aggiunti |
| Deeptest | Aggiunti |
| Errori comuni | Aggiunti |
| Collegamenti | Aggiunti |
| Checklist finale | Aggiunta |

**Recovery score stimato:** 99%.

Il contenuto copre la teoria e la pratica consolidate nel materiale del Master. Potrebbero mancare dettagli minori presenti solo in conversazioni non più accessibili integralmente.

---

## Stato editoriale

**Stato:** FINAL 1.0

Il capitolo è considerato chiuso in prima versione definitiva. Eventuali interventi futuri dovrebbero essere solo correzioni puntuali, integrazioni da materiale originale aggiuntivo o aggiornamenti di stile globali del repository.
