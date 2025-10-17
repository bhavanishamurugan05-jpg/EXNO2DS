# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
 import pandas as pd
 import numpy as np
 import matplotlib.pyplot as plt
 import seaborn as sns
 df=pd.read_csv("/content/titanic_dataset.csv")
 df
```
<img width="1129" height="383" alt="image" src="https://github.com/user-attachments/assets/0edf6f4c-0ad1-48b9-9579-6798e8634c68" />

```
df.info()
```
<img width="613" height="594" alt="image" src="https://github.com/user-attachments/assets/6381e8f2-6796-495c-9c05-a8bee444b604" />

```
df.describe()
```
<img width="707" height="263" alt="image" src="https://github.com/user-attachments/assets/7fcdef53-4283-41e0-8b37-fc641ae4052b" />

```
df.dtypes
```
<img width="178" height="423" alt="image" src="https://github.com/user-attachments/assets/d2034ab2-48da-47ae-844d-08cc1a1ee9d7" />

```
df.shape
```
<img width="83" height="30" alt="image" src="https://github.com/user-attachments/assets/7e8f95f8-9a2c-42e6-9bab-aa0d0b4127c9" />

```
df.value_counts()
```
<img width="1139" height="441" alt="image" src="https://github.com/user-attachments/assets/918e8e49-e0e1-4415-a550-3763820a01c4" />

```
df['Age'].value_counts()
```
<img width="129" height="456" alt="image" src="https://github.com/user-attachments/assets/a70226ea-e478-4791-9adb-2dbf49517ab2" />

```
df.set_index("PassengerId", inplace=True)
df
```
<img width="1080" height="418" alt="Screenshot 2025-09-23 214858" src="https://github.com/user-attachments/assets/5deee799-1260-4353-9213-f141b0083a01" />

```
df.nunique()
```
<img width="120" height="384" alt="Screenshot 2025-09-23 215513" src="https://github.com/user-attachments/assets/6ff651a7-586a-4c4c-b6e9-ed57be93c861" />

```
sns.countplot(data=df,x='Survived')
```
<img width="552" height="430" alt="image" src="https://github.com/user-attachments/assets/4bef14fe-990d-45d3-adcb-e4c994b13e6b" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="1081" height="424" alt="image" src="https://github.com/user-attachments/assets/5011b5cd-379a-485d-ae7e-7a6d08a3c31e" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
<img width="684" height="491" alt="image" src="https://github.com/user-attachments/assets/1fec390a-be2b-4eb7-ae2f-07c6cf14022b" />

```
df.boxplot(column="Age",by="Survived")
```
<img width="534" height="461" alt="image" src="https://github.com/user-attachments/assets/c95ccf10-9130-46e6-a4af-9351ef24659b" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="546" height="435" alt="image" src="https://github.com/user-attachments/assets/fc9d5a4d-0b7f-4bc8-ad19-6bdadee27ea8" />

```
fig, axl=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=axl,x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="653" height="432" alt="image" src="https://github.com/user-attachments/assets/5ae70f11-1a1a-44e2-88a1-9868fc629d72" />

```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="545" height="417" alt="Screenshot 2025-09-23 221039" src="https://github.com/user-attachments/assets/8b752a57-ccb1-444b-89e1-4c7a399aa077" />

```
import seaborn as sns
sns.catplot(x='Pclass',y="Age",hue="Gender",col="Survived",kind="box",data=df)
```
<img width="1039" height="492" alt="Screenshot 2025-09-23 222136" src="https://github.com/user-attachments/assets/b7abf534-c152-4cad-bec9-0e0ec229c628" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue='Pclass',kind="count")
```
<img width="994" height="489" alt="image" src="https://github.com/user-attachments/assets/692208ce-b284-4062-8f6b-913f0c20451e" />

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
<img width="505" height="422" alt="image" src="https://github.com/user-attachments/assets/8f538ab6-18e5-4415-a501-d428d46076ae" />

```
corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```
<img width="509" height="420" alt="image" src="https://github.com/user-attachments/assets/f6a5d88f-0b1e-4995-97a8-2e330d1c5a35" />

```
# RESULT
     Thus the programs are executed successfully.
   
