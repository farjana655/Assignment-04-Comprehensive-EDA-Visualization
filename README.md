# Assignment-04-Comprehensive-EDA-Visualization

# Garments Job Risk Dataset — EDA & Data Cleaning

## Project Overview

This project focuses on Exploratory Data Analysis (EDA) and basic data-quality checking of a Garments Job Risk dataset.

The main goal is to understand the dataset structure, identify possible data-quality issues, and prepare a cleaner dataset for further analysis or machine learning.

## Dataset Columns

The dataset contains the following columns:

- `Name`
- `Garment_Name`
- `Experience_Years`
- `Job_Role`
- `Working_Hours_Per_Week`
- `Exposure_To_Chemicals`
- `Machine_Use`
- `Workstation_Ergonomics`
- `Injury_History`
- `Health_Condition`
- `Safety_Training`
- `Shift_Type`
- `Task_Rotation_Frequency`
- `Job_Risk`

## EDA & Data Quality Checks Performed

### 1. Dataset Shape

The shape of the dataset was checked to understand the number of rows and columns.

### 2. Descriptive Statistics

Statistical information about numerical columns was explored using:

```python
df.describe()
```
This helps understand values such as count, mean, standard deviation, minimum, quartiles, and maximum.

Duplicate rows were checked using:

```python
df.duplicated().sum()
```

Result:

- No duplicate rows were found.

Because no duplicate rows were found, there was no need to remove duplicates.

### 4. Wrong / Inconsistent Format Check

The data was inspected to identify values that may have an unexpected format.

Examples of checks include:

```python
df.info()
df.dtypes
```

### 5. Outlier Check

Outliers were investigated using boxplots and the IQR method.

These values were not automatically removed because an unusual value is not necessarily an incorrect value. The values may represent a valid number of injury occurrences.

# No significant outliers were found in the numerical features.

### 6. Noisy Data Filtering

Negative values in numerical columns were checked.
The shape before and after filtering was compared.

The shape remained the same, which means no negative values were found and no rows were removed during this filtering step
### 7. Data Type Consistency Check

Data types were checked to ensure that each column is stored in an appropriate format.

### 8. Schema Validation

Schema validation was performed to check whether the expected columns exist in the dataset.


### 9. Imbalanced Data Check

The target column `Job_Risk` was checked for class imbalance.

Result:

| Job_Risk | Count | Percentage |
|---|---:|---:|
| Low | 1050 | 42% |
| Medium | 900 | 36% |
| High | 550 | 22% |

The dataset is not perfectly balanced. `Low` risk is the most common class, while `High` risk is the least common.

However, the imbalance is not extremely severe because all three classes have a reasonable number of observations.

## Final Clean Dataset

After completing the data quality assurance and cleaning steps, the final dataset was saved as a CSV file.

## Recommended EDA Flow

The overall workflow followed in this project is:

1. Load the dataset
2. Check dataset shape
3. Explore descriptive statistics
4. Check duplicate rows
5. Check data formats
6. Check outliers
7. Check and filter noisy/invalid numerical values
8. Check data type consistency
9. Validate the dataset schema
10. Check target-class imbalance
11. Save the final cleaned dataset

## Conclusion

The dataset was examined for common data-quality issues including duplicate rows, unexpected formats, outliers, negative numerical values, inconsistent data types, schema problems, and class imbalance.

The cleaning process should only remove data when there is sufficient evidence that the data is invalid. Unusual values should not automatically be treated as errors.


