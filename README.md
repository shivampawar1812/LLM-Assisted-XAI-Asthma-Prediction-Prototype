# LLM-Assisted Explainable Asthma Prediction Framework Prototype

An exploratory Explainable AI (XAI) framework for asthma prediction that combines Machine Learning, SHAP explainability, and Large Language Models (LLMs) to generate human-readable interpretations of model predictions.

This repository represents an early-stage prototype exploring how explainability techniques and LLMs can improve the interpretability of healthcare-oriented machine learning workflows.

---

# Overview

Machine learning models can achieve strong predictive performance in healthcare tasks, but their predictions are often difficult to interpret for non-technical users.

This project explores a multi-stage explainability pipeline that:

* Predicts asthma-related outcomes using a Support Vector Machine (SVM)
* Identifies influential features using SHAP (SHapley Additive Explanations)
* Converts technical feature attributions into structured natural language explanations using an LLM
* Evaluates explanation quality using fidelity and entropy-based metrics

The primary goal of this work is to investigate methods for improving interpretability and transparency in AI-assisted healthcare prediction systems.

---

# System Pipeline

```text
Data Processing
      ↓
Feature Engineering
      ↓
SVM Prediction Model
      ↓
SHAP Feature Attribution
      ↓
LLM-Based Explanation Generation
      ↓
Explainability Evaluation
```

---

# Dataset

### Dataset Used

Asthma Health Dataset

### Source

Kaggle

### Dataset Characteristics

* Total Records: 10,000
* Total Features: 14

### Example Features

* Age
* Gender
* BMI
* Smoking History
* Family History
* Air Pollution Level
* Physical Activity
* Comorbidities
* ER Visits
* Peak Expiratory Flow

### Target Variable

| Value | Meaning   |
| ----- | --------- |
| 0     | No Asthma |
| 1     | Asthma    |

---

# Machine Learning Model

## Model Used

Support Vector Machine (SVM)

## Configuration

```python
SVC(
    kernel='rbf',
    C=10,
    probability=True
)
```

## Model Performance

| Metric   | Score  |
| -------- | ------ |
| Accuracy | 98.29% |

> Note: The dataset used in this prototype is synthetic/simulated in nature. Therefore, the reported performance should not be interpreted as clinically representative.

---

# Explainability Methods

## SHAP-Based Feature Attribution

SHAP (SHapley Additive Explanations) is used to identify which features contribute most strongly to individual predictions.

### Benefits

* Local explanation for individual predictions
* Quantitative feature attribution
* Improved model interpretability
* Visualization of feature influence

---

# LLM-Assisted Explanation Generation

Technical SHAP outputs can be difficult for non-technical users to interpret directly.

To improve readability, SHAP feature contributions are transformed into structured natural language explanations using a Large Language Model.

## LLM Used

* Mistral Large

## Example Explanation Style

```text
Illustrative Interpretation of Model Prediction

The prediction was primarily influenced by:

• Smoking history
• Physical activity level
• Presence of allergies
• Family history of asthma
• Air pollution exposure

The generated explanation summarizes how these
features contributed to the prediction in simplified
natural language.
```

> The generated explanation is intended for interpretability research purposes only and should not be considered medical advice or diagnosis.

---

# Prompt Design Strategy

The prompting framework follows a structured reasoning approach designed to:

* Identify influential SHAP features
* Explain feature influence in simple language
* Summarize overall prediction reasoning
* Maintain non-diagnostic wording

## Safety Constraints

* No medical diagnosis generation
* No treatment recommendations
* Avoidance of authoritative clinical language
* Simplified explanation style for readability

---

# Explainability Evaluation

To evaluate explanation quality and consistency, two evaluation metrics were explored.

## Fidelity

Measures alignment between SHAP-important features and features referenced in generated explanations.

| Metric   | Score |
| -------- | ----- |
| Fidelity | 0.667 |

Interpretation:
A majority of influential SHAP features were reflected in generated explanations.

---

## Entropy

Measures variation and consistency across repeated explanation generations.

| Metric  | Score |
| ------- | ----- |
| Entropy | 0.25  |

Interpretation:
Lower entropy indicates relatively stable explanation generation across repeated runs.

---

# Repository Structure

```text
Explainable-Asthma-Prediction/
│
├── Asthma_Model_notebook.ipynb
└── README.md
```

---

# Technologies Used

* Python
* Scikit-learn
* SHAP
* Pandas
* NumPy
* Mistral Large
* Jupyter Notebook

---

# Installation

Clone the repository:

```bash
git clone https://github.com/shivampawar1812/Explainable-Asthma-Prediction.git
```

Move into the project directory:

```bash
cd Explainable-Asthma-Prediction
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

# Future Improvements

* Migration to real-world healthcare datasets (e.g., NHANES)
* Comparison across multiple LLMs
* Integration of additional explainability techniques
* Improved explainability evaluation metrics
* Clinical expert validation
* Modular research pipeline implementation

---

# Limitations

* Dataset used is synthetic/simulated and may not reflect real-world clinical distributions
* No clinical validation has been performed
* LLM-generated explanations may vary depending on prompt structure
* SHAP explanations may not fully capture all model behaviors
* The framework is intended for research exploration only

---

# Disclaimer

This repository is an educational and research-oriented prototype.

The generated explanations are produced using machine learning and large language models and should not be interpreted as medical advice, diagnosis, or treatment recommendations.

Clinical decisions should always be made by qualified healthcare professionals.

---

# Author

**Shivam Pawar**
B.Tech Artificial Intelligence & Machine Learning
Manipal University Jaipur
