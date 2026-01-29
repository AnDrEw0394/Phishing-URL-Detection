# Phishing URL Detection

## Descrizione del Progetto

"Phishing URL Detection" è un progetto di intelligenza artificiale focalizzato sullo sviluppo di un approccio migliore rispetto a quello di uno studio scelto già pubblicato, per risolvere un task di ML. Esso si basa sull'utilizzo del Machine Learning ed è focalizzato sullo sviluppo di un sistema in grado di distinguere URL legittimi da siti di phishing. A differenza degli approcci basati su semplici "blacklist", questo progetto analizza le caratteristiche strutturali e lessicali dell'URL per identificare minacce anche mai viste prima.
Il progetto pone un'enfasi particolare sulla pulizia dei dati (rilevamento di *Data Leakage*) e sull'explainability, confrontando le logiche decisionali di un singolo Albero Decisionale rispetto a una Random Forest.

## Struttura del Progetto

La documentazione del progetto e il codice sono strutturati nel seguente modo:

### 1. Introduzione
Il progetto inizia con un'analisi del fenomeno del Phishing moderno, spiegando perché i vecchi metodi di rilevamento non bastano più (es. molti siti di phishing oggi usano protocolli HTTPS sicuri) e come il Machine Learning possa offrire una soluzione dinamica.

### 2. Data Understanding and Data Preparation
* **Data Gathering:** I dati utilizzati provengono dal dataset **PhiUSIIL Phishing URL Dataset** (UCI Machine Learning Repository), contenente oltre 235.000 istanze.
* **Data Examination:** Analisi delle 56 feature iniziali.
* **Data Cleaning:** Rimozione di duplicati e feature testuali non elaborabili.
* **Analisi Data Leakage:** Individuazione e rimozione della feature critica `URLSimilarityIndex`, che falsava i risultati portando a un'accuratezza irrealistica del 100%.

### 3. Sviluppo del Modello
* **Scelta del Classificatore:** Confronto tra un modello semplice e interpretabile (**Decision Tree**) e un modello ensemble più robusto (**Random Forest**).
* **Implementazione:** Utilizzo della libreria Scikit-Learn per l'addestramento e l'ottimizzazione degli iperparametri (es. profondità degli alberi).

### 4. Training e Valutazione
* **Metriche di Valutazione:** Utilizzo di Accuracy, Precision, Recall e Matrice di Confusione per misurare le performance.
* **Valutazione dei Modelli:** Il modello finale (Random Forest) ha raggiunto un'accuratezza del **99.99%** sul test set, dimostrando una capacità di generalizzazione superiore rispetto al singolo albero.

### 5. Explainability dei Modelli Implementati
* **Feature Importance:** Analisi di quali caratteristiche l'IA ritiene più sospette.
* **Confronto:** Si evidenzia come il modello Random Forest dia più peso alla struttura della pagina (`LineOfCode`, `NoOfImage`) piuttosto che ai soli riferimenti esterni, comprendendo meglio la natura "vuota" dei siti di phishing.

### 6. Conclusioni
* **Risultati Finali:** Sintesi dei risultati ottenuti e discussione su come il modello possa essere integrato in sistemi di difesa reali.
* **Repository:** Questa repository contiene i Notebook Jupyter con l'analisi passo-passo e il modello addestrato salvato in formato `.pkl`.

## Installazione

Per utilizzare questo progetto, segui i passaggi seguenti:

1. Clona il repository:
   git clone [https://github.com/AnDrEw0394/Phishing-URL-Detection.git](https://github.com/AnDrEw0394/Phishing-URL-Detection.git)

2. Installa le dipendenze:
   pip install -r requirements.txt

## Riferimenti

Il dataset utilizzato per questo progetto è reperibile al seguente link ufficiale UCI:
[PhiUSIIL Phishing URL Dataset (UCI Machine Learning Repository)](https://archive.ics.uci.edu/dataset/967/phiusiil+phishing+url+dataset)

## Autore
Zeno Andrea, studente dell'Università di Salerno - Corso di Machine Learning