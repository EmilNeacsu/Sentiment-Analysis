# 📘 Reddit Sentiment & Engagement Analysis

## 🔎 Project Overview
This project explores the relationship between **sentiment** and **engagement** on Reddit.  
Using **NLTK**, **VADER**, and **TextBlob**, it classifies posts as **positive**, **neutral**, or **negative** and analyzes how these categories correlate with engagement metrics such as **Reddit score** and **number of comments**.

The goal is to provide a lightweight, explainable sentiment analysis pipeline for English text, and to visualize insights into how sentiment may influence user interaction.

---

## 🧰 Key Features
- **Text Preprocessing**
  - Removes URLs, user mentions (`u/`), subreddit references (`r/`), and non-alphanumeric characters.
  - Cleans whitespace and prepares text for analysis.

- **Sentiment Analysis**
  - Combines **VADER** (lexicon-based sentiment scoring) and **TextBlob** (polarity/subjectivity).
  - Weighted scoring approach:
    ```
    final_score = 0.6 * vader_compound + 0.4 * textblob_polarity
    ```
  - Labels:
    - Positive (`> 0.1`)
    - Negative (`< -0.1`)
    - Neutral (otherwise)
  - Confidence score based on absolute polarity.

- **Exploratory Data Analysis**
  - Histograms for Reddit scores and comments.
  - Boxplots linking **sentiment vs. engagement** (with outlier filtering for clarity).
  - Correlation analysis between sentiment and engagement metrics.

- **Output**
  - Saves enriched dataset with:
    - VADER scores (`compound`, `pos`, `neg`, `neu`)
    - TextBlob polarity & subjectivity
    - Final sentiment label & confidence
    - Text length

---

## 📊 Insights & Observations
- Reddit engagement metrics are **highly skewed**, with a small number of posts gaining massive traction while most remain low-engagement.  
- After filtering outliers, **sentiment vs. engagement relationships** became much clearer. Neutral content often dominated, while strongly negative posts sometimes generated intense discussions.  
- During the **UEFA Champions League**, spikes in both positive and negative sentiment were observed around big matches.  
  - Posts celebrating victories received strong **positive sentiment** and high engagement.  
  - Posts about referee mistakes or defeats generated **negative sentiment** but equally high comment activity.  
- This highlights that both **positive and negative emotions drive engagement**, but in different ways.  

**Conclusions:**
- Sentiment polarity alone does not predict engagement, but extreme emotions (positive or negative) tend to spark more interaction.  
- Sports-related discussions (e.g., Champions League) are excellent case studies where sentiment volatility leads to highly dynamic engagement patterns.  
- A balanced mix of sentiment analysis and domain context (e.g., football events) provides the richest insights.

---

## ⚙️ Requirements
- Python 3.8+
- Jupyter Notebook

**Dependencies:**
- `pandas`, `numpy`
- `nltk`, `vaderSentiment`, `textblob`
- `matplotlib`, `seaborn`

Install with:
```bash
pip install pandas numpy nltk vaderSentiment textblob matplotlib seaborn
