# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

## Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

## EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

## Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

## Coding and Output:
```
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
sns.lineplot(x=x,y=y)
```
![image](https://github.com/user-attachments/assets/2281c885-746c-40ed-8dcd-a1ab2fdc60c8)

```
df = sns.load_dataset("tips")
df
```
![image](https://github.com/user-attachments/assets/7576ad2e-7490-42b7-853e-0f26efd532f3)

```
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
```
![image](https://github.com/user-attachments/assets/f55cb9df-ce8e-48d4-a273-6286dec644c5)

```
x=[1, 2, 3, 4, 5]
y1=[3, 5, 2, 6, 1]
y2=[1, 6, 4, 3, 8]
y3=[5, 2, 7, 1, 4]
sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel("Y Label")
```
![image](https://github.com/user-attachments/assets/2422e791-ad33-4677-9315-b4ebd5d5c391)

```
tips=sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![image](https://github.com/user-attachments/assets/127a9e8e-d2d5-4c08-a71f-997e94be34b9)

```
avg_total_bill = tips.groupby('time')['total_bill'].mean() 
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```
![image](https://github.com/user-attachments/assets/8955d2fd-2cb0-4fbf-a9b7-b08cd3fa93ff)

```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939] 
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
```
```
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```
![image](https://github.com/user-attachments/assets/8dd70b90-7898-4af6-b551-55815799882e)

```
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```
![image](https://github.com/user-attachments/assets/38986a39-84b2-4a62-abe8-e69c2fd302af)

```
tit=pd.read_csv("titanic_dataset.csv")
tit
```
![image](https://github.com/user-attachments/assets/5812cfa4-3654-4a2d-b36c-87d4e6eef78f)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow') 
plt.title("Fare of Passenger by Embarked Town")
```
![image](https://github.com/user-attachments/assets/852409ea-5482-4c4a-b4b0-8aed53b89509)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass') 
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```
![image](https://github.com/user-attachments/assets/bf3554f7-0fe5-4860-b024-edbaf4cef306)

```
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
![image](https://github.com/user-attachments/assets/9450f7d8-2ab5-41c6-8446-368264630cb0)

```
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```
![image](https://github.com/user-attachments/assets/e1f37c21-d0c1-479e-bcad-6a3557fd7324)

```
sns.histplot(data = num_var, kde = True)
```
![image](https://github.com/user-attachments/assets/9deb5f2d-c101-43bc-b369-fccfa0cbf9a3)

```
df=pd.read_csv("titanic_dataset.csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```
![image](https://github.com/user-attachments/assets/40f44889-fa22-4166-bdfd-15f73af2928a)

```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```
![image](https://github.com/user-attachments/assets/d5b61feb-f054-440f-ae66-69af079d549d)

```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```
![image](https://github.com/user-attachments/assets/50f9d7a9-4c1b-44cd-a625-f3eeff0c2ec0)

```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![image](https://github.com/user-attachments/assets/eda44dac-4bfc-461f-8c72-e768554e3663)

```
mart=pd.read_csv("titanic_dataset.csv")
mart
```
![image](https://github.com/user-attachments/assets/1fafe0a7-4c02-46c2-8818-592af035c619)

```
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']] 
mart.head(10)
```
![image](https://github.com/user-attachments/assets/e5003aeb-11e2-4103-9ea6-6061d0416a82)

```
sns.kdeplot(data=mart,x='PassengerId')
```
![image](https://github.com/user-attachments/assets/5c27a9fa-e313-4e8f-93fe-8e1eb7188c4e)

```
sns.kdeplot(data=mart,x='Age')
```
![image](https://github.com/user-attachments/assets/c341ccd6-92cf-4777-88ba-1b0b80c5389e)

```
sns.kdeplot(data=mart)
```
![image](https://github.com/user-attachments/assets/41702d92-8f83-4f5c-8c8f-fd636ebcc39b)

```
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
```
![image](https://github.com/user-attachments/assets/4f164684-f2a7-4960-94b1-b1b7791e9239)

```
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
```
![image](https://github.com/user-attachments/assets/30614874-a179-48b8-81a9-40b651bfc4f6)


```
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
```
![image](https://github.com/user-attachments/assets/2ce83720-a373-4f50-9860-d323aa3c399f)

```
hm=sns.heatmap(data=data)
```
![image](https://github.com/user-attachments/assets/24f59c21-29ba-4e0e-8e24-383c7d0f8bb2)

## Result:

Thus, all the data visualization techniques of seaborn has been implemented.
