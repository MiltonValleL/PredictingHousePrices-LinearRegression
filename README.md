# 🏠 Ames Housing Price Prediction: A Robust Linear Regression Approach

<br>

## 👋 Overview
Welcome to my Housing Price Prediction project! This repository contains a comprehensive analysis and modeling workflow designed to predict residential home prices in Ames, Iowa.

The goal of this project was not just to achieve a high accuracy score, but to build a statistically robust and interpretable Linear Regression model. Special emphasis was placed on "Forensic EDA," structural data cleaning, and diagnosing the underlying assumptions of the Ordinary Least Squares (OLS) method.

<br>
<br>

## 🚀 Key Highlights & Methodology
This project moves beyond standard data cleaning by applying domain-specific logic to data engineering:

---
### 1. Forensic Exploratory Data Analysis (EDA)
- **Target Analysis**: Diagnosed the skewness of SalePrice and validated the need for transformation (or the lack thereof based on residual behavior).

- **Bivariate Outlier Detection**: Instead of blindly removing statistical outliers, I implemented a "High Spec vs. Low Price" logic. This preserved valid luxury properties while removing 4 specific anomalies (e.g., >4,000 sq ft homes priced abnormally low) that would have artificially leveraged the regression line.

---

### 2. Strategic Data Preparation
- **Structural Missingness vs. Random Omissions**: Differentiated between missing data that implies "Does Not Exist" (e.g., No Garage, No Pool) versus actual missing information. Implemented specific imputation strategies for each case to maintain structural coherence.

- **Ordinal vs. Nominal Encoding:**

   - **Ordinal Features**: Manually mapped quality ratings (Ex, Gd, TA...) to numerical scales (5, 4, 3...) to preserve hierarchical information.

   - **Nominal Features**: Applied One-Hot Encoding with drop_first=True to mitigate multicollinearity.

---

### 3. Model Training & Evaluation
- **Scaling**: Applied StandardScaler to features to ensure coefficient comparability.

- **Algorithm**: Linear Regression (OLS).

- **Diagnostics**: Validated model assumptions (Linearity, Homoscedasticity, and Normality) using residual plots.

---

<br>
<br>

## 📊 Results & Insights

---
### Model Performance

- **R² Score (Test Set)**: **`0.9119`**

- **MAE (Mean Absolute Error)**: **`$ 16,402.69`**

---

### Key Drivers of Price
Based on the standardized coefficients, the most influential factors in the Ames housing market are:

- **Ground Living Area (Gr Liv Area)**: The strongest positive driver. Size matters most.

- **Overall Quality**: Construction materials and finish are the second most critical factor.

- **The "Bedroom Paradox"**: The model revealed a negative coefficient for Bedroom AbvGr (Bedrooms Above Grade). This suggests that, holding total square footage constant, dividing a house into more (smaller) rooms actually decreases its value compared to having fewer, more spacious rooms.
---

<br>
<br>

## 🛠️ Technologies Used
- **Language**: Python

- **Libraries**: Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn

- **Environment**: Jupyter Notebook / Google Colab

---

<br>
<br>

## 📂 Repository Structure

---

├── datasets/

   │   └── AmesHousing.csv      `(Original Dataset)`

├── Notebooks/

│   └── Predicting House Prices - Linear Regression.ipynb      `(Main analysis and Modeling)`

├── README.md      `(Project documentation)`

└── requirements.txt      `(Dependencies)`

---

<br>
<br>

## 🔮 Future Improvements
To further refine the model and address the specific limitation of multicollinearity detected in the "Garage" features (where absence of features showed artificial positive weights), the next steps would include:

- **Implementing Lasso Regression** (L1 Regularization) to perform automatic feature selection.

- **Exploring Tree-based models** (Random Forest or XGBoost) to capture non-linear relationships.

<br>
<br>

## 🤝 Contact
I am a Data Science enthusiast passionate about Machine Learning and statistical modeling. 

If you have any questions about this project or would like to connect, feel free to reach out!

<br>

---
**Author:** Milton Rodolfo Valle Lora

**LinkedIn:** [Please click here](https://www.linkedin.com/in/miltonvallelora/)

---

