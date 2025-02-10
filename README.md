# DIIG Data Challenge '24
This project was submitted as part of the application process for the Duke Impact Investing Group (DIIG).  The goal was to perform a demographic and attrition analysis on a provided dataset to identify key factors contributing to employee turnover at IBM.

## Features
* **Demographic Clustering:**  The project performs K-Means clustering on employee demographic data to segment employees into distinct groups.
* **Attrition Analysis:**  Attrition rates are calculated and visualized for each cluster, revealing which segments experience higher turnover.
* **Attrition Factor Analysis:** Statistical tests (t-tests) identify significant factors influencing attrition within each cluster.
* **Role Analysis:**  Analyzes the distribution of job roles across clusters and determines statistically significant relationships between roles and clusters using a chi-square test and Cramér's V.
* **Correlation Analysis:** Pearson correlation coefficients are calculated to measure the strength and direction of relationships between specific features (e.g., overtime, job satisfaction) and attrition within individual clusters.
* **Data Visualization:**  Utilizes `matplotlib` and `seaborn` to generate insightful visualizations of the analysis results, including scatter plots, bar charts, and heatmaps.

## Technologies Used
* **Python:** The primary programming language for data analysis and visualization.
* **Pandas:**  Used for data manipulation and analysis.
* **Scikit-learn:**  Provides machine learning algorithms (KMeans clustering, StandardScaler, PCA) and preprocessing tools.
* **Seaborn:**  Used for creating statistically informative and visually appealing visualizations.
* **Matplotlib:**  A fundamental plotting library in Python.
* **Jupyter Notebook:**  Interactive computing environment for running and documenting the analysis.
* **Scipy:** Provides statistical functions like t-tests and chi-square tests.
* **Numpy:** Used for numerical operations and array manipulation.

## Statistical Analysis
The analysis employs the following statistical methods:

* **K-Means Clustering:** To segment employees into distinct groups based on demographic features.
* **Label Encoding:** To convert categorical features into numerical representations suitable for clustering and statistical analysis.
* **Standard Scaling:** To standardize the numerical features before applying clustering, ensuring that features with larger scales don't disproportionately influence the clustering results.
* **Principal Component Analysis (PCA):**  To reduce the dimensionality of the data for visualization purposes, allowing for a 2D representation of the clusters.
* **T-tests:** To assess the statistical significance of differences in the means of non-demographic features between employees who left and those who stayed within each cluster.
* **Chi-Square Test of Independence:** To determine if there is a statistically significant association between job roles and clusters.
* **Cramér's V:** To measure the strength of the association between job roles and clusters, providing a standardized measure of effect size for the chi-square test.
* **Pearson Correlation:** To quantify the linear relationship between specific features and attrition within each cluster.

## Dataset Description
Dataset Description

This project utilizes the IBM HR Analytics Employee Attrition dataset.  The dataset contains 24 variables describing employee characteristics and their attrition status.  A crucial aspect of this analysis is the use of unsupervised learning (K-Means clustering) to segment employees based on demographic factors, enabling a more nuanced understanding of attrition patterns within distinct employee groups.

The dataset includes both categorical and numerical variables.  Below is a description of each variable:

| Variable Name             | Description                                                                     | Data Type | Example(s)                      |
|--------------------------|---------------------------------------------------------------------------------|------------|----------------------------------|
| **Age**                   | Age of the employee                                                             | Numerical  | 41, 49, 37, ...                  |
| **Attrition**             | Whether the employee left the company ("Yes" or "No")                         | Categorical | Yes, No                          |
| **BusinessTravel**        | Frequency of business travel (Non-Travel, Travel_Frequently, Travel_Rarely)      | Categorical | Travel_Rarely, Travel_Frequently |
| **DailyRate**             | Daily rate of the employee                                                     | Numerical  | 1102, 279, 1373, ...              |
| **Department**            | Department the employee belongs to (Sales, Research & Development, Human Resources) | Categorical | Sales, Research & Development    |
| **DistanceFromHome**      | Distance from home to work (in miles)                                          | Numerical  | 1, 8, 2, ...                     |
| **Education**             | Level of education (1: Below College, 2: College, 3: Bachelor, 4: Master, 5: Doctor) | Numerical  | 2, 1, 2, ...                     |
| **EducationField**        | Field of education (Life Sciences, Medical, Marketing, Technical Degree, Other) | Categorical | Life Sciences, Medical           |
| **EmployeeCount**         | Number of employees (always 1 in this dataset)                               | Numerical  | 1                                 |
| **EmployeeNumber**        | Unique identifier for each employee                                             | Numerical  | 1, 2, 4, ...                     |
| **EnvironmentSatisfaction** | Level of environment satisfaction (1: Low, 2: Medium, 3: High, 4: Very High)      | Numerical  | 2, 3, 4, ...                     |
| **Gender**                | Gender of the employee (Male, Female)                                          | Categorical | Male, Female                      |
| **HourlyRate**            | Hourly rate of the employee                                                    | Numerical  | 94, 61, 92, ...                  |
| **JobInvolvement**        | Level of job involvement (1: Low, 2: Medium, 3: High, 4: Very High)            | Numerical  | 3, 2, 2, ...                     |
| **JobLevel**              | Job level of the employee                                                        | Numerical  | 2, 2, 1, ...                     |
| **JobRole**               | Job role of the employee (Sales Executive, Research Scientist, etc.)           | Categorical | Sales Executive, Research Scientist |
| **JobSatisfaction**       | Level of job satisfaction (1: Low, 2: Medium, 3: High, 4: Very High)           | Numerical  | 4, 2, 3, ...                     |
| **MaritalStatus**         | Marital status of the employee (Single, Married, Divorced)                     | Categorical | Single, Married, Divorced         |
| **MonthlyIncome**         | Monthly income of the employee                                                  | Numerical  | 5993, 5130, 2090, ...             |
| **MonthlyRate**           | Monthly rate of the employee                                                   | Numerical  | 19479, 24907, 2396, ...           |
| **NumCompaniesWorked**     | Number of companies worked for                                                 | Numerical  | 8, 1, 6, ...                     |
| **Over18**                | Whether the employee is over 18 (Y/N)                                         | Categorical | Y                                 |
| **OverTime**              | Whether the employee works overtime (Yes/No)                                  | Categorical | Yes, No                          |
| **PercentSalaryHike**     | Percent salary hike                                                            | Numerical  | 11, 23, 15, ...                  |
| **PerformanceRating**     | Performance rating of the employee (1: Low, 2: Good, 3: Excellent, 4: Outstanding) | Numerical  | 3, 4, 3, ...                     |
| **RelationshipSatisfaction** | Level of relationship satisfaction (1: Low, 2: Medium, 3: High, 4: Very High)    | Numerical  | 1, 4, 2, ...                     |
| **StandardHours**         | Standard hours per week (mostly 80 in this dataset)                           | Numerical  | 80                                 |
| **StockOptionLevel**      | Stock option level                                                             | Numerical  | 0, 1, 0, ...                     |
| **TotalWorkingYears**     | Total years of working experience                                               | Numerical  | 8, 10, 7, ...                    |
| **TrainingTimesLastYear** | Number of times the employee received training last year                       | Numerical  | 0, 3, 3, ...                     |
| **WorkLifeBalance**       | Work-life balance (1: Bad, 2: Good, 3: Better, 4: Best)                        | Numerical  | 1, 3, 3, ...                     |
| **YearsAtCompany**        | Years spent at the company                                                     | Numerical  | 6, 10, 0, ...                    |
| **YearsInCurrentRole**    | Years spent in the current role                                                | Numerical  | 4, 7, 0, ...                    |
| **YearsSinceLastPromotion** | Years since the last promotion                                                  | Numerical  | 0, 1, 0, ...                     |
| **YearsWithCurrManager**  | Years spent with the current manager                                           | Numerical  | 5, 7, 0, ...                    |

Basic analysis reveals significant variation in attrition rates across different employee segments identified through K-Means clustering.  Further analysis explores the correlation between various factors and attrition within these clusters.  The goal is to identify key drivers of employee turnover to provide actionable insights for IBM.

## Usage
The project is implemented as a Jupyter Notebook (`demographic_anal.ipynb`).  It requires a CSV file named `Data.csv` (not included in this repository) containing the employee data.  Run the notebook sequentially to execute the analysis and generate the visualizations.

## Installation
1. **Clone the repository:**
   ```bash
   git clone <repository_url>
   ```
2. **Install dependencies:**
    ```bash
    pip install pandas scikit-learn seaborn matplotlib scipy numpy
    ```
3. **Place your `Data.csv` file** in the same directory as the notebook.
4. **Run the Jupyter Notebook:**  Open `demographic_anal.ipynb` in Jupyter Notebook or JupyterLab and execute the code cells.

*README.md was made with [Etchr](https://etchr.dev)*