# AI Generated vs Human Written Text Detection

### Benchmarking Transformer Models for Text Classification

---

## Overview

This project focuses on detecting whether a given text is **AI-generated** or **human-written** using transformer-based models.

With the rapid advancement of large language models, distinguishing between AI-generated and human-written text has become important for maintaining **academic integrity, authenticity, and reliability of content**.

This project benchmarks multiple transformer models on two different datasets to evaluate their performance and generalization ability.

---

## Objectives

* Classify text as AI-generated or human-written
* Compare performance of multiple transformer models
* Evaluate model behavior on different datasets
* Analyze errors and limitations in detection

---

## Datasets

### 1. AIGTxt Dataset

* Total samples: 7,214
* Balanced dataset (AI vs Human)
* Columns: `text`, `labels`
* Labels:

  * 0 → AI-generated
  * 1 → Human-written

---

### 2. Dataset.xlsx

* Total samples: 11,549
* More complex and diverse dataset
* Columns: `text`, `source`, `label name`, `labels`
* Near-balanced distribution

---

### Data Split

* 80% Training
* 20% Testing

---

## Models Used

The following transformer models were fine-tuned:

* BERT
* RoBERTa
* DeBERTa
* DistilBERT
* ELECTRA

All models were trained using the same setup for fair comparison.

---

## Methodology

1. **Data Preprocessing**

   * Lowercasing
   * Removing special characters and URLs
   * Tokenization
   * Padding and truncation

2. **Model Training**

   * Fine-tuning pretrained transformer models
   * Using Hugging Face Trainer API

3. **Evaluation Metrics**

   * Accuracy
   * Precision
   * Recall
   * F1 Score
   * Confusion Matrix
   * ROC-AUC

---

## Project Structure

```id="u1m9yo"
AI GENERATED VS HUMAN WRITTEN/
│
├── aigtxt/
│   ├── AIGTxt dataset file
│   ├── overall_Dataset_B.ipynb
│   ├── all_predictions.csv
│   ├── error_cases_only.csv
│   ├── model_error_summary.csv
│
├── Dataset/
│   ├── Dataset.xlsx related files
│   ├── comparisonModel.ipynb
│   ├── all_predictions.csv
│   ├── error_cases_only.csv
│   ├── model_error_summary.csv
```

---

## Results

### AIGTxt Dataset

* All models achieved **accuracy above 93%**
* Strong performance across all models
* ModernBERT achieved highest F1-score (~94.85%)
* ELECTRA showed high precision
* DeBERTa and DistilBERT showed high recall

---

### Dataset.xlsx

* Performance dropped across all models
* BERT achieved best accuracy (~81.08%)
* BERT showed more balanced performance
* Other models had high precision but low recall

---

## Key Observations

* Models perform well on controlled datasets
* Performance decreases on more complex datasets
* Generalization across datasets is challenging
* No single model performs best in all metrics

---

## Error Analysis

* Models sometimes classify human text as AI-generated
* Struggles with:

  * paraphrased text
  * formal writing
  * domain-specific content
* Performance varies significantly across datasets

---

## Limitations

* Limited dataset size
* Training for only a few epochs
* Lack of multilingual evaluation
* Reduced generalization on complex datasets

---

## Future Work

* Use larger and more diverse datasets
* Improve generalization across domains
* Try advanced transformer architectures
* Extend to multilingual detection
* Deploy as a real-world application

---

## How to Run

1. Clone the repository:

```
git clone https://github.com/your-username/ai-text-detection-transformers.git
```

2. Open notebooks in:

* Google Colab
* Jupyter Notebook

3. Install required libraries:

```
pip install transformers pandas numpy scikit-learn
```

4. Run notebooks step by step

---

## Contributors

* Amita Mondal
* Anuska Sarkar
* Sania Parveen
* Arnab Maji
* Diparna Das

---

## Conclusion

This project demonstrates that transformer-based models are effective for detecting AI-generated text. However, their performance depends heavily on dataset complexity and their ability to generalize across different types of text.
