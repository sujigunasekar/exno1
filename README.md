# Exno:1
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

### Code for DATA 1
```
Name :Suji.G
Register Number : 212222230152
**Data Cleaning - Data_set.csv**
import numpy as np
import pandas as pd
import seaborn as sbn
df = pd.read_csv("/content/Data_set.csv")
print(df)
df.head(10)
df.info()
df.isnull()
df.isnull().sum()
df['show_name'] = df['show_name'].fillna(df['aired_on'].mode()[0])
df['aired_on'] = df['aired_on'].fillna(df['aired_on'].mode()[0])
df['original_network'] = df['original_network'].fillna(df['aired_on'].mode()[0])
df.head()
df['rating'] = df['rating'].fillna(df['rating'].mean())
df['current_overall_rank'] = df['current_overall_rank'].fillna(df['current_overall_rank'].mean())
df.head()
df['watchers'] = df['watchers'].fillna(df['watchers'].median())
df.head()
df.info()
df.isnull().sum()
```
# OUPUT for DATA 1

![225975786-c1294853-cfe5-4058-92bc-3c582123a275](https://github.com/sujigunasekar/exno1/assets/119559822/5b5e8045-9707-44e9-8908-aee3de9fa069)

# Before Cleaning

![225976025-f38b42e2-fe41-4de4-8716-e1f2633a89e0](https://github.com/sujigunasekar/exno1/assets/119559822/e0040428-5986-4d09-9a82-f795f9ff38b8)

![225978903-d7d57049-ddfd-4daf-bfde-8869ee6eb0ad](https://github.com/sujigunasekar/exno1/assets/119559822/5d6f7717-e2fe-4a19-806c-848b9f637b72)

![225976349-ccc38124-41ee-42c4-879e-e9ce1c9d0409](https://github.com/sujigunasekar/exno1/assets/119559822/0d9befb1-e86d-4c22-b6f0-0143df236f71)

![225976485-d53c488c-2f69-48eb-82cd-9e4ed88e0b7d](https://github.com/sujigunasekar/exno1/assets/119559822/6edc9c65-654d-4807-8c7d-2a63a30c6f1f)
# Mode

![225976693-63e838b3-2813-43e9-a9e1-2f3689bbd0d5](https://github.com/sujigunasekar/exno1/assets/119559822/614b2e77-9683-4845-b99b-b1aadfbd0d72)
Mean

![225976895-84bb0106-f0d7-42da-887c-313e30754449](https://github.com/sujigunasekar/exno1/assets/119559822/43bc985c-1716-44f7-a788-1e72eb2ebf46)
# Median
![225976981-3c65e108-3076-4e20-8e9f-5d534b5fa045](https://github.com/sujigunasekar/exno1/assets/119559822/a60b2529-0ec3-4cd5-9180-c6f566255536)
# After cleaning

![225977576-76bd3bb4-56ec-4a22-b29a-c068def0890c](https://github.com/sujigunasekar/exno1/assets/119559822/ef98ae04-3a48-4ead-a238-0bff96948e2b)

![225977466-df5f09b8-653c-4233-94cc-e595953f1f56](https://github.com/sujigunasekar/exno1/assets/119559822/7feef4f0-c3af-4b70-8e64-dc73f9d70835)

### Code for DATA 2
```
Name :Suji.G
Register Number : 212222230112
import pandas as pd
import numpy as np
import seaborn as sns
df = pd.read_csv("/content/Loan_data.csv")
df
df.head()
df.describe()
df.tail()
df.isnull()
df.isnull().sum()
df.shape
df.columns
df.duplicated

#Using mode method to fill the data in columns as Object(String)
#mode()[0] - Takes the most reccuring value and fills the empty cells
df['Gender'] = df['Gender'].fillna(df['Gender'].mode()[0])
df['Dependents'] = df['Dependents'].fillna(df['Dependents'].mode()[0])
df['Self_Employed'] = df['Self_Employed'].fillna(df['Self_Employed'].mode()[0])

#Using mean method to fill the data
df['LoanAmount'] = df['LoanAmount'].fillna(df['LoanAmount'].mean())
df['Loan_Amount_Term'] = df['Loan_Amount_Term'].fillna(df['Loan_Amount_Term'].mean())
df['Credit_History'] = df['Credit_History'].fillna(df['Credit_History'].mean())

sns.boxplot(y="LoanAmount",data=df)

#Checking the total no.of null values
again
df.isnull().sum()

#Checking info of the dataset to check all the columns have entries
df.info()
```
# Output for DATA 2

![225985839-fcc1db78-a1fe-4e0a-9b1a-76672ffe7c1c](https://github.com/sujigunasekar/exno1/assets/119559822/3fc3a9b8-952e-4349-a92c-697fb10bc0b6)

![225990612-65f2b27d-5189-4ea5-a856-59c29d597adc](https://github.com/sujigunasekar/exno1/assets/119559822/8c249d15-b8e6-4e92-aa1e-40173daeee24)
Before Cleaning

![225986091-b2841eec-4db6-45ce-9c0b-c0329c579254](https://github.com/sujigunasekar/exno1/assets/119559822/356073e9-b823-453a-914d-44314489055c)

![225986249-80797c10-6ef4-4545-86e5-b049d7e32e15](https://github.com/sujigunasekar/exno1/assets/119559822/9225ad7e-c361-4f6d-b18b-994e053e972a)

![225986398-1e37fb97-fd72-4cb8-a2df-505e3824b8d6](https://github.com/sujigunasekar/exno1/assets/119559822/2f03f154-eea4-4024-aa48-53117d5c22cf)

![225986471-4c0ef827-81d8-4f46-8c65-41ce405f1da4](https://github.com/sujigunasekar/exno1/assets/119559822/7d45b8ee-e4c9-4e92-a2c4-3a9630aa1b76)

![225986537-12c311dc-3448-4b83-b360-5fa893ab4df1](https://github.com/sujigunasekar/exno1/assets/119559822/02cbd5a1-33b3-4689-8af9-7db18098a596)

![225986616-0643b98c-1906-4714-ac3c-431d9f2b1736](https://github.com/sujigunasekar/exno1/assets/119559822/5227f87b-fcc8-4e64-bc62-5f7b48091110)
# Mode
![225986723-0b3fb589-fb86-498a-aeb0-a2932d402174](https://github.com/sujigunasekar/exno1/assets/119559822/0d57f958-dbf9-4f97-92fa-d383f32101ee)
# Mean
![225986794-38573f63-1ea0-4b38-b24a-f59d64bbae8c](https://github.com/sujigunasekar/exno1/assets/119559822/d98b5ae2-0526-445b-8d39-ccfb5269f32b)
# Median
![225986932-7623b229-3e0b-4fcf-9667-6ce32d8085f8](https://github.com/sujigunasekar/exno1/assets/119559822/d2784233-b3e3-4c80-b67f-e42c75ba3a9a)

# After cleaning

![225987124-ba12fa46-54d0-4ab5-86c1-c020417650b8](https://github.com/sujigunasekar/exno1/assets/119559822/b811e5c3-2bae-4335-bcc3-24af368ab952)

# Result
Thus the given data is read,cleansed and cleaned data is saved into the file.

