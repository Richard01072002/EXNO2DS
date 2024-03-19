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
import numpy as py
import matplotlib as plt
import seaborn as sns

dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```
![image](https://github.com/Richard01072002/EXNO2DS/assets/141472248/ec032cc0-a793-46df-bbec-e0dd8f36ae90)

```
dt.info()
```
![image](https://github.com/Richard01072002/EXNO2DS/assets/141472248/24dff2f1-370d-4a43-b1e9-a38f1ecf0614)

```
dt.shape
```
![image](https://github.com/Richard01072002/EXNO2DS/assets/141472248/77e2051a-a971-4146-919e-278b7485752b)

```
dt.nunique()
```
![image](https://github.com/Richard01072002/EXNO2DS/assets/141472248/204250ea-21bd-43df-b1a6-7c33392680e1)

```
dt["Survived"].value_counts()
```
![image](https://github.com/Richard01072002/EXNO2DS/assets/141472248/7e44d033-9f00-43f1-ae63-e694b5f673d8)

```
pre=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
pre
```
![image](https://github.com/Richard01072002/EXNO2DS/assets/141472248/621480b3-013d-4a06-a538-205355b3b124)

```
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/Richard01072002/EXNO2DS/assets/141472248/ff6c7b45-c736-4e83-ab49-14a562b32db2)

```
dt
```
![image](https://github.com/Richard01072002/EXNO2DS/assets/141472248/1cdfaad8-c303-4c1b-adb4-2b761e4323b2)


```
dt.Pclass.unique()
```
![image](https://github.com/Richard01072002/EXNO2DS/assets/141472248/e8f4ab6a-e5cb-4c3e-974e-6111229f1ab3)


```
dt.rename(columns= {'Sex':'Gender'}, inplace=True)
dt
```
![image](https://github.com/Richard01072002/EXNO2DS/assets/141472248/8d28f80b-1ed3-4ef9-81e5-196422e0f02e)


```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![image](https://github.com/Richard01072002/EXNO2DS/assets/141472248/f55e4214-bc9e-4aa6-a07e-b079705a28ab)

```
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```
![image](https://github.com/Richard01072002/EXNO2DS/assets/141472248/2f2aca6d-6f37-4139-9a50-295a5f874dfe)


```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/Richard01072002/EXNO2DS/assets/141472248/bc16bc38-7fb1-4dd5-81d7-54a4d338199e)


```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/Richard01072002/EXNO2DS/assets/141472248/81ec68f2-05fe-4e2a-a6d4-f06a2ede7c0f)


```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![image](https://github.com/Richard01072002/EXNO2DS/assets/141472248/6ce37ca8-f8dc-4b85-b683-60295d339256)


```
sns.catplot(data=dt,col = "Survived",x = "Gender",hue="Pclass",kind = "count")
```
![image](https://github.com/Richard01072002/EXNO2DS/assets/141472248/657eaf9f-8115-4cae-a94e-d68974a03fbb)


```
corr = dt.corr()
sns.heatmap(corr,annot=True)
```
 ![image](https://github.com/Richard01072002/EXNO2DS/assets/141472248/3227fcce-2ff1-49d8-bd0b-91cd338fd020)


```
sns.pairplot(dt)
```
![image](https://github.com/Richard01072002/EXNO2DS/assets/141472248/f5ae69e1-991b-43ac-9844-8f8256faf9b8)



# RESULT
        <<INCLUDE YOUR RESULT HERE>>
