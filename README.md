# Bloom's Taxonomy Question Difficulty Classifier using BERT

Automated NLP system that classifies university exam questions into Bloom's Taxonomy cognitive levels and predicts overall question paper difficulty (Easy / Medium / High).

Published across **2 Springer conference proceedings** — ICT4SD 2024 and AITA 2024.

---

## Results

| Model | Validation Accuracy |
|-------|-------------------|
| LSTM | 48.76% |
| Bi-LSTM | 67.32% |
| **BERT (ours)** | **98.52%** |

BERT significantly outperforms traditional deep learning approaches by capturing long-range semantic dependencies in question text.

---

## What It Does

1. Takes a university exam question as input
2. Classifies it into one of 6 Bloom's Taxonomy levels:
   - `0` Remember → `1` Understand → `2` Apply → `3` Analyze → `4` Evaluate → `5` Create
3. Aggregates question-level scores using a weighted formula to predict overall paper difficulty

---

## Dataset

- **3,510 questions** collected from university exam papers across multiple subjects
- Two columns: `Questions` and `Bloom's Taxonomy` label
- Labels encoded as: Remember=0, Understand=1, Apply=2, Analyze=3, Evaluate=4, Create=5

Sample:

| Question | Bloom's Level |
|----------|--------------|
| How many steps are required to solve Tower of Hanoi? | Remember |
| Design an algorithm to detect cycles in a graph. | Analyze |
| What is Cyclomatic complexity? | Understand |

---

## Tech Stack

- **Model:** BERT (`bert-base-cased`) via HuggingFace Transformers
- **Framework:** TensorFlow / Keras
- **Tokenization:** BertTokenizer, max length 256
- **Training:** Adam optimizer, ReLU activation, 30 epochs, batch size 16
- **Evaluation:** Accuracy, Precision, Recall, Confusion Matrix

---

## Project Structure

```
question-paper-difficulty-analyzer/
├── blooms_level_final_with_matrices_inc_data.ipynb  # Full training pipeline
├── questions.csv                                    # Dataset of 3,510 labelled questions
├── requirements.txt
└── README.md
```

---

## How to Run

```bash
git clone https://github.com/krish902/question-paper-difficulty-analyzer
cd question-paper-difficulty-analyzer
pip install -r requirements.txt
jupyter notebook blooms_level_final_with_matrices_inc_data.ipynb
```

---

## Publications

This work is published in two peer-reviewed Springer conference proceedings:

1. **Impact of BERT on Evaluating the Quality of Question Papers using Bloom's Taxonomy**
   ICT4SD 2024 — 9th International Conference on ICT for Sustainable Development, Goa, India

2. **Difficulty Level Prediction on Evaluating the Quality of Question Papers using Bloom's Taxonomy**
   AITA 2024 — 2nd International Conference on Artificial Intelligence: Theory and Applications, Bangalore, India

---

## Authors

Krish Bhikadiya, Dhaval Patel, Hemit Rana, Nikita Bhatt
Chandubhai S. Patel Institute of Technology, CHARUSAT, India
