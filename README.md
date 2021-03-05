# food-sales-predictions.

Overview/ Definition of Problem:
This is best framed as a unidimentional regression which predicts sales for food items at various stores, with the aim of highlighting features most associated with higher predicted sales, to help the retailer undestand the properties of products and outlets that play crucial roles in increasing sales.

Dataset:
The original dataset has 8523 entries with 12 columns and a total 3873 missing values; 1463 missing values in the Item Weight column and 2410 missing values in the Outlet Size column. There are several syntax errors within the Item Fat Content classes.

Data Cleaning & preparation:
Dealt with Item Weight missing values by inferring values of an Item from other entries based on the Item Identifier. Also corrected for syntax errors in the Item Fat Content classes. Outlet Size column was dropped because it was impossible to inferr the missing values from the original dataset, or to impute values correctly.

Exploratory Data Analysis:
Six features(columns) in the dataset are categorical; the exploratory data analysis thus included the use of boxplot(interactive plot) and clustermap that helped understand the data and trends within the data. The boxplot highlights the significant difference in the 1997 Outlet establishment Year, as well as the presence of outliers.


![image](https://user-images.githubusercontent.com/73043768/110136812-c09c4d00-7d95-11eb-924a-e1322fb7f5b6.png)

From the Clusterplot below, the Tier2 & Tier3 Outlet Location Types seem to be more associated with higher sales for the different item types.


![image](https://user-images.githubusercontent.com/73043768/110137699-c6466280-7d96-11eb-8325-ca737385ec65.png)


Model Building: Categorical columns were transformed into dummy variables for macine learning. Based on the fact that the Target/ predicted variable is numeric, regression model was considered. Also, given that the exploratory data analysis did not reveal multicollinearity between the variables, linear regression was first option. However, with nine predictor variables, a linear regression model would appear compllicated and there may be issues of overfitting to the model. LASSO regression eliminates this problem by culling predictor variables in order to simplify the model. For this, alpha was set to 16 as shown below:

Lasso(alpha=16, copy_X=True, fit_intercept=True, max_iter=1000, normalize=False,
      positive=False, precompute=False, random_state=None, selection='cyclic',
      tol=0.0001, warm_start=False)
      
A second model using RandomForest was build as a comparison with the LASSO model for predicting the Item Outlet Sales:

RandomForestRegressor(bootstrap=True, ccp_alpha=0.0, criterion='mse',
                      max_depth=5, max_features='auto', max_leaf_nodes=None,
                      max_samples=None, min_impurity_decrease=0.0,
                      min_impurity_split=None, min_samples_leaf=1,
                      min_samples_split=2, min_weight_fraction_leaf=0.0,
                      n_estimators=102, n_jobs=None, oob_score=False,
                      random_state=None, verbose=0, warm_start=False)


Summary of the Results:
