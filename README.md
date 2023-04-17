# Ex-04-Multivariate-Analysis
# AIM:
To perform Multivariate EDA on the given data set.

# EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:
# STEP 1:
Import the built libraries required to perform EDA and outlier removal.

# STEP 2:
Read the given csv file.

# STEP 3:
Convert the file into a dataframe and get information of the data.

# STEP 4:
Return the objects containing counts of unique values using (value_counts()).

# STEP 5:
Plot the counts in the form of Histogram or Bar Graph.

# STEP 6:
Use seaborn the bar graph comparison of data can be viewed.

# STEP 7:
Find the pairwise correlation of all columns in the dataframe.corr() .

# STEP 8:
Save the final data set into the file.

# Program:
```
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

sns.scatterplot(x=data['Country'],y=data['Sales'],data=data)

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

sns.barplot(data['Postal Code'],data['Ship Mode'],hue=data['Region'])

data.corr()

sns.heatmap(data.corr(),annot=True)
```
# OUTPUT:
# DATASET:
![image](https://user-images.githubusercontent.com/118708245/232392862-05f4dc2a-7421-4888-8715-be42c6ce2b7e.png)
# HEAD():
![image](https://user-images.githubusercontent.com/118708245/232394249-050ea832-16ee-4dd9-b1eb-b5a86604eadd.png)
# INFO():
![image](https://user-images.githubusercontent.com/118708245/232394386-787b4a55-8cd9-42fa-abca-0e0f63f05aa4.png)
# DESCRIBE():
 ![image](https://user-images.githubusercontent.com/118708245/232394495-36f3feef-a4dd-482c-b015-9260ae9ca439.png)
 # DATATYPE():
![image](https://user-images.githubusercontent.com/118708245/232394851-168b2175-8ab0-4d1c-9ffd-2e40fdfa088e.png)
# ISNULL():
![image](https://user-images.githubusercontent.com/118708245/232394940-608b382d-0f6a-4640-8b26-56584dcd395b.png)
# POSTAL CODE HAS OUTLIERS():
![image](https://user-images.githubusercontent.com/118708245/232395164-7233c429-0b71-413d-bb71-7acde2a648c0.png)
# After removing outliers from Postal Code:
# MULTIVARIATE ANALYSIS:
# SCATTER PLOT:
![image](https://user-images.githubusercontent.com/118708245/232395438-3520aea0-76ff-49a8-8d58-9c5fc97a9c47.png)
# BARPLOT:
![image](https://user-images.githubusercontent.com/118708245/232395644-e4f84c7a-7d8a-4658-a768-ba74a4a945ae.png)
![image](https://user-images.githubusercontent.com/118708245/232396002-2d94816d-afa7-4639-a09b-139eabd7e458.png)
# SEGMENTATION:
![image](https://user-images.githubusercontent.com/118708245/232396347-09a22fcf-9f99-45df-a343-33935e77a52a.png)
# CORRESSION:
![image](https://user-images.githubusercontent.com/118708245/232396595-fdb9eee0-489e-4b85-9a42-282662b6d115.png)
# HEATMAP:
![image](https://user-images.githubusercontent.com/118708245/232396789-19d7a0b3-0cc6-46a7-bd37-ea3132ed28b0.png)

# RESULT:
Hence The Performance of the Multivariate EDA on the given data set is verified.



