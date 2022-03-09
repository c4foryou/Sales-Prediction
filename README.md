# Walmart Store Sales Prediction (Random Forest)

# **Summary**

**Introduction**: 

This is a predictive analysis for future weekly sales for 45 different Walmart stores, which was subject for **Walmart Recruiting - Store Sales Forecasting competition** held on Kaggle in 2012. ([https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting/submissions](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting/submissions))

I choose this past competition for the practice purpose as it provides a clear dataset and requires a unique evaluation metric, WMAE(giving more weight on accuracy for sales prediction for holiday weeks), for the model.

**Datasets**:

Train Data → Weekly sales data from Feb 2010 to Oct 2012 by each store and department.

Test Data → The data from Nov 2012 to Jul 2013 and weekly sales column is omitted.

Store Data → Type and size information of each store

Feature Data → Temperature, fuel price and markdown information for each date and store

**Language and libraries**: Python, Pandas, Sklearn, Seaborn

**ML Algorithm**: Random Forest

**Evaluation**: 

![ex_screenshot](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/aa643311-7fd3-4b6c-8e06-b79021ece867/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220309%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220309T184015Z&X-Amz-Expires=86400&X-Amz-Signature=b2fd202a6553f7d5806d0ced3efb51d167ba240a8f979aedd97dc8a216fb510c&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)

**Final Result**: 483 WMAE for the train data and 2,797 for the private data(equivalent to top 50 scores)

**Takeaways and future study topics**:

1. How to distinguish good variables
    
    Adding all variables is not always good. Some variables which have a weak correlation with Y can disturb the training of the model, and accuracy was improved after removing these features from the dataset. 
    
    In this project, I found the model’s WMAE was significantly decreased after dropping ‘Temperature’, ‘Fuel Price’ and ‘Is Holiday’ columns. These columns also showed a low correlation with ‘Weekly Sales’, our Y variable. ‘Is Holiday’ column seemed very important for the prediction, but as the ‘Week’ column provides more details, I guess it was no more necessary for the model after adding the ‘Week’ information on the dataset.
    
    However, some columns, ‘Day’ and ‘Year’, which have small correlation, but are related to date was not helpful to improve WMAE when they are removed. It remains questions to me and further study is needed to understand reasons.
    
2. More advanced hyperparameter optimization is required
    
    I tried to find the best numbers for the hyperparameters, however, due to computational burden and long processing time, I could run a code for hyperparameter searching only for two hyperparameters. For the next project, I’d like to apply grid search and test more numbers for more hyperparameters to improve the model and find an optimal point that helps me to avoid overfitting problems.
