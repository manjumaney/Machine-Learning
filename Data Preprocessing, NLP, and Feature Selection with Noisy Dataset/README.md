# README — Assignment: Data Preprocessing, NLP, and Feature Selection

## Overview

This assignment is split into three parts.

1. Clean a noisy CSV dataset using standard preprocessing steps.
2. Process text from `wiki.txt` using tokenization and regular expressions.
3. Perform feature selection on the Melbourne housing dataset from Kaggle and compare methods.

---

## Part A — `noisy_data.csv` Preprocessing (30 points)

### Goal

Prepare a **clean dataset** from `noisy_data.csv` by applying:

1. **Missing value imputation** 
2. **Normality testing** on numerical columns
3. **Categorical encoding + feature scaling** 

### Work Done

* **Missing Values (Imputation)**

  * Numerical columns: imputed using **mean** (or median if needed)
  * Categorical columns: imputed using **mode** (most frequent value)

* **Normality Tests (Numerical Columns)**

  * A normality test (e.g., Shapiro-Wilk) is applied to each numerical column.
  * **Hypotheses**

    * **H₀ (Null):** The data follows a normal distribution.
    * **H₁ (Alternative):** The data does not follow a normal distribution.
  * **Decision Rule (α = 0.05)**

    * p-value > 0.05 → Fail to reject H₀ (approximately normal)
    * p-value ≤ 0.05 → Reject H₀ (not normal)
  * A short comment is provided for each column based on the p-value.

* **Encoding + Scaling**

  * Categorical variables are encoded (One-Hot / Label depending on column type)
  * Numerical features are scaled (StandardScaler / MinMaxScaler)
  * Final output is a cleaned dataset ready for ML.

### Output

* Clean dataset exported (example): `clean_noisy_data.csv`

---

## Part B — `wiki.txt` Text Processing

### Goal

Use the text in `wiki.txt` to:

1. Tokenize text using **RegexpTokenizer()** and **word_tokenize()** while removing **stopwords and punctuation** 
2. Write a **regular expression** to extract all **year mentions** 
3. Explain the **differences** in outputs between the two tokenizers 

### Work Done

* **Tokenization**

  * Both tokenizers are applied separately.
  * Tokens are cleaned by removing:

    * punctuation symbols
    * stopwords (customizable list; negative words like *“don’t”* can be retained if needed)

* **Regex for Years**

  * A regular expression is used to extract year-like patterns.

* **Differences Observed**

  * The outputs are compared and differences are summarized.

### Output

* Token lists for both methods
* Extracted year list
* Comparison notes

---

## Part C — Feature Selection on Melbourne Housing Dataset

### Dataset

Kaggle: **Melbourne Housing Snapshot**
Source: `https://www.kaggle.com/dansbecker/melbourne-housing-snapshot/home`

### Goal

Apply feature selection techniques (20 points):

* Correlation
* Chi-Square
* Mutual Information
* Random Forest feature importance

Then:

* Compare feature importance using a **bar chart** 
* Comment on results and identify the **best and worst** method for this dataset

### Work Done

* Dataset is downloaded and loaded into the notebook.
* Feature selection is applied using four methods:

  * **Correlation:** identifies linear relationships with the target
  * **Chi-Square:** evaluates dependence between categorical features and target
  * **Mutual Information:** captures non-linear dependency
  * **Random Forest Importance:** uses model-based importance scores
* Selected feature rankings are visualized using **bar charts**.
* A written comparison explains differences, overlaps, and method performance.

### Output

* Feature ranking tables per method
* Bar chart comparison
* Short analysis: best vs worst method based on consistency and relevance

---

## Files Required

* `noisy_data.csv`
* `wiki.txt`
* Melbourne dataset file(s) downloaded from Kaggle (e.g., `melb_data.csv`)

---

## Tools & Libraries Used

* Python
* Pandas, NumPy
* SciPy (normality tests)
* scikit-learn (encoding, scaling, feature selection, Random Forest)
* NLTK (tokenization, stopwords)
* Matplotlib (bar charts)

---

## How to Run

1. Place `noisy_data.csv` and the Kaggle dataset file in the same folder as the notebook.
2. Open the notebook and run cells in order (top to bottom).
3. Generated outputs (clean dataset, tables, charts) will be saved or displayed in the notebook.

---

## Conclusion
This assignment shows the whole process from raw data cleaning to text data processing and feature selection. The data preprocessing steps enhance the quality of the data, while the NLP section shows the practical application of data cleaning and extraction, and the feature selection comparison shows the different ways feature selection can be used based on model behavior.
