### Guideline

The assessment focuses on how well you could master the data science tools we covered to serve your quantitative analysis purpose. Each team wants to prepare a 30-min presentation that covers both the source code and slides.  

1. Focus on the stock you pick and their competitors. Report summary statistics of the training period you select and visualize the kernel density. You may use the 10+ sample code shared in Lecture 1 for reference. 

2. Please use the features/factors you take and discovered (e.g. FRED, Fama-French website, ADS, momentum factors, technical indicators, volume, price/return lags, etc.) to construct a feature database. The target variable Y can be either price or return. Extra credits will be given if you use more self-engineered or self-discovered features. Frequency could be either daily or monthly. You may use the following sample code and database as resources: (1) sample code:  Lecture03_FeaturePreparation_NoAPI.ipynb (2) database: [FRED](https://fred.stlouisfed.org), [Fama-French](https://mba.tuck.dartmouth.edu/pages/faculty/ken.french/data_library.html), and [ADS](https://www.philadelphiafed.org/surveys-and-data/real-time-data-research/ads)

3. Demonstrate the feature selection process if you use regression-based approach (Ridge regression, LASSO, Elastic Net or LARS) . Virtualize the feature importance if you use decision-tree-based approach (random forest, XGBoost). You may use the following demo code for reference: Lecture03_FeatureSelection.ipynb, Lecture04_Random_Forest.ipynb (to be covered) and Lecture04_XGBoost.ipynb (to be covered). 

4. Design and train 3-6 quantitative models by feeding the prediction equation with the features you prepared in step 2.  Compare the model performance using RMSE (or recall, precision) between the fitted Y and actual Y in both training and testing periods. You are free to choose the training and sampling periods yourself. You are also free to explore the best model configuration according to your algorithm trading performance (e.g. rolling window length, training start-date, etc.). You may use the following sample code for reference: Lecture03_BackTesting.ipynb

5. Include one benchmark study that uses GARCH or Kalman Filter. You may use all the 5+ sample code shared in Lecture 2 for reference. 

6. Compose of trading rules that uses buy-and-hold, long-short, or day trade. 

7. Generate trading signals using the above 3-6 models. Compare their Profit and Losses.  