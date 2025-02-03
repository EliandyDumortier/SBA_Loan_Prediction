SBA Loan Default Prediction 🚀

Project Overview 📌

This project aims to develop a predictive classification model to determine whether a business will be able to repay a loan guaranteed by the U.S. Small Business Administration (SBA). The goal is to minimize default risks while ensuring financial support for small businesses.

Objectives 🎯

Clean and analyze the dataset (Exploratory Data Analysis - EDA).

Select relevant features and perform feature engineering.

Train a classification model to predict loan repayment probability.

Deploy the model as an API using FastAPI.

Develop a web interface with Django to consume the API.

Tech Stack 🛠️

Python 3.x

Data Processing & Visualization: Pandas, NumPy, Matplotlib, Seaborn

Machine Learning: Scikit-learn

API Development: FastAPI

Web Application: Django

Database: SQLite/PostgreSQL

Deployment: Docker

Project Structure 📂

SBA_Loan_Prediction/
│── data/                 # Raw & processed datasets
│── notebooks/            # Jupyter Notebooks for analysis & EDA
│── src/                  # Source code
│   ├── models/           # Machine learning scripts
│   ├── api/              # FastAPI implementation
│   ├── webapp/           # Django application
│── requirements.txt      # Dependencies list
│── README.md             # Project documentation
│── Dockerfile            # Docker container setup
│── .gitignore            # Files to ignore in Git

Installation & Usage ⚙️

1️⃣ Install Dependencies

pip install -r requirements.txt

2️⃣ Train the Model

python src/models/train_model.py

3️⃣ Run the FastAPI Server 🚀

uvicorn src.api.main:app --reload

Access the interactive API docs at: http://127.0.0.1:8000/docs

4️⃣ Run the Django Web Application 🌐

python src/webapp/manage.py runserver

The app will be available at: http://127.0.0.1:8000/

Model Evaluation 📊

Confusion Matrix: To visualize false positives/negatives.

F1-Score: To assess the balance between precision and recall.

ROC-AUC: To measure the model's discrimination ability.

Author ✍️
Eliandy Dumortier & Dorothée Catry

requirements.txt 📜
(à compléter)

Contributions 🤝

Contributions are welcome! Please follow coding standards and submit well-documented pull requests. 🚀