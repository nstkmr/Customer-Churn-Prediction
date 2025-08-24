# Telco Customer Churn Analysis

This project performs an in-depth exploratory data analysis (EDA) on the Telco Customer Churn dataset. The goal is to understand the key drivers of customer churn and visualize the relationships between various customer attributes and their likelihood to churn. This analysis serves as a foundational step for building a future predictive model.

## Project Overview

Customer churn is a critical metric for subscription-based businesses. This project dives into a popular Telco dataset to uncover patterns and insights related to why customers choose to leave. The notebook covers the entire data analysis pipeline from data cleaning and preprocessing to visualization and insight generation.

## Dataset

The project uses the **Telco Customer Churn** dataset, which contains information about customers of a fictional telecommunications company. The data includes:
- **Customer Demographics:** Gender, senior citizen status, partner, and dependent information.
- **Account Information:** Tenure, contract type, payment method, paperless billing, monthly charges, and total charges.
- **Services Subscribed:** Phone service, multiple lines, internet service, online security, online backup, device protection, tech support, and streaming services.
- **Target Variable:** Churn status (Yes/No).

## Methodology

The analysis in the Jupyter Notebook (`Customer Churn Prediction.ipynb`) follows these key steps:

1.  **Data Loading and Inspection:**
    - The dataset is loaded using Pandas.
    - Initial exploration is done using `.head()`, `.shape`, and `.info()` to understand its structure, size, and data types.

2.  **Data Cleaning and Preprocessing:**
    - The `customerID` column was dropped as it is not a predictive feature.
    - The `TotalCharges` column was converted from an object to a numeric data type. This process identified 11 rows with missing values, which corresponded to customers with a tenure of 0.
    - These 11 rows with null `TotalCharges` were dropped from the dataset.
    - The `SeniorCitizen` column, originally numeric (0/1), was mapped to categorical labels ('No'/'Yes') for better interpretability in visualizations.

3.  **Exploratory Data Analysis (EDA) & Visualization:**
    - A variety of visualizations were created using Matplotlib and Seaborn to explore the relationships between different features and the churn rate.
    - A correlation heatmap was generated to provide a quick overview of the relationships between all variables.

## Key Visualizations & Insights

Several key insights were derived from the visualizations:

* **Contract Type:** Customers with **Month-to-Month** contracts have a significantly higher churn rate compared to those with One-Year or Two-Year contracts. This suggests that long-term contracts are effective in retaining customers.

* **Customer Tenure:** The box plot clearly shows that customers who churn tend to have a much shorter tenure. New customers are more likely to leave than long-standing ones.

* **Internet Service:** Customers with **Fiber optic** internet service exhibit a higher churn rate than those with DSL. While Fiber optic is a premium service, it might be associated with higher costs or other factors causing dissatisfaction.

* **Add-on Services:** Customers **without** services like `OnlineSecurity` and `TechSupport` are more likely to churn. This indicates that these services play a crucial role in customer satisfaction and retention.

* **Payment Method:** The churn rate is highest among customers who use **Electronic check** as their payment method.

* **Monthly & Total Charges:**
    - The KDE plot shows that customers with higher **Monthly Charges** are more prone to churning.
    - Conversely, customers with higher **Total Charges** are less likely to churn, which correlates with longer tenure.

## How to Use

To run this project on your local machine, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/your-repository-name.git](https://github.com/your-username/your-repository-name.git)
    cd your-repository-name
    ```

2.  **Install the dependencies:**
    It is recommended to create a virtual environment first.
    ```bash
    pip install -r requirements.txt
    ```

3.  **Launch Jupyter Notebook:**
    ```bash
    jupyter notebook "Customer Churn Prediction.ipynb"
    ```

## Dependencies

The project was created using Python 3 and the following libraries. You can install them by running `pip install -r requirements.txt`.

```
pandas==<your_pandas_version>
numpy==<your_numpy_version>
matplotlib==<your_matplotlib_version>
seaborn==<your_seaborn_version>
```
*(You can find the versions by running `pip freeze` in your environment and updating the `requirements.txt` file.)*

## Future Work

While this project provides a comprehensive analysis, the next logical step is to build a predictive model. Future work could include:
- **Feature Engineering:** Creating new features from existing ones (e.g., tenure groups).
- **Model Building:** Training several classification models (e.g., Logistic Regression, Random Forest, Gradient Boosting) to predict churn.
- **Model Evaluation:** Comparing model performance using metrics like Accuracy, Precision, Recall, F1-Score, and AUC-ROC.
- **Hyperparameter Tuning:** Optimizing the best-performing model to improve its predictive power.