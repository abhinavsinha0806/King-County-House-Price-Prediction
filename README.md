# House Price Prediction for King County, USA

This repository contains a data analysis and machine learning project focused on predicting house sale prices in King County, Washington, which includes the city of Seattle. The analysis uses various regression techniques to model prices based on a set of features describing each property.

---

### **📖 Dataset**

The dataset contains house sale prices for homes sold between May 2014 and May 2015. It includes 21 variables, such as the number of bedrooms, bathrooms, square footage, and location data.

-   **Source**: The original dataset can be found on [Kaggle](https://www.kaggle.com/harlfoxem/housesalesprediction).
-   **Data Used**: A slightly modified version of the dataset provided for a course, which includes some missing values for practice.

---

### **⚙️ Project Workflow**

The project follows a structured data science workflow, documented in the `house_price_analysis.ipynb` notebook:

1.  **Data Loading and Cleaning**:
    - The dataset is downloaded from a cloud source and loaded into a pandas DataFrame.
    - Unnecessary columns like `id` and `Unnamed: 0` are dropped.
    - Missing values in the `bedrooms` and `bathrooms` columns are handled by imputing the mean.

2.  **Exploratory Data Analysis (EDA)**:
    - The distribution of houses by the number of floors is analyzed.
    - Boxplots are used to investigate price outliers for homes with and without a waterfront view.
    - Regression plots and a correlation matrix are used to identify features that are strongly correlated with `price`, such as `sqft_living` and `grade`.

3.  **Model Development**:
    - **Simple Linear Regression**: A baseline model is built using only the `sqft_living` feature.
    - **Multiple Linear Regression**: The model is improved by including a list of the most correlated features.
    - **Pipeline with Polynomial Features**: A Scikit-learn pipeline is constructed to scale the data, create second-degree polynomial features, and fit a linear model to capture non-linear relationships.

4.  **Model Evaluation and Refinement**:
    - The data is split into training (85%) and testing (15%) sets for robust model evaluation.
    - **Ridge Regression** is implemented to prevent overfitting.
    - **Polynomial Ridge Regression** is used as the final model, combining polynomial features with Ridge regularization for the best performance on unseen data.

---

### **📊 Model Performance Summary**

The performance of each model was evaluated using the **R-squared ($R^2$) score**. The results show a clear improvement as model complexity increased:

| Model Type | Features Used | R² Score (on Training Data) |
| :--- | :--- | :--- |
| Simple Linear Regression | `sqft_living` | ~0.49 |
| Multiple Linear Regression | Multiple Features | ~0.66 |
| Pipeline (Poly Features) | Multiple Features (Transformed) | ~0.75 |

**Final Model Evaluation (on Test Data):**

| Model Type | Features Used | R² Score (on Test Data) |
| :--- | :--- | :--- |
| Ridge Regression | Multiple Features | ~0.65 |
| **Polynomial Ridge Regression** | **Multiple Features (Transformed)** | **~0.70** |

The final Polynomial Ridge Regression model was able to explain approximately **70%** of the variance in house prices on unseen test data.

---

### **🚀 How to Run**

1.  Clone this repository:
    ```bash
    git clone [https://github.com/YourUsername/King-County-House-Price-Prediction.git](https://github.com/YourUsername/King-County-House-Price-Prediction.git)
    ```
2.  Install the required libraries:
    ```bash
    pip install -r requirements.txt
    ```
3.  Open and run the `house_price_analysis.ipynb` notebook in a Jupyter environment.

---

### **🛠️ Libraries & Technologies Used**

-   pandas
-   numpy
-   scikit-learn
-   seaborn
-   matplotlib
-   requests
