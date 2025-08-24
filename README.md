# AI-Powered Customer Complaint Classification
---

## 🚀 Executive Summary

This project demonstrates a complete, end-to-end machine learning workflow to solve a common business problem: the manual sorting and routing of customer support tickets. I developed a system that uses **Natural Language Processing (NLP)** to automatically classify consumer mortgage complaints into 22 distinct categories.

The final model, a fine-tuned **Logistic Regression classifier**, achieved **52% accuracy**—over **11 times better than random chance**. This project showcases the ability to handle unstructured text data, build and evaluate multiple machine learning models, and derive actionable business insights through a data-driven, iterative process.

---

## 🛠️ Key Skills Showcased

* **Data Cleaning:** Handling missing values and preprocessing messy, real-world text data.
* **Exploratory Data Analysis (EDA):** Using libraries like Matplotlib and Seaborn to visualize data distributions and generate initial insights.
* **Natural Language Processing (NLP):** Text tokenization, stop word removal, lemmatization, and feature engineering with TF-IDF.
* **Machine Learning:** Building, training, and evaluating multiple classification models (Logistic Regression, Random Forest).
* **Analytical Thinking:** Conducting methodical experiments, comparing model performance, and making an evidence-based decision on the best solution.
* **Business Acumen:** Translating a technical result into a clear business value proposition focused on operational efficiency and cost savings.

---

## 📊 The Dataset

The data for this project is from the public **Consumer Financial Protection Bureau (CFPB) Consumer Complaint Database**. The key columns used were:

* `consumer complaint narrative`: The raw text of the customer's complaint (our input feature).
* `consumer complaint code`: The specific category of the mortgage issue (our target variable).

---

## ⚙️ Project Workflow

### 1. Data Cleaning & Preprocessing
The initial dataset was loaded and filtered to focus on the core task. I performed several key cleaning steps:
* Selected the relevant columns and renamed them for clarity.
* Removed rows with missing complaint text or issue labels.
* Identified and removed issue categories with only one complaint to ensure the model could be properly trained and evaluated.

### 2. Exploratory Data Analysis (EDA)
I started by visualizing the distribution of complaint types. This revealed the most common issues customers face and highlighted the class imbalance in the dataset, a key consideration for the modeling phase.

<br>

### 3. NLP & Feature Engineering
To prepare the text for the model, I built a standard NLP pipeline:
1.  Converted all text to lowercase.
2.  Removed all punctuation.
3.  Tokenized the text (split it into individual words).
4.  Removed common English "stop words."
5.  Lemmatized words to their root form (e.g., "payments" became "pay").
6.  Converted the cleaned text into a numerical format using **TF-IDF vectorization**.

### 4. Modeling & Iteration
The core of the project was an iterative modeling process to find the best solution.

* **Baseline Model:** I established a strong baseline with a **Logistic Regression** model, which achieved **52% accuracy**.

* **Experiment 1 (N-grams):** I hypothesized that adding two-word phrases (n-grams) would improve performance. However, this **decreased accuracy to 48%**, indicating it introduced more noise than signal for this dataset.

* **Experiment 2 (Random Forest):** I tested a more complex model, a **Random Forest Classifier**, to see if it could capture more intricate patterns. This resulted in a **51% accuracy**.

---

## 🎯 Results & Conclusion

The experiments demonstrated that the simplest model was the most effective. The final, recommended model is the **Logistic Regression classifier with single-word TF-IDF features**, which achieved a **52% accuracy**.

<br>

This result, while not perfect, is **over 11 times more effective than random guessing** and provides a powerful tool for initial complaint triage. The analysis proves that a simple, interpretable model is often the most robust solution, avoiding the overfitting that more complex models can be prone to on smaller datasets.

---

## 🏢 Business Value & Productionization

**How would a business use this?**

This model could be deployed as an API to create a fully automated system for a mortgage company:

1.  A new complaint is submitted through a web form or email.
2.  The text is sent to the model's API.
3.  The model instantly predicts the category (e.g., "Escrow Issue").
4.  The customer support ticket is automatically tagged and routed to the specialized escrow team **without any human intervention**.

This process would significantly reduce manual labor, decrease response times, and improve the overall customer experience.

<br>

---

## 🚀 How to Run This Project

To replicate this analysis, clone the repository and run the Jupyter Notebook:

```bash
# Clone the repository
git clone [(https://github.com/danabr21285/Customercomplaint.git)]

# Navigate to the project directory
cd [Customercomplaint]

# It is recommended to use a virtual environment
python -m venv venv
source venv/bin/activate

# Install the required libraries
pip install -r requirements.txt

# Open the Jupyter Notebook
jupyter notebook
