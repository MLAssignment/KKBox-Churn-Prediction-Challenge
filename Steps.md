# Steps
1.	Data Analysis
2.	Data Cleansing
3.	Feature Engineering
4.	Model Identification
5.	Train and validate the model 
6.	Predict the is_churn for test.tsv data using the trained model

## Data Analysis

### Target Variable
• is_churn :- is target variable and we need to predict it for test data.

### Features in the original data set

[is_churn, payment_method_id,payment_plan_days,plan_list_price,actual_amount_paid,is_auto_renew,transaction_date,embership_expire_date,is_cancel, city, bd,	 gender,	registered_via,	registration_init_time, date,num_25,num_50,num_75,num_985,num_100,num_unq,total_secs]

### 	Numerical features

[payment_plan_days, plan_list_price, actual_amount_paid, num_25, num_50, num_75, num_985, num_100, num_unq, total_secs,registered_via]

### 	Categorical features

[ payment_method_id,is_auto_renew,  is_cancel, city, bd, gender, registered_via]

### Data Observations
• Data imbalance - in train data set is_churn value percentages is ~93% for value 0 and ~7% for value 1
• Gender distribution is pretty equal
• The majority of users come from city 1
• The major registration method is 4,9,3

## Cleansing Data
1. Missing value handling
2. Data Encoding


## Feature Engineering
Upon further analysis, we are able create some new variables that extract hidden information in the data. Below is a complete break down of all the
new variables that contains predictive power

1. discount: Plan list price subtract actual amount paid. 
2. is_discount: Whether the user received a discount, of discount > 0
3. autorenew_&_not_cancel: If a user is using auto-renew and is not a canceled user.
4. notAutorenew_&_cancel: If a user is not using auto-renew and is a canceled user.
5. membership_duration: Number of days between membership expire date and transaction date.
6. registration_duration: Number of days between membership expire date and registration init date.

## Model Identification
1. Identified the category of the problem statement (Classification)
2. Identified 3 algorithms logistic regression classifiers, artificial neural networks and decision trees that they are often used for classification problems.
3. Performances of classification techniques were compared using accuracy scores.
4. In the result, artificial neural networks have highest accuracy score over logistic regression and  decision tree.
  
## Train and Validate the model
We have used Logistic Regression, Decision Classifier, MLPClassifier (Neural Network)  model from scikit learn library to train the model.  Parameters used for algorithms are as below

1. Logistic Regression : - ' class_weight = balanced, C=1'
2. Decision Classifier : - 'criterion = 'entropy', random_state = 0'
3. MLP Classifier :  'activation='relu', max_iter=10000, hidden_layer_sizes=(8,10)'

# Potential shortcomings
1. We could generate more features using dummy coding.
2. Model is not created using Random Forest for classification & regression.
3. We could improve  on handling large datasets.


# Possible improvements
1. We can try to generate more features using dummy encoding and see if it improves accuracy score.
2. We can try using Random Forest algorithm.
3. Generate more features by extracting hidden information.
4. Handling larger datasets.
5. Exploring more parameters in algorithms
