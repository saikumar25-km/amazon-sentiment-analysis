
# Sentiment Analysis of Product Reviews

## Project Overview

This project performs **Sentiment Analysis** on product reviews using **Python (NLP)** and **Power BI**.

It processes raw customer reviews, cleans the data, analyzes sentiment, and visualizes insights.

---

##  Tech Stack

* Python (Pandas, NumPy)
* NLP (NLTK, TextBlob)
* Jupyter Notebook
* Power BI

---

##  Dataset Information

* Total Records: 15,000
* Columns:

  * `review_id`
  * `product_name`
  * `review_text`
  * `rating`
  * `review_date`

## Project Output

![Project Screenshot2](https://github.com/saikumar25-km/amazon-sentiment-analysis/blob/main/Screenshot%20(4).png?raw=true)




### 1️⃣ Data Cleaning

* Removed duplicates
* Checked null values

```python
data.duplicated().sum()
data = data.drop_duplicates()
data.isnull().sum()
![Project](https://raw.githubusercontent.com/saikumar25-km/amazon-sentiment-analysis/main/Screenshot%20(5).png)



### 2️⃣ Text Preprocessing

* Lowercase conversion
* Removed punctuation
* Removed stopwords

```python
data.review_text = data.review_text.str.lower()
```

##stopword removing
![stopword](https://github.com/saikumar25-km/amazon-sentiment-analysis/blob/main/Screenshot%20(14).png?raw=true)



### 3️⃣ Sentiment Analysis

Using **TextBlob**

```python
from textblob import TextBlob
data['sentiment_score'] = data['review_text'].apply(lambda x: TextBlob(x).sentiment.polarity)
```

![texb](https://github.com/saikumar25-km/amazon-sentiment-analysis/blob/main/Screenshot%20(15).png?raw=true)



### 4️⃣ Sentiment Classification

```python
def get_sentiment(score):
    if score > 0:
        return "Positive"
    elif score < 0:
        return "Negative"
    else:
        return "Neutral"

data['sentiment'] = data['sentiment_score'].apply(get_sentiment)
```
![catagory](https://github.com/saikumar25-km/amazon-sentiment-analysis/blob/main/Screenshot%20(16).png?raw=true)
---

## 📊 Results

* Positive: **9125**
* Negative: **3369**
* Neutral: **2506**

---

## 📸 Project Screenshots

> ⚠️ Upload your images into a folder named `images/` in your repo.

---

### 🔹 Power BI Dashboard

![Sentiment Comparison](<img width="1920" height="1080" alt="Screenshot (4)" src="https://github.com/user-attachments/assets/4dc53c00-e0a3-4a0b-8ed5-d758fad0a974" />
)

---

### 🔹 Product-wise Sentiment

![image alt](]([https://raw.githubusercontent.com/saikumar25-km/amazon-sentiment-analysis/main/Screenshot%20(5).png])

---

### 🔹 Data Cleaning (Jupyter)

![Data Cleaning](.png)

---

### 🔹 Text Preprocessing

![Text Processing](images/text_processing.png)

---

### 🔹 Stopwords Removal

![Stopwords](images/stopwords.png)

---

### 🔹 Sentiment Score Calculation

![Sentiment Score](images/sentiment_score.png)

---

###  Final Output

![Final Output](images/final_output.png)

---

##  Insights

* Most reviews are **Positive**
* Apple iPad has highest reviews
* Negative reviews highlight product issues

---

## 🔮 Future Improvements

* Use advanced models (BERT, Transformers)
* Deploy as Web App
* Real-time sentiment analysis
