import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Loading the dataset
df = pd.read_csv('train.csv')

# Displaying the first few rows of the dataset
print("First few rows of the dataset:")
print(df.head())

# Summarized information about the dataset
print("\nSummary information about the dataset:")
print(df.info())

# Checking for missing values
print("\nMissing values in the dataset:")
missing_values = df.isnull().sum()
print(missing_values)

# Filling missing values in 'Age' with the median age
df['Age'].fillna(df['Age'].median(), inplace=True)

# Dropping the 'Cabin' column due to the high number of missing values
df.drop(columns=['Cabin'], inplace=True)

# Filling missing values in 'Embarked' with the most frequent value
df['Embarked'].fillna(df['Embarked'].mode()[0], inplace=True)

# Checking for duplicate rows
print("\nNumber of duplicate rows:")
duplicate_rows = df.duplicated().sum()
print(duplicate_rows)

# Removing duplicate rows
df.drop_duplicates(inplace=True)

# Checking data types
print("\nData types of each column:")
print(df.dtypes)


# Visualizing distribution of 'Fare' using a histogram
print("\nHistogram for 'Fare' to visualize distribution:")
sns.histplot(df['Fare'], bins=30, kde=True)
plt.title('Histogram of Fare')
plt.xlabel('Fare')
plt.ylabel('Frequency')
plt.show()

# Capping the 'Fare' values at the 95th percentile to handle outliers
fare_cap = df['Fare'].quantile(0.95)
df['Fare'] = df['Fare'].apply(lambda x: fare_cap if x > fare_cap else x)

# Summary statistics for numerical columns
print("\nSummary statistics for numerical columns:")
print(df.describe())

# Univariate Analysis
print("\nUnivariate Analysis: Distribution of 'Age'")
sns.histplot(df['Age'], bins=20, kde=True)
plt.title('Distribution of Age')
plt.xlabel('Age')
plt.ylabel('Frequency')
plt.show()

print("\nUnivariate Analysis: Count plot of 'Survived'")
sns.countplot(x='Survived', data=df)
plt.title('Survival Count')
plt.xlabel('Survived')
plt.ylabel('Count')
plt.show()

# Bivariate Analysis
print("\nBivariate Analysis: Distribution of 'Age' by 'Survived'")
g = sns.FacetGrid(df, col='Survived')
g.map(sns.histplot, 'Age', bins=20, kde=True)
g.set_titles('Survived: {col_name}')
g.set_axis_labels('Age', 'Frequency')
plt.show()

print("\nBivariate Analysis: Distribution of 'Fare' by 'Pclass'")
g = sns.FacetGrid(df, col='Pclass')
g.map(sns.histplot, 'Fare', bins=30, kde=True)
g.set_titles('Pclass: {col_name}')
g.set_axis_labels('Fare', 'Frequency')
plt.show()
