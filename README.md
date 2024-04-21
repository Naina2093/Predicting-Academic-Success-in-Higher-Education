# Predicting Academic Success and Reducing Dropout Rates in Higher Education

This project focuses on analyzing enrollment data from a higher education institution, specifically undergraduate degrees in fields such as agronomy, design, education, nursing, journalism, management, social service, and technology. The objective is to develop supervised machine learning models that accurately predict a student’s academic success based on various factors including time of enrollment, student demographics, academic performance in the first and second semester, parents’ qualifications, and economic conditions at the time of course completion.

Through leveraging this dataset, our aim is to explore the predictive capacity of these factors in relation to the likelihood of academic dropout. By conducting exploratory analysis, calculating summary statistics, and generating informative graphs using Jupyter Notebook, we seek to derive valuable insights from the data. Ultimately, our goal is to identify students who may be at risk of dropping out early in their academic journey, allowing for the implementation of appropriate support measures.


## Business Objectives

- Supervised machine learning models for predicting academic success and dropout risk.
- Actionable recommendations based on insights derived from the data analysis.
- Contribution to the reduction of dropout rates in higher education by proactively identifying and supporting at-risk students.

By making this project publicly available on GitHub, I aim to foster collaboration, knowledge sharing, and further research in the domain of educational data analytics.


### Tools used

- Microsoft Excel

- Python

- Machine Learning techniques

### Methodology

**Data Cleaning:**

- The original dataset comprises 36 variables and 4424 observations, including both numerical and categorical variables.
- Initial examination revealed no missing values in the dataset.
- Identified and removed 12 unwanted columns that were deemed irrelevant for the analysis, such as application order, application mode, and non-evaluated curricular units.

**Data Transformation:**

- All columns, including categorical variables, were initially provided in numerical format.
- Utilizing the data dictionary, numerical codes associated with each unique class name of categorical variables were replaced with their corresponding names.
- This transformation facilitated the interpretation of the data and the creation of effective visualizations. For instance, numerical codes for variables like Marital status, Previous qualification, Course, Mother’s and Father’s qualifications, Occupations, Nationality, and Gender were replaced with meaningful labels.

**Categorical Variable Encoding:**

- Categorical variables, such as Marital status, Previous qualification, Course, Mother’s and Father’s qualifications, Occupations, Nationality, and Gender, were encoded using their respective numerical codes initially.
- These numerical codes were replaced with corresponding names to enhance the interpretability of the data and facilitate meaningful analysis and visualization.
- For example, replacing numerical codes with descriptive labels like 'Single' for Marital status improves audience comprehension and aids in creating more informative visualizations.

**Descriptive Analysis**: 

- Enrolled students exhibit a higher average previous qualification compared to admission grades, suggesting a potentially higher aptitude level during enrollment.
- Grades obtained in the first and second semesters show no significant difference, indicating consistent performance overall.
- Median age at enrollment is 20 years, chosen over mean due to outliers, including enrollments above 70 years.
- A small percentage (1%) of enrolled students require educational special needs, while 11% have debt and over 88% pay tuition fees on time. Only one-third are scholarship holders.

**Exploratory Data Analysis (EDA) Highlights:**

Boxplots of grades in the first and second semesters reveal lower median grades and higher variation among dropout students compared to graduates and enrolled students.
Scatter plot of unemployment and inflation rates during the expected course completion date suggests a normal economic condition with a negative correlation between inflation and unemployment.
Heatmap of marital status vs. academic success status indicates that single students are more likely to enroll, drop out, or graduate, raising concerns about dropout rates.
Stacked bar graph comparing academic success status between daytime and evening attendance shows no major difference in distribution, with more students enrolled in daytime classes.

## Final Insights:

- Initial semester grades may serve as indicators of academic success, emphasizing the importance of early performance monitoring and intervention.
- Economic conditions seem stable, suggesting minimal impact on student success, although further analysis may be warranted.
- Marital status may play a role in academic outcomes, highlighting the need for targeted support for single students.
- Attendance mode (daytime vs. evening) does not significantly affect academic success, implying the need for comprehensive support strategies regardless of class schedule.

## Feature Engineering:

- Categorized Mother’s and Father’s occupations and qualifications into simpler groups to enhance interpretability.
- Dropped records with student ages above 70 years and binned remaining ages into categories (child, adult, senior).
- Combined 'enrolled' and 'graduate' classes of the target variable into 'non-dropouts' to focus on predicting dropout students.
- Encoded categorical variables using various techniques such as label encoding and target encoding for different columns.
- Standardized numerical data to ensure features are on similar scales, preventing dominance during model training.

## Predictive Modeling:

- Checked data imbalance, with around 32% belonging to 'dropout' class and 67% to 'non-dropout' class.
- Used 'stratify=y' to ensure balanced train-test splits.

**Decision Tree Model:**

Achieved an accuracy of 86%, providing interpretability but prone to overfitting.
Important features include curricular grades and tuition fee status.

**Random Forest Model:**

Accuracy of 84% with reduced overfitting compared to decision trees.
Key predictors include debtor status and parental occupation.

**Gradient Boost Model:**

Accuracy improved to 87% by sequentially correcting errors of previous trees.
Notable predictors are curricular grades and tuition fee status.

**XG Boost Model:**
Addressed imbalance issue with accuracy of 85.5%.
Important features: tuition fee status, curricular grades, and father’s qualification.

**Logistic Regression (Lasso & Ridge):**

Achieved around 79% accuracy, focusing on feature selection and regularization.
Identified key predictors influencing dropout likelihood.

**Support Vector Machine (SVM):**

SVM model with linear kernel achieved 78% accuracy, addressing imbalance.
Notable features: course category, tuition fee status, and age at enrollment.

**Hyper-tuned SVM Model:**

GridSearchCV optimized hyperparameters, yielding 78% accuracy.
Improved precision for predicting dropout students.

**Model Comparison:**

Decision Tree, Random Forest, Gradient Boost, and XG Boost models perform well with accuracies ranging from 84% to 87%.
Logistic Regression models offer interpretability and precision in predicting dropout students.
SVM models address imbalance but show slightly lower accuracy compared to logistic regression.
Hyper-tuned SVM model improves precision for predicting dropout students.
Ridge regularized Logistic Regression model chosen for analysis due to higher recall for positive class prediction.

**Conclusion:**

Ridge regularized Logistic Regression model selected for analysis due to balanced performance metrics and focus on predicting dropout students.
All models provide insights into important predictors of dropout likelihood.
It's essential to consider metrics beyond accuracy, such as precision and recall, especially for imbalanced datasets.

Goal: The project aims to predict student dropout risk to provide targeted support, starting with data introduction, cleansing, and exploratory analysis.

Data Insights: Data skew towards successful graduates, age outliers, and gender-based dropout proportions were observed.

Modeling Approach: Focused on tree-based classification models and supervised learning techniques like Logistic Regression and SVM.

Best Model: The hyper-tuned XG Boost model emerged as the most reliable, achieving 87% accuracy and addressing class imbalance effectively.

Key Predictors: Features like curricular grades, tuition fee status, and father's qualification were identified as crucial in dropout prediction.

Intervention Strategies: Insights from the model can inform early intervention strategies like financial aid, mentorship, and gender-specific support programs.

Future Directions: Further research can explore the impact of mother's occupation and course category on dropout rates and improve model performance.

**Next Steps:**

Implementation: Utilize model insights to implement targeted intervention programs for at-risk students.

Data Enhancement: Explore further data collection and improvements to address imbalance issues and enhance model accuracy.

Continuous Monitoring: Regularly monitor model performance and refine strategies based on feedback and new data.
