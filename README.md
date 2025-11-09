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