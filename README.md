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

## CODING AND OUTPUT:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```

# Output

![image](https://github.com/user-attachments/assets/6da9711d-7202-4470-8da9-4d8bf669e55e)


```
df.info()
```

# Output

![image](https://github.com/user-attachments/assets/2d8eba47-a095-4302-9eb5-ca0e6f622704)

```
df.shape
```


# Output

![image](https://github.com/user-attachments/assets/8be27ebd-4fcc-42b5-83d1-cff9279cbcba)


```
df.set_index("PassengerId",inplace=True)
df.describe()
```

# Output

![image](https://github.com/user-attachments/assets/18dba159-c681-4a5f-a228-8a9f388b8846)

```
df.nunique()
```

# Output

![image](https://github.com/user-attachments/assets/d77575e2-ccf0-4afb-a400-812abf961889)



```
df["Survived"].value_counts()
```

# Output

![image](https://github.com/user-attachments/assets/fc13628b-eac5-465f-bfa8-e5ddd1cdf8fa)


```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```

# Output

![image](https://github.com/user-attachments/assets/0d1202a5-9456-4083-b40a-4c18c0c5070e)


```
sns.countplot(data=df,x="Survived")
```

# Output

![image](https://github.com/user-attachments/assets/116b4fb1-cae9-4cb6-9e5a-1521c8afdb58)



```
df
```

# Output

![image](https://github.com/user-attachments/assets/91047700-a5ca-46af-bacf-01f12be84b5c)


```
df.Pclass.unique()
```

# Output

![image](https://github.com/user-attachments/assets/62bbd625-bca5-48c4-b77b-b9798ed413d2)


```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

# Output

![image](https://github.com/user-attachments/assets/5b39c81c-3987-4e92-b8ac-6024404e0f20)


```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```

# Output

![image](https://github.com/user-attachments/assets/4b9792df-8127-406a-a8d2-e5e6262b243b)


```
sns.catplot(x='Survived',hue="Gender",data=df,kind='count')
```

# Output

![image](https://github.com/user-attachments/assets/05c6fdbc-31d4-450f-a679-bf0b491c7c2d)

```
df.boxplot(column="Age",by="Survived")
```

# Output

![image](https://github.com/user-attachments/assets/4f664727-e315-4703-919c-7165c612c731)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

# Output

![image](https://github.com/user-attachments/assets/723a5ea8-925c-401a-8ab9-bf5e19479e4d)


```
sns.jointplot(x="Age",y="Fare",data=df)
```

# Output

![image](https://github.com/user-attachments/assets/a5292643-7e43-41dd-86b4-d381ca244cd2)


```
fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=df)
```

# Output

![image](https://github.com/user-attachments/assets/27e15150-d328-4bb7-9d67-846ff4c97438)




```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

# Output


![image](https://github.com/user-attachments/assets/be060a64-cf2d-42a7-a112-07973fcf78bb)



```
corr=df.corr()
sns.heatmap(corr,annot=True)
```

# Output





```
sns.pairplot(df)
```

# Output


![image](https://github.com/user-attachments/assets/04076fd1-215c-4210-88b5-975139c50e71)




# RESULT
Thus, the Exploratory Data Analysis on the given data set was performed successfully.
