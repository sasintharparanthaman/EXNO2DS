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
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```
![Screenshot 2024-03-15 104052](https://github.com/sasintharparanthaman/EXNO2DS/assets/145743219/28823390-eb01-4e65-828c-39e79f38b5c7)


```
dt.info()
```
![Screenshot 2024-03-15 104210](https://github.com/sasintharparanthaman/EXNO2DS/assets/145743219/6879e4ec-02ce-4659-b422-b39b463b63da)


```
dt.shape
```
![Screenshot 2024-03-15 104222](https://github.com/sasintharparanthaman/EXNO2DS/assets/145743219/a909d8d4-e73d-435b-94ba-13191a7da8a9)

```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```
![Screenshot 2024-03-15 104237](https://github.com/sasintharparanthaman/EXNO2DS/assets/145743219/87777799-e78b-4adc-a84a-e3379a7eb63b)


```
dt.nunique()
```
![Screenshot 2024-03-15 104248](https://github.com/sasintharparanthaman/EXNO2DS/assets/145743219/c21acd5c-0e91-43f3-9845-0afb837bd751)


```
dt["Survived"].value_counts()
```
![Screenshot 2024-03-15 104256](https://github.com/sasintharparanthaman/EXNO2DS/assets/145743219/520e4849-300d-47aa-8bd6-7b929ea13027)


```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![Screenshot 2024-03-15 104303](https://github.com/sasintharparanthaman/EXNO2DS/assets/145743219/e4ba7b52-2eac-46ec-a2a5-aa667956bf21)

```
sns.countplot(data=dt,x="Survived")
```
![Screenshot 2024-03-15 104313](https://github.com/sasintharparanthaman/EXNO2DS/assets/145743219/1197b90f-f05c-4bd6-bffc-7d6349ae3468)

```
dt
```

![Screenshot 2024-03-15 104332](https://github.com/sasintharparanthaman/EXNO2DS/assets/145743219/a95a0a3e-be77-4f05-9a3e-536a6b32b186)

```
dt.Pclass.unique()
```
![Screenshot 2024-03-15 104342](https://github.com/sasintharparanthaman/EXNO2DS/assets/145743219/18101374-f99e-453d-b404-2b9d2d0a2500)

```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![Screenshot 2024-03-15 104357](https://github.com/sasintharparanthaman/EXNO2DS/assets/145743219/f58dc5e8-9d92-4e04-8821-6f1bdaa9d959)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![Screenshot 2024-03-15 104419](https://github.com/sasintharparanthaman/EXNO2DS/assets/145743219/55b3cfae-3aff-40f3-82f4-ac85ff83b32b)


```
sns.catplot(x='Survived',hue="Gender",data=dt,kind='count')
```

![Screenshot 2024-03-15 104437](https://github.com/sasintharparanthaman/EXNO2DS/assets/145743219/f69a6545-29bf-44c2-a033-f45d85a43d3f)


```
dt.boxplot(column="Age",by="Survived")
```
![Screenshot 2024-03-15 104450](https://github.com/sasintharparanthaman/EXNO2DS/assets/145743219/feb6d8e2-ccc5-4e71-a202-8096db349c38)


```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![Screenshot 2024-03-15 104506](https://github.com/sasintharparanthaman/EXNO2DS/assets/145743219/33727315-39ed-40d7-9dff-03a89c5c5502)

```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![Screenshot 2024-03-15 104521](https://github.com/sasintharparanthaman/EXNO2DS/assets/145743219/20f6e119-873b-4f8e-8f9f-a0da40219725)


```
fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=dt)
```

![Screenshot 2024-03-15 104534](https://github.com/sasintharparanthaman/EXNO2DS/assets/145743219/46d1f151-fcf3-473e-b761-4e750aaa6957)

```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![Screenshot 2024-03-15 104547](https://github.com/sasintharparanthaman/EXNO2DS/assets/145743219/b80e933d-2cb2-4cf7-8136-7e5b610ab1e7)


```
corr=dt.corr()
sns.heatmap(corr,annot=True)
```

![Screenshot 2024-03-15 104613](https://github.com/sasintharparanthaman/EXNO2DS/assets/145743219/2e1c8214-5413-40e8-8e37-df206f0738c7)


```
sns.pairplot(dt)
```
![Screenshot 2024-03-15 104745](https://github.com/sasintharparanthaman/EXNO2DS/assets/145743219/1f3884d9-ebd3-4af9-9448-2b8cc68bfacd)

# RESULT
Thus, the Exploratory Data Analysis on the given data set was performed successfully. 

