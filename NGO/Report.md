# 📊 Clustering & PCA - Analisi dei Paesi in via di Sviluppo

## 📝 Obiettivo

L'International Humanitarian NGO ha recentemente raccolto circa **10 milioni di dollari**.  
Il CEO dell'organizzazione deve decidere **come allocare questi fondi in modo strategico ed efficace**.

Il nostro compito, in qualità di **Data Analyst**, è:

- Classificare i paesi in base a **fattori socio-economici e sanitari**.
- Identificare i paesi che necessitano maggiormente di aiuti.
- Fornire una lista prioritaria su cui focalizzare gli investimenti umanitari.

---

## 📂 Struttura del Dataset

Il dataset comprende **167 paesi** e le seguenti variabili:

| **Colonna**  | **Descrizione**                                    |
| ------------ | -------------------------------------------------- |
| `country`    | Nome del paese                                     |
| `child_mort` | Morti infantili sotto i 5 anni ogni 1000 nati vivi |
| `exports`    | Esportazioni di beni e servizi (in % del PIL)      |
| `health`     | Spesa sanitaria totale (in % del PIL)              |
| `imports`    | Importazioni di beni e servizi (in % del PIL)      |
| `income`     | Reddito netto pro capite                           |
| `inflation`  | Tasso di crescita annuale del PIL                  |
| `life_expec` | Aspettativa di vita alla nascita                   |
| `total_fer`  | Numero medio di figli per donna                    |
| `gdpp`       | PIL pro capite (PIL totale / popolazione)          |

Esempio dei dati:

| **Paese**           | **Child Mort** | **Exports** | **Health** | **Imports** | **Income** | **Inflation** | **Life Expec** | **Total Fer** | **GDP per capita** |
| ------------------- | -------------- | ----------- | ---------- | ----------- | ---------- | ------------- | -------------- | ------------- | ------------------ |
| Afghanistan         | 90.2           | 10.0        | 7.58       | 44.9        | 1610       | 9.44          | 56.2           | 5.82          | 553                |
| Albania             | 16.6           | 28.0        | 6.55       | 48.6        | 9930       | 4.49          | 76.3           | 1.65          | 4090               |
| Algeria             | 27.3           | 38.4        | 4.17       | 31.4        | 12900      | 16.10         | 76.5           | 2.89          | 4460               |
| Angola              | 119.0          | 62.3        | 2.85       | 42.9        | 5900       | 22.40         | 60.1           | 6.16          | 3530               |
| Antigua and Barbuda | 10.3           | 45.5        | 6.03       | 58.9        | 19100      | 1.44          | 76.8           | 2.13          | 12200              |

---

## 📈 Analisi Preliminare

Sono stati prodotti **istogrammi** e **boxplot** per analizzare la distribuzione delle variabili:

<img src="HistMulti.png" alt="Istogrammi" width="100%">

<img src="BoxMulti.png" alt="Boxplot" width="100%">

Dalle analisi esplorative si osserva:

- Presenza di **code lunghe** nelle distribuzioni, soprattutto per le variabili:
  - `income`
  - `inflation`
  - `gdpp`
  - (in misura minore) `exports`
- Queste asimmetrie sono probabilmente dovute al fatto che si considerano una moltitudine di paesi che differiscono per popolazione e, soprattutto, per grado di sviluppo economico. Infatti, a prima vista, si possono notare tra gli outlier superiori in `income` paesi come Qatar, Luxemburg, USA e altri paesi con una forte concentrazione di capitale, stesso vale per `gdpp`e `import`.

---

## 🔍 Tecniche Utilizzate

Sono state applicate due tecniche fondamentali:

- **PCA (Principal Component Analysis)**: per ridurre la dimensionalità e sintetizzare le informazioni.
- **Cluster Analysis**: per raggruppare i paesi secondo uno score di sviluppo socio-economico.

Il risultato dell'analisi ha permesso di distinguere **due gruppi principali**:

- **Paesi ad alto sviluppo socio-economico**
- **Paesi a basso sviluppo socio-economico**

<img src="Cluster.png" alt="Cluster" width="100%">

---

## 🌍 Classifica dei Paesi più Bisognosi

Dai cluster ottenuti, è stata ricavata la **Top 10 dei paesi con il punteggio di sviluppo più basso**, che quindi necessitano **priorità negli aiuti**:

| **Posizione** | **Paese**                | **Punteggio** |
| ------------- | ------------------------ | ------------- |
| 1°            | Nigeria                  | 3.336         |
| 2°            | Haiti                    | 3.009         |
| 3°            | Central African Republic | 2.719         |
| 4°            | Chad                     | 2.454         |
| 5°            | Niger                    | 2.384         |
| 6°            | Mali                     | 2.359         |
| 7°            | Sierra Leone             | 2.339         |
| 8°            | Congo, Dem. Rep.         | 2.204         |
| 9°            | Burkina Faso             | 2.170         |
| 10°           | Malawi                   | 2.078         |

---

## ✅ Conclusione

Dall'analisi emerge chiaramente che **la Nigeria** è il paese con il **maggior bisogno di aiuti umanitari**.  
Il gruppo dei primi 10 paesi rappresenta la fascia più vulnerabile a livello globale e costituisce un **target prioritario** per l’utilizzo strategico dei fondi raccolti.

---
