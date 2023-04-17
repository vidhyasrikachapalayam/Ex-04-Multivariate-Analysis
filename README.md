# Ex-04-Multivariate-Analysis

## AIM:
To perform Multivariate EDA on the given data set.

## EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM:

### STEP 1
Import the built libraries required to perform EDA and outlier removal.

### STEP 2
Read the given csv file.

### STEP 3
Convert the file into a dataframe and get information of the data.

### STEP 4
Return the objects containing counts of unique values using (value_counts()).

### STEP 5
Plot the counts in the form of Histogram or Bar Graph.

### STEP 6
Use seaborn the bar graph comparison of data can be viewed.

### STEP 7
Find the pairwise correlation of all columns in the dataframe.corr() .

### STEP 8
Save the final data set into the file.

## PROGRAM:

```
NAME:SUJITHRA B K N
REG NO:212222230153

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("SuperStore.csv")
data

data.head()

data.info()

data.describe()

data.dtypes

data.isnull().sum()

data['Postal Code']=data['Postal Code'].fillna(data['Postal Code'].mode()[0])
data.isnull().sum()

sns.scatterplot(x=data['Country'],y=data['Category'],data=data)

states=data.loc[:,["Region","Sales"]] 
states=states.groupby(by=["Region"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("REGION")
plt.ylabel=("SALES") 
plt.show()

states=data.loc[:,["State","Sales"]] 
states=states.groupby(by=["State"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("SALES") 
plt.ylabel=("STATES") 
plt.show()

states=data.loc[:,["Category","Sales"]] 
states=states.groupby(by=["Category"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(10,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("CATEGORY") 
plt.ylabel=("SALES") 
plt.show()

data.corr()

sns.heatmap(data.corr(),annot=True)
```

## OUTPUT:
![Screenshot 2023-04-17 173158](https://user-images.githubusercontent.com/119477857/232479986-9dd2ceaf-a45e-4c9f-9000-ad88acd105a4.png)

![Screenshot 2023-04-17 173225](https://user-images.githubusercontent.com/119477857/232479994-a4277597-87d9-4af0-a877-5ef84295f609.png)

![Screenshot 2023-04-17 173234](https://user-images.githubusercontent.com/119477857/232480012-01e6d682-698f-48ca-bb6e-a174516136a1.png)

![Screenshot 2023-04-17 173241](https://user-images.githubusercontent.com/119477857/232480043-e9b15063-0fa4-4804-9388-fc4bafc3c890.png)

![Screenshot 2023-04-17 173248](https://user-images.githubusercontent.com/119477857/232480071-7348d999-c833-449f-98da-899a1703078e.png)

![Screenshot 2023-04-17 173256](https://user-images.githubusercontent.com/119477857/232480091-4992e4d5-f262-4208-b264-63b3e1213239.png)

![Screenshot 2023-04-17 173303](https://user-images.githubusercontent.com/119477857/232480112-95043005-3c85-4da4-99a7-c066366fe16b.png)

![Screenshot 2023-04-17 173323](https://user-images.githubusercontent.com/119477857/232480141-6471a1fe-37b6-4a43-9042-09207c51916e.png)

![Screenshot 2023-04-17 173340](https://user-images.githubusercontent.com/119477857/232480186-37b4be38-0067-40dd-904b-3d08a408282a.png)

![Screenshot 2023-04-17 173348](https://user-images.githubusercontent.com/119477857/232480205-4bf79249-8a05-47ab-a2de-7b45b4794638.png)

![Screenshot 2023-04-17 173355](https://user-images.githubusercontent.com/119477857/232480231-b4560f52-6f1b-4652-a972-1300447ffcf4.png)

![Screenshot 2023-04-17 173401](https://user-images.githubusercontent.com/119477857/232480251-85aefb38-9af8-443b-8dcf-c6e11e924a0f.png)

## RESULT
Hence The Performance of the Multivariate EDA on the given data set is verified.
