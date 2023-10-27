# Churn at Flatiron Communications

![image](https://user-images.githubusercontent.com/96458808/157768617-494374d0-7b78-40cf-ac06-bb6bef64a0ff.png)

## Business Problem
Currently, there is massive competition between 6 major cellular providers. “Churn”, a jargon term, refers to the lost of previously subscribed customers. Churn is a major problem within the telecommunications industry with an average churn rate of 22% per year. Additionally, new cellular customers are hard to come by with customer acquisition costs continuing to soar. Approximately, 9 out of 10 customers have churned in the last 5 years with about 50% of them unsubscribing while maintaining a balance on their bill. Given that nearly 1 in 4 customers are churning each year, retaining  existing customers has never been more important.

Flatiron Communications, a multinational telecommunications company, has approached our team to find out how they can reduce churn. Thus, we are tasked with generating a binary classification model to identify customers at risk of churning from Flatiron Communications, our stakeholder. We will optimize our model to reduce amount of money lost due to churn.

## Data and Preparation
Our dataset for this project was sourced from kaggle : https://www.kaggle.com/jpacse/datasets-for-churn-telecom. Exploratory data analysis (EDA) revealed a dataset containing 58 features and 51,047 entries, with our target variable being a binary classification of churn. After further EDA, we began the process of data cleaning and filtering. We dropped the null values in the dataset as well as dropped columns that were not pertinent to the business problem. Futhermore, we converted the Service Area data to Zipcode. Additionally, we converted our cartergorical values to numeric values to allow for modeling going forward. At the end of the cleaning process we had a total of 49,752 entries with 51 features. Customers who did not churn numbered 35,507 while 14,245 entries were classified as customers who did churn. 

### Methods
Our dataset comes from an anonymous top 6 cellular provider and contains information on over 50,000 customers with data collected through 2014. Though nearly 50% of churn is due to nonpayment, our dataset only contained data of those who churned for reasons other than nonpayment. Both Scikit-Learn and SciPy were used to contruct and run our model. 

## Modeling
We ran several models while optimizing hyperparameters throughout. We started off with a baseline DummyClassifier model.  We then built a DecisionTreeClassifier to identify features of importance for future model iterations. Next, we ran a LogisticRegression model as well as a KNN model. Our final model was a DecisionTreeClassifier optimized with GridSearchCV. Recall was used as our primary evaluation metric. Evaluating for recall worked best when pertaining to the business problem given that average revenue per user (APRU) was nearly $60 and customer retention costs (CRC) were assumed to be negligible. Using recall allowed us to optimize to reduce false negatives or not identifying customers that would churn. 

### Results
The DecisionTreeClassifier optimized with GridSearchCV proved to have the best recall score: 91.2%!

![image](https://i.imgur.com/57gFNhT.png)

From the LogisticRegression model we identified the 3 most impactful predictors of churn:

  1. Customers are 1.45x times as likely to churn for every day that they hold the same cell phone.
  2. Customers are 1.23x times as likely to churn for every additional subscriber added onto a plan.
  3. Customers are 1.16x times as likely to churn for every 1% increase in charges.

## Conclusions & Recommendations

Based on our analyses we recommend our stakeholder implement 3 targeted approaches to reduce churn:

  1. Offer discounted or complimentary cell phone upgrades for loyal customers to receive the latest devices. 
  2. Create  a loyalty program to reward multiple subscriber customers.
  3. Control customer charges by avoiding increasing fees on customers bills. 

## Next Steps
The next iterative step in this project is to segement customer data by region, using either zip code or state. This would allow us to develop a more focused model and generate specific recommendations are customer patterns likely vary by region. Given the high incidence of churn in general we also recommend investing in a dedicated team to proactively monitor and address dissatisfaction among customers with the potential to churn.

## For More Information
View the full analysis via the [Jupyter Notebook](https://github.com/chris161011/P3_Project/blob/main/Main%20Notebook.ipynb).

