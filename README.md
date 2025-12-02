# 📊 YouTube Video Engagement Analysis & Prediction

## 📖 Abstract
Questo progetto universitario analizza le dinamiche di **Engagement** (coinvolgimento) dei video sulla piattaforma YouTube. Attraverso un approccio *data-driven*, l'analisi mira a identificare quali caratteristiche (durata, categoria, metriche di interazione) rendono un video "di successo" rispetto alla media, segmentando i contenuti e costruendo un modello predittivo.

## 🎯 Motivazione e Obiettivi
In un ecosistema saturo di contenuti come YouTube, capire cosa spinge l'algoritmo e l'interesse degli utenti è fondamentale per i content creator. L'obiettivo di questo progetto è duplice:
1. **Analitico:** Comprendere *quali fattori* influenzano maggiormente le visualizzazioni e i like. La durata conta? La definizione HD è determinante?
2. **Strategico:** Fornire strumenti (cluster e modelli predittivi) per stimare se un video avrà un alto tasso di coinvolgimento (High Engagement) basandosi sulle sue caratteristiche tecniche.

## 📂 Struttura del Progetto

```text
youtube-engagement-analysis/
├── data/
│   └── youtube_recommendation_dataset -.csv  # Dataset originale
├── notebooks/
│   └── youtube_analysis.ipynb                # Notebook principale con l'intera analisi
├── requirements.txt                          # Dipendenze Python
└── README.md                                 # Documentazione del progetto
```

## ⚙️ Metodologia
Il progetto segue un flusso di lavoro strutturato in 4 fasi principali:

1. Data Cleaning & Preprocessing
Gestione delle date (published_at) per calcolare l'età del video.

Encoding delle variabili categoriche (es. caption da Booleano a Binario, definition da testo a numerico).

Variabile Target: Definizione di "Video di Successo" basata sul superamento della mediana dell'engagement_rate.

2. Exploratory Data Analysis (EDA)
Analisi della correlazione tra metriche (es. Like vs Views vs Commenti).

Studio della distribuzione dei video per Categoria.

Visualizzazione avanzata con Seaborn (Heatmaps) e Matplotlib.

3. Content Segmentation (Clustering)
Utilizzo dell'algoritmo K-Means per raggruppare i video in tipologie omogenee.

Determinazione del numero ottimale di cluster tramite Elbow Method (risultato ottimale: k=3).

Profilazione dei cluster basata su duration_seconds (lunghezza) e view_count (popolarità), identificando gruppi come "Video Virali", "Standard" e "Nicchia Long-form".

4. Modellazione Predittiva (Classification)
Addestramento di un modello di Logistic Regression.

Obiettivo: Predire se un video sarà "High Engagement" (1) o "Low Engagement" (0).

Valutazione tramite Accuracy, Confusion Matrix e Classification Report.

Analisi della Feature Importance per capire quali variabili pesano di più sul successo.

## 🔑 Risultati Chiave
Dall'analisi sono emersi i seguenti insight:

Accuratezza del Modello: La Logistic Regression prevede il successo del video con un'accuratezza dell'83%.

Fattore Chiave (Likes): Il numero di like_count è il predittore più forte e positivo per l'engagement rate.

Visualizzazioni vs Engagement: Un alto numero di visualizzazioni (view_count) non garantisce automaticamente un alto engagement rate; spesso video virali hanno molte view ma bassa interazione proporzionale.

Cluster: Sono stati individuati 3 cluster distinti, dove i video brevi tendono ad avere dinamiche di interazione drasticamente diverse dai video lunghi.

## 🚀 Installazione e Utilizzo
Per eseguire il progetto in locale:

Clona la repository (o scarica la cartella):

Bash

git clone <repository-url>
cd youtube-engagement-analysis
Crea un ambiente virtuale (opzionale ma consigliato):

Bash

python -m venv venv
# Windows
venv\Scripts\activate
# Mac/Linux
source venv/bin/activate
Installa le dipendenze:

Bash

pip install -r requirements.txt
Avvia Jupyter Notebook:

Bash

jupyter notebook
Apri il file notebooks/youtube_analysis.ipynb ed esegui le celle sequenzialmente.

## 🛠️ Tecnologie Utilizzate
Python: Linguaggio principale.

Pandas & NumPy: Manipolazione dati e calcolo vettoriale.

Matplotlib & Seaborn: Visualizzazione dati e grafici statistici.

Scikit-Learn: Machine Learning (K-Means, Logistic Regression, Preprocessing, Metrics).
