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

# Coding and Output
```
import pandas as pd
data=pd.read_csv("SAMPLEIDS.csv")
print(data)
```
<img width="696" height="707" alt="Screenshot 2026-05-13 233216" src="https://github.com/user-attachments/assets/5f3bee7c-c040-4c59-85f3-adf74a7a9134" />
```
data.isnull()
```
<img width="753" height="681" alt="Screenshot 2026-05-13 233440" src="https://github.com/user-attachments/assets/5a0ae0a0-fdda-485a-adc7-5440c03bcd3a" />
```
data.notnull()
```
<img width="600" height="541" alt="Screenshot 2026-05-13 234118" src="https://github.com/user-attachments/assets/0b23a34e-644c-4c7f-a89b-9ffce4bf4089" />
```
data.dropna(axis=1)
```
<img width="217" height="542" alt="Screenshot 2026-05-13 234248" src="https://github.com/user-attachments/assets/8963ac50-a8aa-4303-a88c-4a3b1710035e" />
```
data.dropna(axis=0)
```
<img width="717" height="347" alt="Screenshot 2026-05-13 234503" src="https://github.com/user-attachments/assets/92d9ddbe-6030-4180-991c-d9ac5fa06dd2" />
```
data
```
<img width="712" height="547" alt="Screenshot 2026-05-13 234657" src="https://github.com/user-attachments/assets/44f8620c-a7b3-4f8c-93d6-537f8dcc62d6" />
```
data.fillna(method='ffill')
```
<img width="655" height="507" alt="Screenshot 2026-05-13 235129" src="https://github.com/user-attachments/assets/7173c536-eb01-4fb4-82db-da7e655d2ae4" />
```
data.fillna(method='bfill')
```
<img width="670" height="507" alt="Screenshot 2026-05-13 235603" src="https://github.com/user-attachments/assets/5cd2d107-bb03-48d7-a76e-527c6431b666" />
```
data.dropna(inplace=True)
data
```
<img width="957" height="507" alt="Screenshot 2026-05-14 002320" src="https://github.com/user-attachments/assets/b1255c13-d64d-4985-a6f4-f9ed95dcf51d" />
```
data['M4'].fillna(value=data['M4'].mode(),inplace=True)
```
<img width="1575" height="192" alt="Screenshot 2026-05-14 002541" src="https://github.com/user-attachments/assets/e0d01f5b-6583-4ff3-807b-ea0349f1bef7" />
```
data
```
<img width="902" height="715" alt="Screenshot 2026-05-14 002621" src="https://github.com/user-attachments/assets/41b89a05-fbdb-4044-8159-27c2e32a3664" />
# IQR METHOD :
```
import pandas as pd
ir=pd.read_csv("iris.csv")
ir
```
<img width="777" height="591" alt="Screenshot 2026-05-14 002910" src="https://github.com/user-attachments/assets/c5f85233-efe9-4c15-aca5-63675d8f96ba" />
```
ir.describe()
```
<img width="645" height="383" alt="Screenshot 2026-05-14 003047" src="https://github.com/user-attachments/assets/94f3435d-aad3-48e3-ae95-888afe780f08" />
```
ir.shape
(150, 5)
ir.info()
```
<img width="600" height="347" alt="Screenshot 2026-05-14 003229" src="https://github.com/user-attachments/assets/2ba6536b-b3de-4438-a1d7-756eae1071d6" />
```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```
<img width="958" height="790" alt="Screenshot 2026-05-14 003428" src="https://github.com/user-attachments/assets/65ea8620-fa4b-4f0d-b2d9-2e30e9137dc7" />
# Z-SCORE METHOD :
```
import numpy as np
import pandas as pd
df=pd.read_csv("heights.csv")
df
```
<img width="251" height="663" alt="Screenshot 2026-05-14 003601" src="https://github.com/user-attachments/assets/49d485fb-3e7e-4ed6-a086-8f281794c7cd" />
```
df1 = df[((df['height'] >=low)& (df['height'] <=high))]
df1
```
<img width="272" height="581" alt="Screenshot 2026-05-14 003705" src="https://github.com/user-attachments/assets/f77ed0af-df98-4f8e-9389-88f14cab0c6c" />
```
z = np.abs(stats.zscore(df['height']))
z
```
<img width="387" height="437" alt="Screenshot 2026-05-14 003756" src="https://github.com/user-attachments/assets/345ce43c-bcee-4958-bcd6-dc056173d905" />
```
df1 = df[z<3]
df1
```
<img width="243" height="620" alt="Screenshot 2026-05-14 003827" src="https://github.com/user-attachments/assets/63f99ea0-3866-4d07-bcd5-aaed2794732a" />























# Result
```
            The given dataset was successfully read and cleaned using Python. Missing values and duplicate records were handled properly, and the cleaned data was saved into a new file named cleaned_data.csv and removed the outliers using IQR and Z-score method.
```

