# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
```
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
sns.lineplot(x=x,y=y)
```
![Screenshot 2024-10-22 105159](https://github.com/user-attachments/assets/5e3850e5-2929-4919-a98e-7e6e9f49c6b4)

```
df = sns.load_dataset("tips")
df
```
![Screenshot 2024-10-22 105253](https://github.com/user-attachments/assets/228af7be-9660-4e25-bd83-45abb56c7cc3)

```
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
```
![Screenshot 2024-10-22 105349](https://github.com/user-attachments/assets/114af95e-8b25-42bb-bee1-36ab28e0fe63)

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
![Screenshot 2024-10-22 105450](https://github.com/user-attachments/assets/b2157f1e-97ca-4281-a4f7-6ff64d78b8bb)

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
![Screenshot 2024-10-22 105716](https://github.com/user-attachments/assets/b525d94c-0c43-405e-9acd-ff48bb830fcf)

```
avg_total_bill = tips.groupby('time')['total_bill'].mean() 
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```
![Screenshot 2024-10-22 110157](https://github.com/user-attachments/assets/e5ab1a93-9fd5-4894-91f7-a3b37fa2a797)

```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939] 
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```
![Screenshot 2024-10-22 110414](https://github.com/user-attachments/assets/93d3268c-804b-4a13-800f-de954fc16262)

```
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```
![Screenshot 2024-10-22 110516](https://github.com/user-attachments/assets/a26deb65-eafa-4727-806d-96b1dcd6ebbc)

```
tit=pd.read_csv("titanic_dataset.csv")
tit
```
![Screenshot 2024-10-22 110653](https://github.com/user-attachments/assets/8da1a4e5-b5f5-453d-94f6-aa3dd7bf2dab)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow') 
plt.title("Fare of Passenger by Embarked Town")
```
![Screenshot 2024-10-22 110730](https://github.com/user-attachments/assets/4b7faeb6-4bdf-480c-8cd4-2f3dbc1cde66)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass') 
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```
![Screenshot 2024-10-22 110839](https://github.com/user-attachments/assets/0060be31-6942-4d2e-bf9c-e973963688c2)

```
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
![Screenshot 2024-10-22 110918](https://github.com/user-attachments/assets/6bd8a4c2-801f-4c25-bb57-f687d58c6c2c)

```
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```
![Screenshot 2024-10-22 110949](https://github.com/user-attachments/assets/db156afe-ff62-42ae-b030-a04b83c327f8)

```
sns.histplot(data = num_var, kde = True)
```
![Screenshot 2024-10-22 111017](https://github.com/user-attachments/assets/29604c70-4cf3-43b8-b59d-cbfba626e730)

```
df=pd.read_csv("titanic_dataset.csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```
![Screenshot 2024-10-22 111112](https://github.com/user-attachments/assets/f9b8ffc4-7a23-4a99-9be0-6d71b208f079)

```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```
![Screenshot 2024-10-22 111224](https://github.com/user-attachments/assets/a8197864-3171-4dd6-a7dc-b4bf4a01b3ef)

```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```
![Screenshot 2024-10-26 225012](https://github.com/user-attachments/assets/2108fe27-773d-4462-8bfe-c7beb1480f24)

```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![Screenshot 2024-10-26 225101](https://github.com/user-attachments/assets/473bb020-5683-4b70-a37f-08cced58c6b6)

```
import seaborn as sns
sns.set(style = 'whitegrid')
tip = sns.load_dataset('tips') 
tips = sns.load_dataset("tips")
sns.violinplot(x="tip", y="day", data=tip)
```
![Screenshot 2024-10-26 225524](https://github.com/user-attachments/assets/7edd4779-f3ac-4316-88b1-eaf351738186)

```
mart=pd.read_csv("titanic_dataset.csv")
mart
```
![Screenshot 2024-10-26 225607](https://github.com/user-attachments/assets/839d4a31-8d9e-4654-b9ad-67cf667ece64)

```
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']] 
mart.head(10)
```
![Screenshot 2024-10-26 225637](https://github.com/user-attachments/assets/dd083a1c-994f-48d8-a920-c52410dcd632)

```
sns.kdeplot(data=mart,x='Age')
```
![Screenshot 2024-10-26 225727](https://github.com/user-attachments/assets/8903e364-c169-4058-b60e-2138f3d95872)

```
sns.kdeplot(data=mart,x='PassengerId')
```
![Screenshot 2024-10-26 225752](https://github.com/user-attachments/assets/1b703a7b-7275-49d3-a269-a9447dc4a46b)

```
sns.kdeplot(data=mart)
```
![Screenshot 2024-10-26 225823](https://github.com/user-attachments/assets/89b5bb5b-294f-410f-b922-93ed089c5048)

```
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
```
![Screenshot 2024-10-26 225935](https://github.com/user-attachments/assets/7ab0ca8a-9593-48c2-b2c9-7aa37800489d)

```
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
```
![Screenshot 2024-10-26 230008](https://github.com/user-attachments/assets/ff9f542b-cba5-4c9b-bfd5-14847f3fc33d)

```
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
```
![Screenshot 2024-10-26 230043](https://github.com/user-attachments/assets/7d359c50-696c-445e-b0e6-af81985493f2)

```
hm=sns.heatmap(data=data)
```
![Screenshot 2024-10-26 230109](https://github.com/user-attachments/assets/9a5e922d-1133-4c70-8028-8abba02a5489)


# Result:
Thus, all the data visualization techniques of seaborn has been implemented.
