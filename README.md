#EX.NO:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output

# Step 1: Import Required Libraries
```
import pandas as pd
import numpy as np
from scipy import stats
import seaborn as sns
import matplotlib.pyplot as plt
```

```
# Step 2: Read the Dataset

# Replace with your actual CSV file
df1 = pd.read_csv('Data_set.csv')
df1.head()
```
<img width="1906" height="872" alt="Screenshot 2026-02-10 112601" src="https://github.com/user-attachments/assets/2dcaebab-3f3c-4631-96be-ffff5696f8c8" />

```
# Step 3: Dataset Information
df1.info()
df1.describe()
```
<img width="1905" height="1012" alt="Screenshot 2026-02-10 112615" src="https://github.com/user-attachments/assets/7427d6dd-3d00-491c-8cde-7374df54ebef" />

```
# Step 4: Handling Missing Values
# Check Null Values
df1.isnull()
df1.isnull().sum()
```
<img width="1911" height="580" alt="Screenshot 2026-02-10 112658" src="https://github.com/user-attachments/assets/5c4d56a4-52eb-45f1-b54b-dc1f599d4b7c" />

```
# Fill Missing Values with 0
df1_fill_0 = df1.fillna(0)
df1_fill_0
```
<img width="1909" height="769" alt="Screenshot 2026-02-10 112715" src="https://github.com/user-attachments/assets/f96c7521-29a1-4103-8a0b-f474fffae066" />

```
# Forward Fill
df1_ffill = df1.ffill()
df1_ffill

```
<img width="1914" height="775" alt="Screenshot 2026-02-10 112725" src="https://github.com/user-attachments/assets/e990c96b-88a1-489f-80ef-5ad1ff3066af" />

```
# Backward Fill
df1_bfill = df1.bfill()
df1_bfill
```
<img width="1919" height="772" alt="Screenshot 2026-02-10 112735" src="https://github.com/user-attachments/assets/14333118-1fe5-46bb-aa26-6ccc32c2a8e7" />


```
# Fill with Mean (Numerical Column Example)

df1['num_episodes'] = df1['num_episodes'].fillna(df1['num_episodes'].mean())
df1
```
<img width="1920" height="843" alt="Screenshot 2026-02-10 112744" src="https://github.com/user-attachments/assets/cbf5c95e-4958-410b-96fe-f282b12c74c1" />


```
# Drop Missing Values
df1_dropna = df1.dropna()
df1_dropna
```

```

#Step 5: Save Cleaned Data
df1_dropna.to_csv('Data_set_new.csv', index=False)
```
<img width="1916" height="929" alt="Screenshot 2026-02-10 112756" src="https://github.com/user-attachments/assets/9dfe1bda-16ab-44f9-9adf-b6e7aa465b2b" />


```
# OUTLIER DETECTION
# Step 6: IQR Method (Using Iris Dataset)
ir = pd.read_csv('Data_set_new.csv')
ir.head()
ir.info()
ir.describe()
```

```
#Boxplot for Outlier Detection
sns.boxplot(x=ir['num_episodes'])
plt.show()

```
<img width="1920" height="718" alt="Screenshot 2026-02-10 112808" src="https://github.com/user-attachments/assets/ce6eea01-1562-4f70-90fe-4462f44e5096" />

<img width="1914" height="655" alt="Screenshot 2026-02-10 112823" src="https://github.com/user-attachments/assets/ea8f1b16-1099-43b1-9f95-a0c456eff115" />





         <<include your coding and its corressponding output screen shots here>>
# Result
          <<include your Result here>>
