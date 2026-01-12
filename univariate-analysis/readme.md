# Data Visualization Notes

## 1. Categorical Data Analysis

### a. Countplot
- **Purpose**: Visualize frequency distribution of categorical variables
- **Example**: `sns.countplot(df['Embarked'])`
- **Features**:
  - Shows count of observations in each category
  - Bars represent different categories
  - Useful for comparing category frequencies
  - **From output**: Embarked categories show different passenger counts

### b. Pie Chart
- **Purpose**: Show proportional composition of categories
- **Example**: `df['Sex'].value_counts().plot(kind='pie', autopct='%.2f')`
- **Features**:
  - `autopct='%.2f'` displays percentage values with 2 decimal places
  - Shows relative proportion of each category
  - **From output**: Sex distribution shows percentage of males vs females

## 2. Numerical Data Analysis

### a. Histogram
- **Purpose**: Show frequency distribution of numerical data
- **Example**: `plt.hist(df['Age'], bins=5)`
- **Output Interpretation**:
  - First array `[100., 346., 188., 69., 11.]`: Frequency counts per bin
  - Second array: Bin edges (0.42 to 80.0 divided into 5 bins)
  - **Insights**: Most passengers are young (0-32 years old)

### b. Distplot
- **Purpose**: Combined histogram with kernel density estimate
- **Example**: `sns.distplot(df['Age'])`
- **Features**:
  - Shows smooth probability density curve
  - Combines histogram with density plot
  - Useful for understanding distribution shape

### c. Boxplot
- **Purpose**: Visualize distribution statistics and outliers
- **Example**: `sns.boxplot(df['Age'])`
- **Features**:
  - Shows median, quartiles, and outliers
  - Box represents interquartile range (IQR)
  - Whiskers show data range (excluding outliers)

## 3. Statistical Summary

From the Age column analysis:
- **Minimum**: 0.42 years
- **Maximum**: 80.0 years  
- **Mean**: 29.7 years
- **Skewness**: 0.389
  - Positive skew (right-skewed)
  - Mean > Median (typical for age data)
  - Most passengers are younger than the mean age

## Key Observations:
1. **Age Distribution**: Right-skewed with concentration in 20-40 age range
2. **Data Range**: Wide age range from infants to elderly
3. **Visualization Choices**:
   - Countplot/Pie for categorical data
   - Histogram/Distplot for distribution shape
   - Boxplot for statistics and outliers

## Tips:
1. Use countplots for quick categorical frequency checks
2. Use histograms with appropriate bins (default=10, here bins=5)
3. Distplots add density estimation to histograms
4. Boxplots help identify outliers quickly
5. Always check basic statistics (min, max, mean, skewness)