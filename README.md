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

# Coding 
```
import numpy as np
import pandas as pd
df = pd.read_csv("SAMPLEIDS.csv")
df
```

# Output
<img width="888" height="711" alt="Screenshot 2025-08-30 133000" src="https://github.com/user-attachments/assets/0e3e6425-15a4-47aa-a15a-2a5010b42cdc" />

```
df.head()
```

# Output
<img width="837" height="280" alt="image" src="https://github.com/user-attachments/assets/b889c1a0-d49e-4347-ab75-a2f5fa82e8e7" />

```
df.tail()
```
# Output
<img width="852" height="185" alt="image" src="https://github.com/user-attachments/assets/75ed5ed1-dfc1-4394-9fe6-7a815edbabe9" />

```
df.head(3)
```
# Output
<img width="818" height="176" alt="image" src="https://github.com/user-attachments/assets/704f39ec-185d-41a2-a6de-afd65766c15e" />

```
df.tail(3)
```
# Output
<img width="856" height="129" alt="image" src="https://github.com/user-attachments/assets/5fc3c2da-8ad7-474f-bdf8-36149001daf3" />

```
df.isnull()
```
# Output
<img width="698" height="658" alt="image" src="https://github.com/user-attachments/assets/04fd6af6-4368-4e93-bd92-dc2fd47f0b22" />

```
df.isnull().sum()
```
# Output
<img width="278" height="438" alt="image" src="https://github.com/user-attachments/assets/d71a8a44-a645-40a5-ba92-ae31d0f5605d" />

```
df.isnull().any()
```
# Output
<img width="206" height="428" alt="image" src="https://github.com/user-attachments/assets/b9279e35-5b10-4713-a884-1f0dbdcf609d" />

```
df.dropna()
```
# Output
<img width="862" height="425" alt="image" src="https://github.com/user-attachments/assets/c3784f9f-718f-45ca-b59d-9f3df7ccfd29" />

```
df.fillna(5)
```
# Output
<img width="836" height="663" alt="image" src="https://github.com/user-attachments/assets/f84f1328-5eb8-4c32-8119-d133b8a7e2b6" />

```
df.fillna(method = 'ffill')
```
# Output
<img width="1323" height="691" alt="image" src="https://github.com/user-attachments/assets/6678ea6b-791c-4f65-9f40-b19df05d873d" />

```
df.fillna(method = 'bfill')
```
# Output
<img width="1330" height="694" alt="image" src="https://github.com/user-attachments/assets/cc10b4bf-48e4-499d-b473-570f9239f3b7" />

```
df.fillna({'GENDER': 'MALE','NAME':'RAM','TOTAL':602.5,'AVG':108.057777})
```
# Output
<img width="926" height="658" alt="image" src="https://github.com/user-attachments/assets/311a9ec0-d7ee-496f-913d-19cd16e7cbf8" />

```
ir = pd.read_csv('iris.csv')
ir
```
# Output
<img width="718" height="491" alt="image" src="https://github.com/user-attachments/assets/433dd764-a4ae-4e10-8f94-17ba3a2c45ce" />

```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```
# Output
<img width="611" height="438" alt="image" src="https://github.com/user-attachments/assets/669ea6c2-364c-449b-b37e-d3070233702e" />

```
q1=ir.sepal_width.quantile(0.25)
q3=ir.sepal_width.quantile(0.75)
iqr=q3-q1
print(iqr)
```
# Output
<img width="463" height="27" alt="image" src="https://github.com/user-attachments/assets/e9249fc0-5a4e-4181-8d5c-b5f861c6e997" />

```
rid = ir[((ir.sepal_width<(q1-1.5*iqr)) |(ir.sepal_width>(q3+1.5*iqr)))]
rid['sepal_width']
```
# Output
<img width="392" height="199" alt="image" src="https://github.com/user-attachments/assets/b3cac905-913f-42d2-9709-8f9f697e6cc0" />

```
delid = ir[~((ir.sepal_width<(q1-1.5*iqr)) |(ir.sepal_width>(q3+1.5*iqr)))]
delid
```
# Output
<img width="692" height="437" alt="image" src="https://github.com/user-attachments/assets/afb30f74-07a2-4fd7-819a-0005226e0943" />

```
sns.boxplot(x='sepal_width',data=delid)
```
# Output
<img width="671" height="430" alt="image" src="https://github.com/user-attachments/assets/fb94e1a8-aa45-4005-b13b-7c0d2fee442a" />

```
import numpy as np
import scipy.stats as stats
```

```
z = np.abs(stats.zscore(ir['sepal_width']))
z
```
# Output
<img width="559" height="563" alt="image" src="https://github.com/user-attachments/assets/8c1ff242-8740-4325-bf9e-33624b26aca2" />

# Result
Thus, we have read the given data and performed data cleaning and saved the cleaned data to a file successfully.
