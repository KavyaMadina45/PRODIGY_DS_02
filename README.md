# IMDB Top 1000 Movies Data Analysis

This project involves analyzing the IMDB Top 1000 Movies dataset. Various data analysis tasks are performed, including data cleaning, handling missing values, data visualization, and statistical analysis using Python libraries such as pandas, numpy, matplotlib, and seaborn.

## Project Description

The project demonstrates how to:
1. Load and inspect the IMDB Top 1000 Movies dataset.
2. Clean the dataset by removing NaN values and duplicates.
3. Perform various data visualizations, including histograms, box plots, scatter plots, line plots, and violin plots.
4. Conduct univariate and bivariate analyses on key features of the dataset.

## Installation Instructions

To run this project, you need to have Python installed along with the following libraries:
- pandas
- numpy
- matplotlib
- seaborn

You can install these libraries using pip:
```sh
pip install pandas numpy matplotlib seaborn
 ```
**Usage**
1) Place your dataset file (imdb_top_1000.csv) in an accessible directory.
2) Update the file path in the code to match the location of your dataset file.
3) Run the script to perform the analysis and generate visualizations.
 ```sh
   import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np

# Load the dataset
x = '/home/kavya/Downloads/imdb_top_1000.csv'
df = pd.read_csv(x)

# Display the dataframe
print(df)

# Check for NaN values
print(df.isnull())

# Drop duplicates and NaN values
df = df.drop_duplicates()
df = df.dropna()

# Display specific columns
print(df[['IMDB_Rating', 'Meta_score']])

# Fill NaN values in specific columns with 20
print(df[['IMDB_Rating', 'Meta_score']].fillna(20))

# Display first 2 rows of specific columns
print(df[['IMDB_Rating', 'Meta_score']].head(2))

# Correlation between rating and meta score
print(df[['IMDB_Rating', 'Meta_score']].corr())

# Descriptive statistics
print(df.describe())

# Univariate analysis: No of Votes distribution using histogram
plt.hist(df['No_of_Votes'], bins=10, color="green")
plt.ylabel("No of bins")
plt.title("Visualization of distribution of No of votes")
plt.show()

# Box Plot for No of Votes
plt.figure(figsize=(10, 8))
sns.boxplot(x=df['No_of_Votes'])
plt.title('Box Plot of votes')
plt.show()

# Bivariate analysis: Rating and Meta score using scatter plot
rating = df['IMDB_Rating'].values
score = df['Meta_score'].values
plt.scatter(rating, score, marker='*', color="orange")
plt.xlabel("Rating")
plt.ylabel("Meta Score")
plt.title("Bivariate Analysis of Rating and Meta Score")
plt.show()

# Bivariate analysis: Rating and Meta score using line plot
plt.plot(rating, score, marker='p', color="navy")
plt.xlabel("Rating")
plt.ylabel("Meta Score")
plt.title("Bivariate Analysis of Rating and Meta Score by Line Plot")
plt.show()

# Violin Plot for No of Votes
plt.figure(figsize=(10, 6))
sns.violinplot(y=df['No_of_Votes'], color="black")
plt.title('Violin Plot of Votes')
plt.show()

# Pair plot of the dataframe
sns.pairplot(df)
plt.show()

# Histograms for all columns
df.hist(figsize=(10, 8), bins=20, color="deeppink")
plt.show()
```
**Features**
1) Data Loading: Efficiently loads the IMDB Top 1000 Movies dataset from a CSV file.
2) Data Cleaning: Removes NaN values and duplicates from the dataset.
3) Data Selection: Displays specific columns for inspection.
4) Data Visualization: Creates various plots (histogram, box plot, scatter plot, line plot, violin plot) for univariate and bivariate analyses.
5) Descriptive Statistics: Provides statistical summaries and correlations of key features.

**Contributing**

If you want to contribute to this project, please follow these steps:

* Fork the repository.
* Create a new branch (git checkout -b feature-branch).
* Make your changes.
* Commit your changes (git commit -m 'Add new feature').
* Push to the branch (git push origin feature-branch).
* Create a new Pull Request.

# License
This project is licensed under the MIT License - see the LICENSE file for details.
# Contact Information
For any questions or issues, please contact Kavya at madinakavya6@gmail.com

