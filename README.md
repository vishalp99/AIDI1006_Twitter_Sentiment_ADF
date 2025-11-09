# Sentiment Analysis with TextBlob and SQL Server Integration

This project performs **Sentiment Analysis** on text data fetched directly from an **Azure SQL Database** using **Python and TextBlob**. It compares TextBlob’s predicted sentiments with actual sentiment labels stored in the database and visualizes the results for easy interpretation.

---

## Features

- Connects to an **Azure SQL Database** securely using ODBC.
- Fetches live data with columns:
  - `clean_text` → preprocessed text.
  - `category` → sentiment labels (`-1 = Negative`, `0 = Neutral`, `1 = Positive`).
- Performs **sentiment polarity analysis** using TextBlob.
- Visualizes:
  - Bar chart comparison of predicted vs actual sentiments.
  - Distribution plots to understand sentiment bias.
- Provides clean, reproducible results for sentiment evaluation.

---


## Project Structure

```bash
Sentiment-Analysis-TextBlob
├── sentiment_analysis.ipynb   # Jupyter notebook with all analysis
├── requirements.txt            # Required dependencies
├── README.md                   # Project documentation
└── images/                     # (Optional) Folder for generated plots
```

---

## Setup Instructions

```bash
# 1️ Clone the repository
git clone <git repo> 
cd Sentiment-Analysis-TextBlob


# 2️ Create and activate a virtual environment (Python venv)
python -m venv venv
source venv/bin/activate     # On Mac/Linux
venv\Scripts\activate        # On Windows

# OR using Conda
conda create -n sentiment_env python=3.11 -y
conda activate sentiment_env

# 3️ Install dependencies
pip install -r requirements.txt

# 4️ Launch Jupyter Notebook
jupyter notebook sentiment_analysis.ipynb

```

---
## Steps Performed

### 1️ Data Acquisition
- Used a Twitter sentiment dataset from Kaggle.  
- Data was cleaned and stored in **Azure SQL Database** using **Azure Data Factory (ADF) pipelines**.

### 2️ Data Processing
- Connected to Azure SQL using `pyodbc` in **Jupyter Notebook (Anaconda)**.  
- Loaded tweets and applied **TextBlob** for sentiment classification.  
- Generated a new column `textblob_category`:
  - `1` → Positive  
  - `0` → Neutral  
  - `-1` → Negative

### 3️ Data Storage
- Created a new SQL table `dbo.twitter_results` to store analyzed results.  
- Used Python scripts to insert processed data back into the database.

### 4️ Visualization
- Built dashboards in **Power BI** showing:
  - Distribution of Positive, Neutral, and Negative tweets  
  - Comparison between original and TextBlob sentiments  
  - Word clouds for each sentiment category

### 5️ Evaluation
- Compared TextBlob sentiment results with original labels from the dataset.  
- Discussed performance limitations due to the short-text nature of tweets.

---

## Technologies Used

| Component           | Tool / Library                         |
|--------------------|---------------------------------------|
| Cloud Platform      | Microsoft Azure                        |
| Database            | Azure SQL Database                      |
| Data Ingestion      | Azure Data Factory                      |
| Programming Language| Python 3                                |
| NLP Library         | TextBlob                                |
| Visualization       | Power BI / Matplotlib / Seaborn        |
| IDE                 | Jupyter Notebook (Anaconda)            |

---
