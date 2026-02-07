# Customer Feedback NLP Analysis

NLP-powered analysis of banking customer reviews using topic modeling and sentiment classification to uncover key themes and satisfaction patterns.

## 📊 Project Overview

This project analyzes customer feedback from multiple channels (websites, mobile apps, social media) to extract actionable insights about customer satisfaction. Using Natural Language Processing techniques, we identify main discussion topics and classify sentiment to guide business decisions.

**Key Achievements:**
- **8 distinct topics** identified with 0.77 coherence score
- **76% sentiment classification accuracy** (F1 score)
- Discovered critical themes: mobile app, interest rates, inflation concerns, call center experiences

## 🎯 Business Problem

**Objective:** Extract meaningful insights from unstructured customer feedback

**Two-Fold Approach:**
1. **Topic Clustering:** Identify main themes discussed in reviews using LDA
2. **Sentiment Classification:** Classify reviews as positive, negative, or neutral

**Impact:** Enable data-driven decisions to improve products, services, and customer experience

## 📁 Repository Structure
```
├── notebook/
│   └── NLP_Analysis.ipynb           # Complete analysis workflow
├── data/
│   └── reviews.json                 # Customer reviews dataset
├── report/
│   └── NLP_Analysis.pdf            # Detailed technical report
├── requirements.txt                 # Python dependencies
└── README.md
```

## 🔍 Dataset Features

- **datetime:** Timestamp of review submission
- **review:** Customer feedback text
- **rating:** Numerical rating (1-5 scale)
- **agent_response:** Customer service response (if any)
- **review_id:** Unique identifier

**Dataset Characteristics:**
- **389 reviews** collected over 6 months
- **Rating distribution:** 32% rated 5 stars, 22% rated 1 star
- **Temporal insights:** January had lowest avg rating, February had highest volume

## 🛠️ Technologies Used

**Python 3.x** with libraries:
- **NLP:** NLTK, Gensim
- **ML:** Scikit-learn, LazyPredict
- **Data:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn, WordCloud

## 📈 Methodology

### Part 1: Text Preprocessing

**Cleaning Pipeline:**
1. Emoji removal
2. Contraction expansion
3. Punctuation removal & lowercasing
4. Tokenization (NLTK)
5. Stop word removal
6. Lemmatization (WordNetLemmatizer)
7. Domain-specific word filtering ("bank", "would", "really", etc.)

### Part 2: Topic Clustering (Unsupervised Learning)

**Technique:** Latent Dirichlet Allocation (LDA)

**Process:**
1. Count Vectorization (BoW representation)
2. Corpus generation for Gensim
3. LDA model training with 8 topics
4. Topic assignment & probability analysis

**Topics Identified:**
- **Topic 1:** Loan services & rates
- **Topic 2:** Mobile banking app
- **Topic 3:** Notifications & transactions
- **Topic 4:** Account savings & push notifications
- **Topic 5:** App issues & customer service
- **Topic 6:** App features & payments
- **Topic 7:** Loan installments & failed transactions
- **Topic 8:** Inflation & banking support

### Part 3: Sentiment Classification (Supervised Learning)

**Label Strategy:**
- Ratings 1-2 → "bad"
- Rating 3 → "ok"  
- Ratings 4-5 → "good"

**Models Evaluated:**
- SGDClassifier (best F1 score: 0.76)
- Logistic Regression (F1: 0.76)
- Random Forest, SVM, others via LazyClassifier

**Feature Extraction:** CountVectorizer (bag-of-words)

## 📊 Results

### Topic Modeling Performance

| Metric | Score |
|--------|-------|
| **Coherence Score (c_v)** | **0.77** |
| **Number of Topics** | 8 |
| **Avg Topic Probability** | >0.70 (7 out of 8 topics) |

**Key Finding:** Most reviews belong to Topic 0 (general service feedback), while Topic 2 (mobile app) has fewer but highly focused reviews.

### Sentiment Classification Performance

| Model | Accuracy | Precision | Recall | F1 Score |
|-------|----------|-----------|--------|----------|
| **SGDClassifier** | **76%** | 0.74 | 0.76 | **0.76** |
| Logistic Regression | 76% | 0.74 | 0.75 | 0.76 |

**Class-wise Performance (SGDClassifier):**
- "bad": 32 correct predictions, 11 misclassifications
- "good": 25 correct predictions, 9 misclassifications  
- "ok": 2 correct predictions, 6 misclassifications

### Key Customer Insights

**Top Keywords Across All Reviews:**
- Mobile app
- Interest rates
- Inflation
- Call center
- Service quality
- Notifications

**Temporal Patterns:**
- **January:** Lowest avg rating (potential service issues)
- **February:** Highest review volume (increased engagement)

## 💡 Business Recommendations

1. **Mobile App Improvement:** Most discussed topic - prioritize UX/UI enhancements
2. **Rate Communication:** Address customer concerns about interest rates and inflation impact
3. **Call Center Training:** Improve response quality based on negative feedback
4. **January Investigation:** Identify root causes of January satisfaction drop
5. **Notification Optimization:** Customers mention push notifications frequently - refine strategy

## 🚀 Future Enhancements

- Implement **ordinal classification models** (respects rating order: bad < ok < good)
- Explore **transformer models** (BERT, GPT) for improved sentiment accuracy
- Add **aspect-based sentiment analysis** (sentiment per topic)
- Automate **topic coherence optimization** (find optimal number of topics)
- Implement **temporal analysis** (track topic/sentiment trends over time)
- Deploy as **real-time feedback analysis API**

## 📖 How to Use

### Installation
```bash
# Clone repository
git clone https://github.com/YOUR_USERNAME/customer-feedback-nlp-analysis.git
cd customer-feedback-nlp-analysis

# Install dependencies
pip install -r requirements.txt

# Download NLTK data
python -c "import nltk; nltk.download('punkt'); nltk.download('stopwords'); nltk.download('wordnet')"

# Launch Jupyter Notebook
jupyter notebook notebook/NLP_Analysis.ipynb
```

### Running the Analysis

1. Open `NLP_Analysis.ipynb`
2. Run cells sequentially
3. Review visualizations:
   - Topic word clouds
   - Sentiment distribution
   - Rating trends
   - Model confusion matrices
4. Check `report/NLP_Analysis.pdf` for detailed methodology

## 📄 Detailed Report

For comprehensive analysis including:
- Complete methodology
- All visualizations
- Statistical analysis
- Model comparison details

See [`report/NLP_Analysis.pdf`](report/NLP_Analysis.pdf)

## 👤 Author

**Thanos Paidoulias**
- Data Scientist specializing in Marketing Analytics & NLP
- GitHub: [@https://github.com/ThanosPaidoulias]
- LinkedIn: [https://www.linkedin.com/in/thanos-paidoulias/]

## 📝 License

This project is open source and available for educational purposes.

## 🏆 Highlights

- ✅ Dual NLP approach (unsupervised + supervised)
- ✅ Real-world banking customer data
- ✅ Interpretable results with word clouds
- ✅ Production-ready preprocessing pipeline
- ✅ Model comparison & selection framework

---

⭐ If you found this analysis insightful, please consider starring the repository!
