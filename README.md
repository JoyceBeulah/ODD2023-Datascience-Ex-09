# Ex-09-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.

# CODE AND OUPUT
NAME : R . JOYCE BEULAH
REG NO : 212222230058

```
import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt
df=sns.load_dataset("tips")
print(df)
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex-09/assets/118343698/170e0909-682b-4bb2-83d7-3dd8bfaca844)

```
df.isnull().sum()
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex-09/assets/118343698/a7487184-fc21-44e9-a46d-5703be157d48)

```
plt.figure(figsize=(5,5))
plt.title("data with outliners")
df.boxplot()
plt.show()
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex-09/assets/118343698/83aa9b9e-d2a3-48b8-ad9f-cf6ea68c0980)

```
plt.figure(figsize=(5,5))
cols=["size","tip","total_bill"]
q1=df[cols].quantile(0.25)
q3=df[cols].quantile(0.75)
iqr=q3-q1
df=df[~((df[cols]<(q1-1.5*iqr))|(df[cols]>(q3+1.5*iqr))).any(axis=1)]
plt.title("dataset after removing outliners")
df.boxplot()
plt.show()
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex-09/assets/118343698/77059e78-86af-4676-8858-bd3e35d40b70)

```
sns.barplot(x=df["day"],y=df["total_bill"],hue=df["day"])
plt.legend(loc="center")
plt.title("highest total bill amount by day of the week")
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex-09/assets/118343698/7169fa37-2708-4267-9075-712dba33b362)

```
sns.boxplot(x=df["smoker"],y=df["tip"],hue=df["smoker"])
plt.title("average tip amount given by smokers and non-smokers")
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex-09/assets/118343698/9028df5c-6777-48f4-9d1a-38cd8073a13a)

```
df["tip_percent"]=df["tip"] / df["total_bill"]
sns.scatterplot(x=df['size'], y=df['tip_percent'],data=df)
plt.title("Tip Percentage by Dining Party Size")
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex-09/assets/118343698/7cf1bb34-4d7f-42c4-aae6-fc5f61c0ba89)

```
sns.boxplot(x=df["sex"],y=df["tip"],hue=df["sex"])
plt.title("tips based on gender")
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex-09/assets/118343698/896409b5-a267-4403-ad4f-8657457dc72f)

```
sns.scatterplot(x=df["day"],y=df["total_bill"],hue=df["day"])
plt.legend(loc="best")
plt.title("total bill amount by day of te week")
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex-09/assets/118343698/d5053a21-30c6-4d3d-9f1a-b0a74c2682e7)

```
sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")
plt.title("Distribution of Total Bill Amounts by Time of Day")
plt.show()
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex-09/assets/118343698/2c3fd62b-fe20-4418-ae07-fe633bf0cc8c)

```
sns.barplot(x=df["size"],y=df["total_bill"],hue=df["size"])
plt.title("average total bill amount by dinning party size")
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex-09/assets/118343698/d261b5ea-2e2a-4c19-950d-084a227c2693)

```
sns.boxplot(x="day", y="tip", data=df)
plt.title("Tip Amount by Day of Week")
plt.show()
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex-09/assets/118343698/ac4a74fa-8afb-4e22-928e-bf7595b09db8)

```
sns.violinplot(x="time",y="tip",data=df)
plt.title("tip amount time of day")
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex-09/assets/118343698/8bb1550e-6340-4a54-ac9b-be4288faba82)

```
sns.scatterplot(x="total_bill",y="tip",data=df)
plt.title("Correlation between Tip Amount and Total Bill Amount")
plt.show()
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex-09/assets/118343698/4af37545-7adc-44c4-9d80-901151b78879)

# RESULT:
Thus, Data Visualization on a complex dataset and save the data to a file has been performed successfully.
