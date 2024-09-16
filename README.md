
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
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/2555e302-d9a2-4ad5-80ad-fa0bbab55e07)
```
df.isna().sum()
```
![image](https://github.com/user-attachments/assets/ba830c55-769d-4491-99fe-81a577be9d53)
```
df.dropna(inplace=True)
df
```
![image](https://github.com/user-attachments/assets/b5c1a2c5-404c-4f0b-93f1-720e4bfe38c7)
```
df.info()
```
![image](https://github.com/user-attachments/assets/74de49e7-8151-4dea-9fab-e8b63e89db8e)
```
df.shape
```

![image](https://github.com/user-attachments/assets/9e4a87d6-259e-45de-a49e-bc8e8bfb024c)
```
df.set_index("PassengerId",inplace=True)
```
```
df.describe()
```

![image](https://github.com/user-attachments/assets/af805b2a-a971-4ecf-86ec-62604089469a)
```
df.nunique()
```

![image](https://github.com/user-attachments/assets/d5cb88c2-db46-4750-8553-a3c91cc2d598)
```
df["Survived"].value_counts()
```

![image](https://github.com/user-attachments/assets/f33160b6-b8fc-43a4-9d88-2450b49797de)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```

![image](https://github.com/user-attachments/assets/bf6f3d88-3dc2-4192-82f2-191275cf0fb7)
```
import matplotlib.pyplot as plt
import seaborn as sns
```
```
sns.countplot(data=df,x="Survived")
```

![image](https://github.com/user-attachments/assets/f15d0bf2-5b76-44b9-b1aa-539c61f021dc)
```
df
```

![image](https://github.com/user-attachments/assets/1f9254de-e484-4932-b10c-d25d7fd741a1)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/f29737f2-f49a-4294-8c77-324ba8cb68ad)
```
df.rename(columns= {'Sex': 'Gender'},inplace=True)
```
```
sns.catplot(x="Gender",col="Survived",kind= "count",data=df,height=5,aspect=.7)
```

![image](https://github.com/user-attachments/assets/2d44e781-2c1d-4728-9508-2d3bc7dfeb39)
```
sns.catplot(x='Survived',hue="Gender",data=df,kind = "count")
```

![image](https://github.com/user-attachments/assets/c2ba78f5-03e0-43d9-ae9a-f37f61667cb2)
```
sns.catplot(data=df,col = "Survived",x="Gender",hue="Pclass",kind = "count")
```

![image](https://github.com/user-attachments/assets/fbed2e54-70d0-410c-9f7f-fb44c65d87f1)








     

# RESULT
        
This process helps in effective data cleaning, outlier detection, and exploratory data analysis (EDA).
