
## NAME: HARITHA SHREE 
## REG NO: 212222230046


# EX NO:2
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
```python
import pandas as pd     
import numpy as np     
import matplotlib.pyplot as plt     
import seaborn as sns       
df=pd.read_csv("titanic_dataset.csv")   
df
```
![image](https://github.com/user-attachments/assets/4e5902ed-1a7f-4152-b0bf-58547b6d859f)

df.info()    
![image](https://github.com/user-attachments/assets/b91ebc8e-ea21-47c8-bca5-ae6c18ae76ff)

df.shape     
![image](https://github.com/user-attachments/assets/f780cd52-9ca9-46c2-b335-6c2a0c71f48e)

df.set_index("PassengerId",inplace=True)     
df.describe()     
![image](https://github.com/user-attachments/assets/1e5a0c0a-777c-42b3-ba23-181b09dc8790)

df.shape     
![image](https://github.com/user-attachments/assets/60628c0d-1daf-4b9a-895c-3399caf413f1)

CATEGORICAL DATA ANALYSIS     

df.nunique()     
![image](https://github.com/user-attachments/assets/043f595d-99e5-4326-bde6-b166c21df129)

df["Survived"].value_counts()     
![image](https://github.com/user-attachments/assets/b24894f7-be94-42a3-8435-5cd834436f7a)

 per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)    
 per       
![image](https://github.com/user-attachments/assets/5c085b9f-accc-409e-baeb-a482bb63afbe)

 sns.countplot(data=df,x="Survived")     
 ![image](https://github.com/user-attachments/assets/d8947426-a581-441e-b9de-b76c2c39e4f8)

df      
![image](https://github.com/user-attachments/assets/f429896b-0c6c-45bd-ace8-d8c09aa4b19c)

df.Pclass.unique()     
![image](https://github.com/user-attachments/assets/20e526cc-2a5f-403a-bb92-64057e058425)

df.rename(columns={'Sex':'Gender'},inplace=True)     
 df      
![image](https://github.com/user-attachments/assets/589b0f46-4153-4357-a883-8d6884c95fe4)

BIVARIATE ANALYSIS         

sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)     
![image](https://github.com/user-attachments/assets/d15d5751-0b4e-439d-ab00-99bca2bc383e)

sns.catplot(x="Survived",hue="Gender",data=df,kind="count")      
![image](https://github.com/user-attachments/assets/9d661147-bf09-461d-88f6-91909bc8aafe)

 df.boxplot(column="Age",by="Survived")      
![image](https://github.com/user-attachments/assets/af7fbe33-a3b8-4b8e-b99c-0c1da1d3fe71)

 sns.scatterplot(x=df["Age"],y=df["Fare"])      
![image](https://github.com/user-attachments/assets/e8122354-b7bc-471d-9db8-b144221ceeb0)

 sns.jointplot(x="Age",y="Fare",data=df)      
![image](https://github.com/user-attachments/assets/addb1864-2c00-41b2-b9fd-d03f576c11c5)

MULTIVARIATE ANALYSIS      

 fig, ax1 = plt.subplots(figsize=(8,5))       
 plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)       
![image](https://github.com/user-attachments/assets/3eec1d4e-90c2-4f5a-8fdd-42f2e5fa0e1b)

 sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")       
![image](https://github.com/user-attachments/assets/65b6c4a6-f6b3-4a48-b20c-78180d59a6b9)

CO-RELATION     

 corr=df.corr()       
 sns.heatmap(corr,annot=True)      
![image](https://github.com/user-attachments/assets/6659ad9a-9cee-4e62-bdc9-cbb564b22dc9)

sns.pairplot(df)      
![image](https://github.com/user-attachments/assets/7d9e6a78-cb25-4461-832f-f6b9e6e02cd0)




# RESULT
       We have performed Exploratory Data Analysis on the given data set successfully
