
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

## 📂 Dataset Information

* Total Records: 15,000
* Columns:

  * `review_id`
  * `product_name`
  * `review_text`
  * `rating`
  * `review_date`

---

##  Workflow

### 1️⃣ Data Cleaning

* Removed duplicates
* Checked null values

```python
data.duplicated().sum()
data = data.drop_duplicates()
data.isnull().sum()



---

### 2️⃣ Text Preprocessing

* Lowercase conversion
* Removed punctuation
* Removed stopwords

```python
data.review_text = data.review_text.str.lower()
```

---

### 3️⃣ Sentiment Analysis

Using **TextBlob**

```python
from textblob import TextBlob
data['sentiment_score'] = data['review_text'].apply(lambda x: TextBlob(x).sentiment.polarity)
```

---

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

![Sentiment Comparison](images/powerbi_dashboard.png)

---

### 🔹 Product-wise Sentiment

![Product Sentiment](images/product_sentiment.png)

---

### 🔹 Data Cleaning (Jupyter)

![Data Cleaning](images/data_cleaning.png)

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

### 🔹 Final Output

![Final Output](images/final_output.png)

---

## 📈 Insights

* Most reviews are **Positive**
* Apple iPad has highest reviews
* Negative reviews highlight product issues

---

## 🔮 Future Improvements

* Use advanced models (BERT, Transformers)
* Deploy as Web App
* Real-time sentiment analysis

---

## 👨‍💻 Author

**Karthikeya Gundu**

---

# ⚠️ IMPORTANT (VERY IMPORTANT STEP)

You MUST do this:

1. Create folder:

```
images/
```

2. Rename your screenshots like:

```
powerbi_dashboard.png
product_sentiment.png
data_cleaning.png
text_processing.png
stopwords.png
sentiment_score.png
final_output.png
```

3. Upload them to GitHub repo inside `images/`

---

## 💥 Want Next Level?

I can:
✅ Convert this into **LinkedIn post + GitHub repo description**
✅ Create **project PPT (with diagrams)**
✅ Make **resume points from this project**

Just tell me 👍
