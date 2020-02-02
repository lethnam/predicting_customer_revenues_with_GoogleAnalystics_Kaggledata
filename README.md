## Summary: Predicting customer revenue with Google Analytics data

Click [here](https://nbviewer.jupyter.org/github/lethnam/predicting_customer_revenues_with_GoogleAnalystics_Kaggledata/blob/master/ga_kaggle.ipynb) to see the codes + interactive plots

The data come from [a Kaggle competition](https://www.kaggle.com/c/ga-customer-revenue-prediction). The objective is to predict the transaction revenue per customer, given a set of indicators from the GStore. In this notebook,

1. I first check and transform the data to gather all the necessary predictors
2. Then, I do extensive exploratory data analyses that involves data visualization with matplotlib, seaborn and plotly
3. Since less than 2% of all visitors decided to purchase, the sample is highly imbalanced. Thus, in order to predict the revenue per customer, I carry out a 2-step procedure:
    - First, try to classify buyers vs. non-buyers. Non-buyers obviously will give 0 revenue. Here, I compare the classifying accuracy scores with and without randomly under-sampling to balance out the sample.
    - Second, given the sample of only the actual buyers, using regression models to predict the revenue.
    
    For both classification and regression, I will compare the performances of the models: Support Vector Machine, Logistic/Linear Regression, Decision Tree, Random Forest, AdaBoost with Decision Tree, Adaboost with Random Forest, and Extreme Gradient Boosting library XGBoost.
    
In the end, XGBoost gives the best performances in both classification (with the re-balanced under-sampling train sample) and regression.