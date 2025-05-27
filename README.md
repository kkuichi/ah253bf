## Téma práce: **Analýza dynamického vývoja toxicity na sociálnych sieťach**

Cieľom tejto práce bola analýza dynamiky šírenia dezinformácií na sociálnych sieťach s využitím jazykových modelov ako **BERT**, **BertForSequenceClassification** a **RoBERTa**. Práca zahŕňa aj porovnanie modelov z hľadiska ich vysvetliteľnosti pomocou metrík a konfúznej matice. Okrem toho bola vizualizovaná časová dynamika šírenia falošných príspevkov počas pandémie COVID-19.

### Použitý dataset č.1: **Covid\_fake\_news (Hugging Face)**

Na trénovanie, validáciu a testovanie modelov bol použitý verejne dostupný dataset Covid_fake_news z platformy Hugging Face, ktorý už bol rozdelený do množín. Dataset obsahuje texty tweetov označené ako fake alebo real.

#### Základné informácie:

* **Zdroj:** Hugging Face Datasets
* **Formát:** CSV
* **Tréningová množina:** 6420 vzoriek
* **Validačná množina:** 2140 vzoriek
* **Testovacia množina:** 2140 vzoriek

#### Stĺpce:

* `id` – identifikátor exemplára
* `text` – text tweetu
* `label` – označenie (fake/real)

#### Štruktúra súborov:

* `train.csv` – tréningová množina
* `val.csv` – validačná množina
* `test.csv` – testovacia množina

### Použitý dataset č.2: **245K Tweets of COVID-19 (Kaggle)**

Na analýzu dynamiky šírenia falošných správ modelmi bol použitý dostupný dataset 245K Tweets of COVID-19 z platformy Kaggle, ktorý zahŕňa dátový rozsah počas pandémie.

#### Základné informácie:

* **Zdroj:** Kaggle
* **Formát:** CSV
* **Veľkosť:** 245 000 vzoriek

#### Stĺpce:

* `id` – identifikátor
* `content` – text tweetu
* `date` – dátum publikácie

#### Štruktúra súborov:

* `245_tweets.csv` – celý dataset tweetov

### Jupyter súbory a ich obsah

* **`BERT.ipynb`** – trénovanie modelu BERT (príprava dát, tokenizácia, tréning, validácia, uloženie modelu)
* **`bert_sequenceclassification.ipynb`** – trénovanie BertForSequenceClassification
* **`RoBERT.ipynb`** – trénovanie modelu RoBERTa
* **`bert_test.ipynb`** – testovanie modelu BERT a výpočet metrík
* **`bertseqclas_test.ipynb`** – testovanie BertForSequenceClassification
* **`robert_test.ipynb`** – predikcia a hodnotenie RoBERTa
* **`bert_dynamic.ipynb`** – predikcia BERT + vizualizácia šírenia v čase
* **`bertseqclas_dynamic.ipynb`** – predikcia BertForSequenceClassification + vizualizácia
* **`robert_dynamic.ipynb`** – časová analýza modelu RoBERTa

### Použité technológie a knižnice

Projekt bol implementovaný v **Python 3.10.11**. Na spracovanie dát, trénovanie modelov a vizualizácie boli použité nasledujúce knižnice:

| Knižnica       | Verzia | Popis                                |
| -------------- | ------ | ------------------------------------ |
| `pandas`       | 2.2.3  | Práca s dátami                       |
| `numpy`        | 1.24.3 | Numerické výpočty                    |
| `matplotlib`   | 3.10.1 | Vizualizácia grafov                  |
| `seaborn`      | 0.13.2 | Vizualizácia (matica zámen a pod.)   |
| `torch`        | 2.6.0  | Tréning neurónových sietí            |
| `transformers` | 4.50.1 | Predpripravené modely BERT a RoBERTa |
| `sklearn`      | 1.6.1  | Vyhodnocovanie modelov, metriky      |
| `re`           | 2.2.1  | Regulárne výrazy                     |
