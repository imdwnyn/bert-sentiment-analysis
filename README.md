# 🎭 BERT Sentiment Analysis

Fine-tuning a pre-trained BERT model to classify IMDb movie reviews as **Positive** or **Negative** using Hugging Face Transformers and PyTorch.

---

## 📌 Project Overview

This project demonstrates **transfer learning** for NLP — instead of training a model from scratch, we fine-tune **BERT** (`bert-base-uncased`, 110M parameters) on the IMDb dataset. BERT's bidirectional attention mechanism makes it significantly better at understanding context, negation, and nuance compared to traditional sentiment models.

---

## 🗂️ Dataset

**IMDb Movie Reviews** (via Hugging Face `datasets`)
- 25,000 training reviews
- 25,000 test reviews  
- Binary labels: `1` = Positive, `0` = Negative
- Perfectly balanced classes

---

## 🔧 Tech Stack

| Library | Purpose |
|---|---|
| `transformers` | BERT model, tokenizer, Trainer API |
| `datasets` | IMDb dataset loading & processing |
| `torch` | PyTorch deep learning backend |
| `scikit-learn` | Evaluation metrics (accuracy, F1) |

---

## 📁 Project Structure
```
bert-sentiment-analysis/
│
├── movie_review_sentiment_analysis.ipynb   # Main notebook
└── README.md
```

---

## 🚀 How to Run

1. Open the notebook in **Google Colab**
2. Go to `Runtime → Change runtime type → T4 GPU`
3. Run all cells top to bottom

Or clone and run locally:
```bash
git clone https://github.com/yourusername/bert-sentiment-analysis
cd bert-sentiment-analysis
pip install transformers datasets torch scikit-learn
jupyter notebook
```

---

## 📊 Results

| Metric | Score |
|---|---|
| Accuracy | ~93% |
| F1 Score | ~93% |

---

## 🧪 Edge Case Analysis

One of the highlights of this project is testing the model on tricky, real-world inputs beyond standard positive/negative reviews:

| Text | Predicted | Confidence | Correct? |
|---|---|---|---|
| "It wasn't the worst movie I've seen" | Negative 😠 | 99.7% | ❌ Should be weakly positive |
| "The movie was long" | Positive 😊 | 73.3% | ❓ Truly ambiguous |
| "I can't believe how good this was!" | Positive 😊 | 99.5% | ✅ |
| "So bad it's actually good" | Positive 😊 | 93.4% | ✅ Handled irony well! |

**Key findings:**
- BERT handles emphatic language and sarcasm well
- Struggles with double negatives and ambiguous sentences
- Overconfident on edge cases — a known BERT limitation

---

## 🛠️ Potential Improvements

- Add a **Neutral class** for ambiguous sentences
- Fine-tune on more diverse datasets (SST-2, Yelp, Twitter)
- Try stronger models like `roberta-base` or `distilbert`
- Apply **temperature scaling** to fix overconfidence

---

## 👤 Author

**Your Name**  
B.Tech [Your Branch] | [Your College]  
[LinkedIn](https://linkedin.com/in/yourprofile) • [GitHub](https://github.com/yourusername)
