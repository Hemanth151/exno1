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
            <<include your coding and its corressponding output screen shots here>>
            import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
<img width="815" height="612" alt="image" src="https://github.com/user-attachments/assets/d1c0a3d4-a8be-41bb-a529-5c62d7683e29" />
print(df.head(7))
<img width="465" height="134" alt="image" src="https://github.com/user-attachments/assets/94376c1f-0d84-40eb-b222-fb53dffd5045" />
<img width="465" height="134" alt="image" src="https://github.com/user-attachments/assets/5cf8e0af-ca7a-4021-be52-33518f081718" />
print(df.tail(2))
<img width="478" height="69" alt="image" src="https://github.com/user-attachments/assets/8e32a79d-5c02-419d-bccc-b380ea2204fc" />
df.info()
<img width="155" height="155" alt="image" src="https://github.com/user-attachments/assets/986aa3ea-a028-4f78-88e1-ada707eefbf7" />
print(df.describe())
<img width="484" height="160" alt="image" src="https://github.com/user-attachments/assets/2cb8e627-44eb-41e3-a107-24ab33726913" />
df.isnull().sum()
<img width="76" height="112" alt="image" src="https://github.com/user-attachments/assets/93c358f2-3567-4fb0-aaeb-40a0622dc2d1" />
df.nunique()
<img width="65" height="109" alt="image" src="https://github.com/user-attachments/assets/7ea9eb5f-89ad-4bb3-8a5f-91832e076df3" />
mn=df.TOTAL.mean()
mn
<img width="104" height="39" alt="image" src="https://github.com/user-attachments/assets/f9dae159-939d-4dc5-8413-57a789d127f9" />
df.TOTAL.fillna(mn,inplace=True)
df
<img width="589" height="337" alt="image" src="https://github.com/user-attachments/assets/8985d800-07d3-4038-bf44-7d13ec5cf38f" />
min=df.M4.min()
min
<img width="91" height="46" alt="image" src="https://github.com/user-attachments/assets/9c0fa00d-1803-4b99-9f2f-629608afecab" />
df.M4.fillna(min,inplace=True)
df
<img width="373" height="308" alt="image" src="https://github.com/user-attachments/assets/bcc728d7-0916-48ab-a1f6-8410a7e5c4c9" />
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
<img width="89" height="223" alt="image" src="https://github.com/user-attachments/assets/b0859e5d-6a06-420f-a2a7-cbf9a5b37105" />
sns.boxplot(data=af)
<img width="284" height="201" alt="image" src="https://github.com/user-attachments/assets/a0f01471-d4ab-49f0-8e6b-c49b6876524f" />
sns.scatterplot(data=af)
<img width="249" height="201" alt="image" src="https://github.com/user-attachments/assets/df4a502d-98cd-47c7-a6c6-a2b91d8bbbdd" />
q1=af.quantile(0.25)
q2=af.quantile(0.50)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
low=q1-1.5*iqr
low
high=q3+1.5*iqr
high
<img width="95" height="116" alt="image" src="https://github.com/user-attachments/assets/c21866c9-35ba-46e4-9b1c-3f311a28479e" />
af=af[((af>=low)&(af<=high))]
af
<img width="103" height="217" alt="image" src="https://github.com/user-attachments/assets/03babce2-5b0c-4ccb-9580-36d90ba4abb7" />
af.dropna()
<img width="56" height="166" alt="image" src="https://github.com/user-attachments/assets/638e2710-ad4f-4be8-8eff-74614591b8f1" />
sns.boxplot(data=af)
<img width="281" height="194" alt="image" src="https://github.com/user-attachments/assets/bf6f1511-d9fc-4cd7-8c00-be21ecd48bc9" />
sns.scatterplot(data=af)
<img width="289" height="198" alt="image" src="https://github.com/user-attachments/assets/a1951ecc-1a06-4e68-8b09-87e6cc42b927" />
data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105]
df=pd.DataFrame(data)
df
<img width="61" height="273" alt="image" src="https://github.com/user-attachments/assets/2030c4d2-7d05-47b5-a7f3-16725228e552" />
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
<img width="86" height="378" alt="image" src="https://github.com/user-attachments/assets/67f99bee-6dd4-45a2-a686-20222c7de0d5" />



































 







# Result
          <<include your Result here>>
          Hence the data was cleaned , outliers were detected and removed.
 
