# Ex-04-Multivariate-Analysis
## AIM
To perform Multivariate EDA on the given data set.

## EXPLANATION
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM
### STEP 1
Import the built libraries required to perform EDA and outlier removal.

### STEP 2
Read the given csv file

### STEP 3
Convert the file into a dataframe and get information of the data.

### STEP 4
Return the objects containing counts of unique values using (value_counts()).

### STEP 5
Plot the counts in the form of Histogram or Bar Graph.

### STEP 6
Use seaborn the bar graph comparison of data can be viewed.

### STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()

### STEP 8
Save the final data set into the file

# Program
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

# Bivariate Analysis
```python
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5, aspect=.7)

sns.catplot(x='Survived',hue = "Gender",data = dt,kind = "count")

fig, ax1 = plt.subplots(figsize=(8,5))
graph = sns.countplot(ax=ax1,data=dt,x="Survived",hue="Pclass",palette="rainbow")
graph.set_xticklabels(graph.get_xticklabels())
for p in graph.patches:
  height = p.get_height()
  graph.text(p.get_x()+p.get_width()/2, height + 20.8,height,ha="left")

dt.boxplot(column="Age",by="Survived")

sns.scatterplot(x = dt["Age"],y = dt["Fare"])
```

# Multivariate Analysis
```python
fig, ax1 = plt.subplots(figsize = (8,5))
pt = sns.boxplot(ax = ax1,x = 'Pclass',y = 'Age', hue='Gender',data=dt)

sns.catplot(data=dt,col="Survived",x="Gender",hue ="Pclass",kind = "count")

g = sns.catplot(data=dt,col="Survived",x="Gender",hue ="Pclass",kind = "count",legend=True)
g.fig.set_size_inches(8,5)
g.fig.subplots_adjust(top=0.81,right=0.86)
ax = g.facet_axis(0,0)
for p in ax.patches:
  ax.text(p.get_x()- 0.01,p.get_height() * 1.02,'{0:.1f}'.format(p.get_height()),color='red',rotation='horizontal',size='small')

corr = dt.corr()
sns.heatmap(corr,annot=True)

sns.pairplot(dt)
```

# Output
![image](https://github.com/vinushcv/Ex-04-Multivariate-Analysis/assets/113975318/447dca3d-b28d-4eda-af37-64e137732ed9)

![image](https://github.com/vinushcv/Ex-04-Multivariate-Analysis/assets/113975318/b4f1591d-6c6e-479c-aa93-adcc9e7b99f4)

![image](https://github.com/vinushcv/Ex-04-Multivariate-Analysis/assets/113975318/0c90fbe4-12c9-483c-b836-911b26b3f7bb)

![image](https://github.com/vinushcv/Ex-04-Multivariate-Analysis/assets/113975318/065f119e-4857-41cd-99df-b8eb5583c3a6)

![image](https://github.com/vinushcv/Ex-04-Multivariate-Analysis/assets/113975318/0b76a83d-caca-41f9-b50c-8ea7ad43a8c0)

![image](https://github.com/vinushcv/Ex-04-Multivariate-Analysis/assets/113975318/998eba86-6e0f-4174-a8e3-bcefcc788ff9)

![image](https://github.com/vinushcv/Ex-04-Multivariate-Analysis/assets/113975318/c0d5343b-372d-4465-a802-e1afaf7a881e)

![image](https://github.com/vinushcv/Ex-04-Multivariate-Analysis/assets/113975318/312ad99c-7351-4aad-9b9f-bfd117bad97f)

![image](https://github.com/vinushcv/Ex-04-Multivariate-Analysis/assets/113975318/cab62416-0b13-4d76-a2fa-301efc400635)

![image](https://github.com/vinushcv/Ex-04-Multivariate-Analysis/assets/113975318/aaf952e4-bdc5-40bf-b1fb-3d7ebfc16668)

# Result
Thus,The program has been Executed Successfully.










