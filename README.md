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
Developed by: HEMA LOKITHA P
Register no: 212223110014
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns 
df=pd.read_csv("titanic_dataset.csv")
df
```
![Screenshot 2024-09-02 092833](https://github.com/user-attachments/assets/27609481-d45e-4f7b-95d7-0a707c629355)


```
df.info()
```
![Screenshot 2024-09-02 092846](https://github.com/user-attachments/assets/b359b19a-e161-4185-be2c-2ac8935a9ea8)

```
df.shape
```
![Screenshot 2024-09-02 092851](https://github.com/user-attachments/assets/5402e62a-c8ba-4a4e-9fe8-5de63b747bfe)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![Screenshot 2024-09-02 092859](https://github.com/user-attachments/assets/4eedc077-29af-4d73-83a9-0345fee70ca9)


```
df.shape
```
![Screenshot 2024-09-02 092904](https://github.com/user-attachments/assets/a61051f5-5a83-4c71-a616-0ac28c8bbb99)

Categorical data analysis

```
df.nunique()
```

![Screenshot 2024-09-02 092909](https://github.com/user-attachments/assets/8a3eec4e-ea71-47da-9159-2cdce9a214ce)


```
df["Survived"].value_counts()
```

![Screenshot 2024-09-02 092916](https://github.com/user-attachments/assets/0a8eab3a-67ca-443a-958d-c110d08c9369)


```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```

![Screenshot 2024-09-02 092922](https://github.com/user-attachments/assets/ca875d07-dcfc-4dbc-99e9-115cf1388f6d)


```
sns.countplot(data=df,x="Survived")
```
![Screenshot 2024-09-02 092930](https://github.com/user-attachments/assets/33105f05-f786-4088-a84f-c825011bec77)


```
df
```
![Screenshot 2024-09-02 092943](https://github.com/user-attachments/assets/0085d95c-f085-436d-a805-efe2676afb30)

```
df.Pclass.unique()
```

![Screenshot 2024-09-02 092949](https://github.com/user-attachments/assets/75bb4a81-62c5-450e-995c-41b187a31d54)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![Screenshot 2024-09-02 093004](https://github.com/user-attachments/assets/50c10860-2d0e-4fd7-b4c4-c7aac4cc7dac)

Bivariate Analysis
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![Screenshot 2024-09-02 093015](https://github.com/user-attachments/assets/7dc8caa2-bd8d-43fd-8423-d063abe76266)

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![Screenshot 2024-09-02 093025](https://github.com/user-attachments/assets/69ea5e76-4f77-4b6b-8316-959bb7576095)

```
df.boxplot(column="Age",by="Survived")
```
![Screenshot 2024-09-02 093033](https://github.com/user-attachments/assets/62539acd-bca4-4989-a156-ce6793bec473)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![Screenshot 2024-09-02 093040](https://github.com/user-attachments/assets/dc5275c2-3de2-444e-be8e-d9576a2aaaf7)

```
sns.jointplot(x="Age",y="Fare",data=df)
```
![Screenshot 2024-09-02 093049](https://github.com/user-attachments/assets/aa055a56-9f63-4878-868c-2ac3c595c851)

Multivariate Analysis
```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```

![Screenshot 2024-09-02 093100](https://github.com/user-attachments/assets/cf3fc757-563d-4420-b9a3-b74a7dab6397)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![Screenshot 2024-09-02 093111](https://github.com/user-attachments/assets/86dbdab9-8278-4c51-8ddb-743010d71cfa)


Co-relation
```
corr=df.corr()
sns.heatmap(corr,annot=True)
```

![Screenshot 2024-09-02 093117](https://github.com/user-attachments/assets/ffa383bf-0d72-4c8e-9384-3ebe8e520a6d)

```
sns.pairplot(df)
```

![Screenshot 2024-09-02 093138](https://github.com/user-attachments/assets/961d3f6a-64da-4b97-80ec-65de4a2ce176)


# RESULT

We have performed Exploratory Data Analysis on the given data set successfully.
