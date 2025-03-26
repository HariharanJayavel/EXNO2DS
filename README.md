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
df=pd.read_csv("titanic_dataset.csv")
df
 ```
![image](https://github.com/user-attachments/assets/88322923-de7c-4a5c-8cb9-b022b615123c)
```
df.info()
df.shape()
```
![image](https://github.com/user-attachments/assets/a4ce9684-b4c1-488f-a008-0a08d478a730)
![image](https://github.com/user-attachments/assets/b7b7831a-3c1f-439d-8089-9c2f75943ecd)


```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/7df6936e-d3b1-4b7e-b65d-9095cecbc5fe)
```
df
df.shape
```
![image](https://github.com/user-attachments/assets/feb6c0c7-078c-44b8-9e58-75f47f9fe3cd)
![image](https://github.com/user-attachments/assets/47d77ad3-05f9-4b9d-b66f-b84399ef96de)

```
df.nunique()
```
![image](https://github.com/user-attachments/assets/5c76fbdc-4346-402a-bd50-9e01b3425b6c)

```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/cfabb9b0-efe1-4a6a-ad5d-dad2a5ea2b91)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/dd2b9e94-4451-4439-95bb-4f77541fceb2)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/e86511db-44c9-4aad-96de-5cd92fe2f378)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/b26420f9-9bde-4440-89d1-d00e3fdfa5dd)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/a6588227-542f-4233-b585-e074b7fd3944)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/fad64c23-6bad-4ac8-b687-98031e87b495)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/52a9deb2-727b-4708-8dae-c16d80f8afc8)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/a4d31364-ae83-463e-8d2c-6733961011ff)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/bb8e558b-31ae-4f1b-b056-4bca88d7a063)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/31e3e461-84d1-4d79-a99b-7374d2ecde21)
```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/7c247b89-ed83-4358-97f7-a798a0236878)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/1a8a8706-0d7c-4811-8283-00a6511b5e63)
```
numeric_df = df.select_dtypes(include=['number'])
corr = numeric_df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/94c1e769-47fb-4ee9-9bcc-a22edc530b84)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/41583a2c-bf0a-4b16-a2f7-67240390bc7c)

# RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
