# customer-satisfaction-analysis
customer-satisfaction-analysis
# Customer Satisfaction Analysis using Statistical Methods

In this project, we analyze customer satisfaction data using statistical techniques to draw insights and test hypotheses.

## Key Concepts Used
- Descriptive Statistics (Mean, Median, Mode, Std Dev)
- Z-Test & T-Test
- Hypothesis Testing
- Visualization using Seaborn & Matplotlib
- Business Insight Generation

## Dataset
The dataset is simulated and contains 300 customer records with the following features:
- Customer_ID
- Satisfaction_Score (1-10)
- Age
- Gender
- Product_Category
- Region

# 📦 Importing Libraries
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
from scipy import stats

# 📂 Load Dataset
df = pd.read_csv("dataset.csv")
df.head()
# 📊 Descriptive Statistics
print("Mean:", df['Satisfaction_Score'].mean())
print("Median:", df['Satisfaction_Score'].median())
print("Mode:", df['Satisfaction_Score'].mode()[0])
print("Std Dev:", df['Satisfaction_Score'].std())
print("Variance:", df['Satisfaction_Score'].var())

# 📈 Distribution Plot
sns.histplot(df['Satisfaction_Score'], kde=True, bins=15)
plt.title("Distribution of Satisfaction Scores")
plt.show()
# 🧪 One-Sample T-Test
# H0: Mean satisfaction = 7
t_stat, p_val = stats.ttest_1samp(df['Satisfaction_Score'], 7)
print("T-stat:", t_stat, "| P-value:", p_val)

# 👩‍🦰 Gender Comparison
male_scores = df[df['Gender'] == 'Male']['Satisfaction_Score']
female_scores = df[df['Gender'] == 'Female']['Satisfaction_Score']
t_stat, p_val = stats.ttest_ind(male_scores, female_scores)
print("T-stat:", t_stat, "| P-value:", p_val)
# ✅ Conclusion
print("Analysis Complete - Statistical insights generated.")
