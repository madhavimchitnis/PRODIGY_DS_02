# PRODIGY_DS_02
Following are the steps performed to accomplish this task:

## Steps for Data Cleaning and Exploratory Data Analysis (EDA) on Titanic Dataset

1. *Importing Necessary Libraries*:
   - Imported `pandas` for data manipulation.
   - Imported `seaborn` and `matplotlib.pyplot` for data visualization.

2. *Loading the Dataset*:
   - Loaded the Titanic dataset using `pd.read_csv()`.

3. *Displaying Initail Data*:
   - Displayed the first few rows using `df.head()`.
   - Obtained summary information using `df.info()`.

4. *Checking for Missing Values*:
   - Checked for missing values in each column using `df.isnull().sum()`.

5. *Handling Missing Values*:
   - Filled missing values in the 'Age' column with the median age.
   - Dropped the 'Cabin' column due to a high number of missing values.
   - Filled missing values in the 'Embarked' column with the most frequent value.

6. *Checking for and Removing Duplicate Rows*:
   - Checked for duplicate rows using `df.duplicated().sum()`.
   - Removed duplicate rows using `df.drop_duplicates()`.


7. *Visualizing Data Distributions*:
   - Used histograms to visualize the distribution of 'Fare', 'Age', and their distributions across different categories:
     - Histogram for 'Fare' using `sns.histplot()`.
     - Histogram for 'Age' using `sns.histplot()`.
     - Count plot for 'Survived' using `sns.countplot()`.

8. *Capping Outliers*:
   - Capped 'Fare' values at the 95th percentile to handle outliers.

9. *Univariate Analysis*:
    - Visualized the distribution of 'Age' and 'Survived' using histograms and count plots.

10. *Bivariate Analysis*:
    - Visualized the distribution of 'Age' by survival status using a faceted histogram.
    - Visualized the distribution of 'Fare' by passenger class using a faceted histogram.

By following these steps, data cleaning and exploratory data analysis on the Titanic datasetwas performed.
