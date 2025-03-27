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
DEVELOPED BY : LUKESH M
DATE : 27-03-25

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
lk = pd.read_csv('/content/titanic_dataset.csv')
lk
```
# output:
![DS EX2 S1](https://github.com/user-attachments/assets/221a3026-3a77-4e32-aabf-e167e967a70a)

```
lk.info()
```
# output:
![EX2 2](https://github.com/user-attachments/assets/fd540276-dae5-496e-b444-6df183c429f8)

```
lk.shape
```
# output:
![EX2 3](https://github.com/user-attachments/assets/9867c5f1-2211-4617-bced-571f4e525ee5)

```
lk.set_index('PassengerId', inplace=True)
lk.describe()
```
# output:
![EX2 4](https://github.com/user-attachments/assets/a2cc1f45-8c8a-450e-9f32-ea4f762f54fd)

```
lk.shape
```
# output:
![EX2 5](https://github.com/user-attachments/assets/6d67c9a4-ad40-4399-9b82-1f9a2a544229)
```

lk.nunique()
```
# output:
![EX2 6](https://github.com/user-attachments/assets/744b3514-3adb-4244-b09a-5ecde048312f)

```
lk["Survived"].value_counts()
```
# output:
![EX2 7](https://github.com/user-attachments/assets/32eb9230-3ea6-437b-9ce7-671099416387)

```
per=(lk["Survived"].value_counts()/lk.shape[0]*100).round(2)
per
```
# output:
![EX2 8](https://github.com/user-attachments/assets/5ec8ece6-9e11-4459-8a4c-c0cc8da09be1)

```
sns.countplot(data=lk,x="Survived")
```
# output:
![EX2 9](https://github.com/user-attachments/assets/3ea884cd-4336-4074-84c0-b13043f989b6)

```
lk
```
# output:
![EX2 10](https://github.com/user-attachments/assets/84e43a9f-7c31-4f4e-900d-f574f09ad704)

```
lk.Pclass.unique()
```
# output:
![EX2 11](https://github.com/user-attachments/assets/aac25dd0-14fa-4680-bc5a-50aa7c7682bd)

```
lk.rename(columns={'Sex':'Gender'},inplace=True)
lk
```
# output:
![EX2 12](https://github.com/user-attachments/assets/77d4a8f7-964f-4df7-8cb2-966e93b85927)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=lk,height=5,aspect=.7)
```
# output:
![EX2 13](https://github.com/user-attachments/assets/1f956877-0873-4a4c-96b7-35a73a1cad61)

```
sns.catplot(x="Survived",hue="Gender",data=lk,kind="count")
```
# output:
![EX2 14](https://github.com/user-attachments/assets/1ae90f7a-08f3-461d-a714-68fd71ce3075)

```
lk.boxplot(column="Age",by="Survived")
```
# output:
![EX2 15](https://github.com/user-attachments/assets/9ae2ead3-1135-4775-94d8-77e10ad5ca27)

```
sns.scatterplot(x=lk['Age'],y=lk["Fare"])
```
# output:
![EX2 16](https://github.com/user-attachments/assets/dd3894bd-8066-40eb-a08a-cb0470b8aa8c)

```
sns.scatterplot(x=lk['Age'],y=lk["Fare"])
```
# output:
![EX2 17](https://github.com/user-attachments/assets/0587b21b-b99e-409c-83b5-13c2026e92a7)
```

fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=lk)
```
# output:
![EX2 18](https://github.com/user-attachments/assets/3961e91b-3b9b-4301-b562-4da6a44d54fb)

```
sns.catplot(data=lk,col="Survived",x="Gender",hue="Pclass",kind="count")
```
# output:
![EX2 19](https://github.com/user-attachments/assets/206dc38b-03af-43e1-b6d6-f57d07993b97)

```
numerical_features = lk.select_dtypes(include=np.number).columns
corr = lk[numerical_features].corr()
sns.heatmap(corr, annot=True)
```
# output:
![EX2 20 1](https://github.com/user-attachments/assets/f5414f86-0e44-4c9a-80c8-2eb700bb5ea8)

```
sns.pairplot(lk)
```
# output:

![EX2 20 2](https://github.com/user-attachments/assets/52e086e3-289e-41f4-8a60-bb2849adcbb3)


# RESULT
        <<INCLUDE YOUR RESULT HERE>>
