# Sales Forecasting
The data used for this project is available on [Kaggle](https://www.kaggle.com/c/rossmann-store-sales) from the "Rossmann Store Sales" Competition from six years ago. It contains time-series data from 1115 different stores (Sales, Customers, Promotions, ...) as well as additional data related to the stores (type of store, type of assortment, ...). 

In addition, data about the stores location was included thanks to the work shared by a Kaggle member (Dune_Dweller) [source](https://www.kaggle.com/c/rossmann-store-sales/discussion/17048), and completed with demographic data shared by another Kaggle member (Nicolas Gaude) [source](https://www.kaggle.com/c/rossmann-store-sales/discussion/17229).


## Use of:
* **Python** version 3.9.7
    * **Main Packages used:** pandas, seaborn, sklearn, pickle, LIME
* **Tableau Public**

# Overview
## Main Results
* For most stores, sales have increased between the given time period (2013-2015)
* On average, sales are relatively higher when there is a promotion & an "extra" or "extended" type of assortment (instead of a "basic" one)
* Moreover, the area in which the store is located plays an important role on sales. Stores located on more populated areas, with higher GDPs, get more sales.
* Promotions have a mixed effect on sales. Normal promotions running in a given day seem to increase sales, but ongoing promotions (Promo2) seem to be associated with lower sales.
* The final model is a RandomForestRegressor with a R2 = 0.903, a RMSE = 960 and a MAE = 646 (based on performance on validation set)

### Test on Kaggle Competition (late submission)
* As recommended ([source](https://www.kaggle.com/competitions/rossmann-store-sales/discussion/17601)), before submitting I scaled back sales which did not impact other metrics besides the RMSPE, which decreased
* The model gets a public score of 0.11861 but a final score of 0.13248 (best final score in competition: 0.10021)

## Main Steps
* Conducted an exploratory data analysis to be able to better understand the data and clean it for future forecasting 
* Applied an Adfuller statistical test to verify stationarity
* Studied differences between the best and worst performing stores
* Conducted further analysis thanks to visualizations on [Tableau](https://public.tableau.com/app/profile/paula2733/viz/Sales_16476157430450/SalesReport)
* Applied a preprocessing pipeline to clean validation set
* Explored different tree-based models and fine-tuned hyperparameters on the best peforming models using 3-fold cross validation with time series split
* Applied a preprocessing pipeline to clean validation set to test model performance
* Visualized feature importance as well as interpretations with LIME (Local Interpretable Model-agnostic Explanations)
* Cleaned and predicted on test data from competition then applied a late submission with final RMSPE score of 0.13248 (best final score in competition: 0.10021 *--[Leaderboard](https://www.kaggle.com/competitions/rossmann-store-sales/leaderboard)*)

