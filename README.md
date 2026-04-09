
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


### 1️ Data Cleaning

* Removed duplicates
* Checked null values

```python
data.duplicated().sum()
data = data.drop_duplicates()
data.isnull().sum()


### 2️⃣ Text Preprocessing

* Lowercase conversion
* Removed punctuation
* Removed stopwords
![proces1s](https://github.com/saikumar25-km/amazon-sentiment-analysis/blob/main/Screenshot%20(11).png?raw=true)



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

overview of positive ,negative and netural
![over_all](https://github.com/saikumar25-km/amazon-sentiment-analysis/blob/main/Screenshot%20(47).png?raw=true)


* Real-time sentiment analysis





##positive overall
![image](https://github.com/saikumar25-km/amazon-sentiment-analysis/blob/main/Screenshot%20(27).png?raw=true)





#negative overall

![nagive](https://github.com/saikumar25-km/amazon-sentiment-analysis/blob/main/Screenshot%20(28).png?raw=true)





#ipad overall view
![ipa](https://github.com/saikumar25-km/amazon-sentiment-analysis/blob/main/Screenshot%20(40).png?raw=true)






#sumsag overall view
![samsung](https://github.com/saikumar25-km/amazon-sentiment-analysis/blob/main/Screenshot%20(35).png?raw=true)





#oneplus overall view

![onepluse](https://github.com/saikumar25-km/amazon-sentiment-analysis/blob/main/Screenshot%20(36).png?raw=true)
