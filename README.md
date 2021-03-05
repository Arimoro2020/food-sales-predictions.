# food-sales-predictions.

Overview:
This project builds a macine learning model to predict sales for food items at various stores, highlighting features most associated with higher predicted sales, to help the retailer undestand the properties of products and outlets that play crucial roles in creasing sales.

Dataset:
The original dataset has 8523 entries with 12 columns and a total 3873 missing values; 1463 missing values in the Item Weight column and 2410 missing values in the Outlet Size column. There are several syntax errors within the Item Fat Content classes.

Data Cleaning & preparation:
Dealt with Item Weight missing values by inferring values of an Item from other entries based on the Item Identifier. Also corrected for syntax errors in the Item Fat Content classes. Outlet Size column was dropped because it was impossible to inferr the missing values from the original dataset, or to impute values correctly.

Exploratory Data Analysis:
Six features(columns) in the dataset are categorical; the exploratory data analysis thus included the use of boxplot(interactive plot) and clustermap that helped understand the data and trends within the data.


![image](https://user-images.githubusercontent.com/73043768/110136812-c09c4d00-7d95-11eb-924a-e1322fb7f5b6.png)

![image](https://user-images.githubusercontent.com/73043768/110137405-710a5100-7d96-11eb-94be-68802780c976.png)

