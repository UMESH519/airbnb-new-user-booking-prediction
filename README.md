# airbnb-new-user-booking-prediction
The aim of the project is to predict which country a new user's first booking destination will be. 


## Project Motivation

New users on Airbnb can book a place to stay in more than 34,000 cities across 190+ countries. By accurately predicting where a new user will book their first travel experience. Airbnb can:</br>
1) share more personalized content with their community. </br>
2) decrease the average time to first booking  </br>
3) Better forecast demand </br>

## Project Goal
The goal is to predict  top 5  destinations a new user is likely to book. Here, the rank of the relevant destination is an important consideration

## Data

Data consist of list of users along with their demographics, web session records, and some summary statistics and the task is to predict which country a new user's first booking destination will be. All the users in this dataset are from the USA. </br>
There are 12 possible outcomes of the destination country: 'US', 'FR', 'CA', 'GB', 'ES', 'IT', 'PT', 'NL','DE', 'AU', 'NDF' (no destination found), and 'other'. Please note that 'NDF' is different from 'other' because 'other' means there was a booking, but is to a country not included in the list, while 'NDF' means there wasn't a booking.

Data is Available at : https://www.kaggle.com/competitions/airbnb-recruiting-new-user-bookings/data

## Metric

Since the goal is to predict top 5 destinations a new user is likely to book; the rank of
the relevant destination is an important consideration. Thus we can’t simply use
accuracy as the classification metric. Instead we used Normalized Discounted
Cumulative Gain (NDCG) as the evaluation metric which takes care of the ranking of the
ground truth into context.

## Conclusions

<img width="615" alt="Screen Shot 2023-01-23 at 6 14 11 PM" src="https://user-images.githubusercontent.com/63723023/214181162-324057fd-2c7b-4b05-bd58-5e929c3eb205.png">

1) Naïve Bayes gives lowest NDCG score on training and test data. It assumes that features are independent, which is not true in most cases </br>
2) Logistic regression produces linear decision boundaries resulting in lower accuracy as compared to LightGBM / XGBoost /  ExtraTrees </br>
3) ExtraTrees, XGBoost and LightGBM produces better accuracy among these 6 models. </br>


## Interpretation 

1) Age is one of the most important feature which helps in predicting the destination country </br>
2) Session metrics like average time per session, number of sessions play a significant role in deciding the destination </br>
3) Users who use certain actions like booking request, create listing are more likely to book for a destination </br>
4) Some other important factors like signup method, gender of the user helps in identifying the first destination




