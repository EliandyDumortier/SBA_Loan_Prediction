
# SBA Financial Data Modeling and Analysis

## Project Context

The United States Small Business Administration (US SBA) was established in 1953 with the goal of helping small businesses secure credit. Small businesses are a major source of job creation in the United States, so promoting their growth has significant social benefits. Over the years, many successful startups—such as FedEx and Apple—have received SBA-guaranteed loans. However, not all businesses succeed, and some default on their loans.

Our project addresses a critical question: **Can we predict whether a business will be able to repay its loan?**  
This is a binary classification problem (the loan should be granted or not). Importantly, we must be cautious to avoid data leakage—only information available at the time of prediction may be used.

## Project Structure

The project is divided into two main parts:
1. **Data Cleaning, EDA, and Modeling (Machine Learning Focus):**  
   - **Data Cleaning & Preprocessing:**  
     We begin by cleaning the raw data and performing exploratory data analysis (EDA) to understand its characteristics. This involves univariate and bivariate analyses, statistical tests, and more.
   - **Feature Engineering & Selection:**  
     After cleaning, we prepare the data for modeling by creating new features and selecting the most relevant ones.
   - **Modeling:**  
     We applied several machine learning models (excluding Deep Learning) while ensuring no data leakage occurs. In this project, we specifically implemented:
     - **Logistic Regression**
     - **Boosting Models:** (using CatBoost, XGBoost, and LightGBM)
     
2. **Model Interpretation:**  
   - **Feature Importance:**  
     We examine which features contribute most to the predictions.
   - **SHAP Values (bonus):**  
     SHAP values provide an in-depth explanation of each feature's impact on individual predictions.

## Encoding Strategies

Our modeling notebooks use two different encoding strategies for handling categorical variables:
- **Target Encoding:**  
  Converts categorical variables into numerical values based on the target distribution. This method is particularly useful for high-cardinality variables.
- **One-Hot Encoding:**  
  Converts categorical variables into a set of binary (dummy) variables. This approach is simpler but can lead to high dimensionality when many unique categories are present.

> **Note:**  
> For the boosting models (*RandomForest,GradientBoosting,XGBoost*), we used Target Encoding in one notebook and One-Hot Encoding in another.

## Results and Evaluation

We evaluated the models using various metrics such as ROC AUC, F1 Macro, Accuracy, Recall, and Precision. In our comparison notebook, we also provide:
- A **combined ROC curve** to visually compare the models.
- Detailed **confusion matrices** and **classification reports**.
- A summary table that includes automated interpretations of Recall and Precision.

For example, our best XGBoost model (using One-Hot Encoding) and our best LightGBM model (using Target Encoding) were further analyzed using feature importance and SHAP values.

## How to Use This Repository

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/BRIEF_LOAN_PROJECT.git
   cd BRIEF_LOAN_PROJECT

2. **Set Up the Virtual Environment:**

    Activate the virtual environment located in .venv/.
    Install dependencies:

        pip install -r requirements.txt

3. **Explore the Notebooks:**

    - Data Cleaning & EDA:

    Start with notebooks/01_Data_Cleaning.ipynb and notebooks/02_Data_Analysis.ipynb.

    - Modeling Notebooks:

        Check out the notebooks for the different encoding strategies:

            One-Hot Encoding: notebooks/One Hot Encoding/03_Model_XB_RF_GB_OneHOTencoding.ipynb

            Target Encoding: (e.g., notebooks/Target Encoding/                                    03_Model_Logistic_Regression.ipynb, etc.)

     - Model Comparison:

        See notebooks/04_Models_Comparison.ipynb for a side-by-side performance evaluation.

4. **PowerBI Dashboard:**

![alt text](<Capture d’écran du 2025-02-14 15-41-28.png>)

    The powerbi/ folder contains the PowerBI dashboard file (SBA_Financial_Dashboard.pbix) 

    Open the .pbix file in PowerBI Desktop to interact with the visualizations.

```

BRIEF_LOAN_PROJECT/
│
├── .venv/                           # Python virtual environment files
│
├── data/                            # Data directory
│   ├── raw/                        # Original data files (e.g., CSV, Excel)
│   └── processed/                  # Cleaned or intermediate data files
│
├── notebooks/                       # Jupyter notebooks
│   ├── One Hot Encoding/            # Notebooks using One-Hot Encoding
│   │   └── 03_Model_XB_RF_GB_OneHOTencoding.ipynb
│   ├── Target Encoding/             # Notebooks using Target Encoding
│   │   ├── 03_Model_CatBoost.ipynb
│   │   ├── 03_Model_Dummy_Classifier.ipynb
│   │   ├── 03_Model_LightGBM.ipynb
│   │   ├── 03_Model_Logistic_Regression.ipynb
│   │   └── 03_Model_XgBoost_Gradient_Boosting_RandomForest.ipynb
│   ├── 01_Data_Cleaning.ipynb       # Data cleaning steps
│   ├── 02_Data_Analysis.ipynb       # Exploratory data analysis
│   └── 04_Models_Comparison.ipynb   # Comparison of model performances
│
├── powerbi/                         # PowerBI files
│   ├── SBA_Financial_Dashboard.pbix
│   └── powerbi_screenshot.png       # Screenshot of the dashboard
│
├── src/                             # Source code and serialized models
│   ├── api/                         # API code (if applicable)
│   ├── best_dummy_model.pkl
│   ├── catboost_best_grid_model.pkl
│   ├── GradientBoosting_best_grid_model.pkl
│   ├── lightgbm_best_grid_model.pkl
│   ├── logistic_regression_best_grid_model.pkl
│   ├── RandomForest_best_grid_model.pkl
│   └── XgBoost_best_grid_model.pkl
│
├── webapp/                          # Front-end code (if applicable)
│
├── LoanProject_Plan.md              # Project plan/outline
├── README.md                        # This file
└── requirements.txt                 # Python dependencies
```
## Contributing

Feel free to fork this repository, improve the code, and submit pull requests. For any issues or suggestions, please open an issue.
License

This project is licensed under the MIT License. See the LICENSE file for details.


---

### Final Notes

- **Project Context:**  
  This project predicts whether small businesses will repay their SBA loans. It focuses on preventing data leakage by using only data available at prediction time.
  
- **Modeling Approach:**  
  We built models using both One-Hot and Target Encoding to manage categorical data, and we compared their performance using various metrics and visualizations.

- **PowerBI Dashboard:**  
  An interactive PowerBI dashboard is also available to provide additional insights.


# Authors
- [Dorothée Cathry](https://github.com/DorotheeCatry)

- [Eliandy Dumortier](https://github.com/EliandyDumortier)

