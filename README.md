# NAME:Punniyakotti.M
# REGISTER NO: 212224240122
# EXNO:2
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
df = pd.read_csv("Titanic-Dataset.csv")
df
```

<img width="1223" height="403" alt="image" src="https://github.com/user-attachments/assets/9c953613-c8c4-4d37-9d2f-6586d3e1154b" />

```
df.info()
```
<img width="622" height="378" alt="image" src="https://github.com/user-attachments/assets/b8c04d16-d6c6-4305-85d8-3c1ba9252ba5" />

```
df.shape
```
<img width="586" height="98" alt="image" src="https://github.com/user-attachments/assets/4b599961-8706-455d-ba43-60f93d075e77" />

```
df.set_index("PassengerId",inplace=True)
df.nunique()
```
<img width="393" height="252" alt="image" src="https://github.com/user-attachments/assets/7913a28b-04da-417d-8d50-4e4a1d0ad31a" />

```
df["Survived"].value_counts()
```
<img width="434" height="89" alt="image" src="https://github.com/user-attachments/assets/660e9d38-07f7-4d4b-9543-8fd59c79e893" />
```
per = (df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
<img width="571" height="80" alt="image" src="https://github.com/user-attachments/assets/4c3e1d31-05bc-4181-85ef-d620f2f89be9" />

```
df.describe()
```
<img width="766" height="275" alt="image" src="https://github.com/user-attachments/assets/b73fd6e1-7dc5-4110-96c2-0006b68e9a53" />

```
sns.countplot(data=df,x="Survived")
```
<img width="1004" height="535" alt="image" src="https://github.com/user-attachments/assets/42a287bc-f693-4702-8c40-4eb2b7d52138" />

```
df.Pclass.unique()
```
<img width="503" height="41" alt="image" src="https://github.com/user-attachments/assets/724cfcf0-aea7-4ccd-8a05-a1844cb0be98" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="1231" height="450" alt="image" src="https://github.com/user-attachments/assets/2f2d31b9-104a-45fa-829f-30fc455d0ee6" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
<img width="1027" height="595" alt="image" src="https://github.com/user-attachments/assets/97fc7a58-8b2d-40ff-99b6-9683697f8c89" />

```
sns.catplot(x='Survived',hue="Gender",data=df,kind="count")
```
<img width="1123" height="600" alt="image" src="https://github.com/user-attachments/assets/60085efb-fbcb-4036-bc58-a1b311bb2470" />
```
df.boxplot(column="Age",by="Survived")
```
<img width="775" height="568" alt="image" src="https://github.com/user-attachments/assets/bc7154e7-dbf4-4ded-9069-b5e8bb5f7513" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="857" height="543" alt="image" src="https://github.com/user-attachments/assets/0dbd3ac8-15d6-4cb0-b049-88aa5469b9c7" />

```
sns.jointplot(x="Age",y="Fare",data=df)
```
<img width="866" height="701" alt="image" src="https://github.com/user-attachments/assets/ef35eac0-14cb-43c8-a7c7-6f6f82a466af" />

```
fig,ax1 = plt.subplots(figsize=(8,5))
pt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="984" height="525" alt="image" src="https://github.com/user-attachments/assets/71987c29-dc50-4bbb-8599-5c39c79daf94" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
<img width="1217" height="551" alt="image" src="https://github.com/user-attachments/assets/c7af8933-3826-49e5-a494-4adeda6d31a8" />

```
sns.pairplot(df)
```
<img width="1231" height="810" alt="image" src="https://github.com/user-attachments/assets/165c9e81-6df3-4d39-9257-e83c8d313315" />
<img width="1311" height="638" alt="image" src="https://github.com/user-attachments/assets/48a9280e-f306-46e1-8f1a-b2eac005a98e" />





# RESULT
Thus the data analysis has been implemented succesfully.
