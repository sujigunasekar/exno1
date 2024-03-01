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

### Coding and Output
```
Name :Suji.G
Register Number : 212222230152
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
data = pd.read_csv("/content/SAMPLEIDS.csv")
data.head()
```
![307662516-adeed988-0f22-4477-aa1f-fc0767f58229](https://github.com/sujigunasekar/exno1/assets/119559822/5053a26e-03df-4ee4-861b-3adbae5836c5)
```
data = pd.get_dummies(data)
data.isnull().sum()
```
![307662612-16a9d857-c8ed-412f-b196-7e83fbc27639](https://github.com/sujigunasekar/exno1/assets/119559822/fafa5543-a30a-496a-a1c0-1712d0dc74a7)
```
columns_with_null = data.columns[data.isnull().any()]
import seaborn as sns
plt.figure(figsize=(10,10))
sns.barplot(columns_with_null)
plt.title("NULL VALUES")
plt.show()
```
![307662689-a140ef65-d5d0-4e5d-bb99-edb3ee4c67db](https://github.com/sujigunasekar/exno1/assets/119559822/a15db12b-ab9e-4f6e-a990-ef24603721cd)
```
for column in columns_with_null:
    median = data[column].median()  
    data[column].fillna(median, inplace=True)
data.isnull().sum().sum()
```
![307662793-2aa701f0-302e-4f12-acfe-4c08d4891b83](https://github.com/sujigunasekar/exno1/assets/119559822/491d03d3-8b07-4616-b1ee-bc081916ddbe)
### IQR
```
import pandas as pd
import seaborn as sns
ir = pd.read_csv("/content/iris (1).csv")
ir.head()
```
![307662926-b6163966-c207-4ebe-b859-26fc1f31c052](https://github.com/sujigunasekar/exno1/assets/119559822/c3730b8b-2794-4e83-af84-23f29e882c5d)
```
ir.describe()
```
![307663064-790ec93f-9b41-45f8-9a3c-8eecbd7b5878](https://github.com/sujigunasekar/exno1/assets/119559822/b5f9187d-49e5-4d59-bfd6-799542dfffda)
```
sns.boxplot(x='sepal_width',data=ir)
```
![307663145-fa475df8-36e0-4a3d-9d95-895486097f62](https://github.com/sujigunasekar/exno1/assets/119559822/a8a1678b-5484-48a2-93fa-9eeb0d758b25)
```
c1=ir.sepal_width.quantile(0.25)
c3=ir.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)
```
![307663214-7c7de03a-8c19-4629-adee-d2f8ddfc7550](https://github.com/sujigunasekar/exno1/assets/119559822/44201373-5e98-402a-9cd4-ea749a417407)
```
rid=ir[((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']
```
![307663280-c891d33a-411a-43cb-88bb-0614d0cbfbaa](https://github.com/sujigunasekar/exno1/assets/119559822/585c77f8-a955-4a0f-9f04-d8830b9fa8f7)
```
delid=ir[~((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
delid
```
![307663361-7f10012d-255b-42c7-88fb-7f49c0bf4e3e](https://github.com/sujigunasekar/exno1/assets/119559822/09288c4f-1be5-43b9-93b9-7b9556cd1667)
```
sns.boxplot(x='sepal_width',data=delid)
```
![307663437-d94161ba-b61b-43aa-b3f7-3c9f352eda00](https://github.com/sujigunasekar/exno1/assets/119559822/46eb4236-a8d8-452c-9141-366dd232c5c7)
### Z Score
```
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
import scipy.stats as stats
dataset=pd.read_csv("/content/heights.csv")
dataset
```
![307663558-f01f125b-7c8e-4fba-9a31-6c09ef3b6974](https://github.com/sujigunasekar/exno1/assets/119559822/cdb9897b-8331-44c1-97a3-9095fe9459eb)

# Result
Thus the given data is read,cleansed and cleaned data is saved into the file.

