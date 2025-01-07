# Yelp Restaurant Rating Analysis: A Personal Data Science Project

## Overview
In this project, I analyzed factors that most influence a restaurant’s rating on Yelp using a real-world dataset. The restaurant industry is competitive, and online reviews can significantly impact a restaurant’s success. Understanding the factors that drive Yelp ratings can help restaurant owners, marketers, and other stakeholders optimize their business strategies.

I used Yelp’s public dataset to build a multiple linear regression model that identifies the key features affecting Yelp ratings. This project gave me the opportunity to apply machine learning techniques, perform data cleaning and preprocessing, and analyze feature importance in a real-world context.

## Project Workflow

### Step 1: Data Exploration & Preparation
To begin, I loaded the provided Yelp dataset into my environment, which consisted of several JSON files. These included:
- Yelp Business Data (location, attributes)
- Yelp Review Data (text, rating, sentiment)
- User Profile Data (demographics, review history)
- Other Metadata (check-ins, tips, photos)

I started by exploring the data to understand its structure and identify potential issues (e.g., missing values, incorrect formats). I then performed several preprocessing tasks to clean the data, such as:
- **Handling Missing Values**: I used imputation for missing numeric values and dropped rows where necessary.
- **Feature Encoding**: I transformed categorical features (like `has_wifi` and `price_range`) into numerical representations using one-hot encoding.

### Step 2: Feature Engineering & Analysis
Once the data was clean, I analyzed the key features that could potentially affect Yelp ratings. Some of the features I worked with included:
- **Average Review Sentiment**: Positive vs. negative sentiment in reviews
- **Price Range**: The restaurant’s price range, which could influence rating behavior
- **Amenities**: Features like Wi-Fi, bike parking, and whether the restaurant accepts reservations
- **User Demographics**: Factors like the number of friends or review activity for users

I used correlation matrices and visualization techniques to explore relationships between these features and the Yelp rating. From my analysis, I identified a few features that appeared to have a significant correlation with ratings, such as `average_review_sentiment` and `price_range`.

### Step 3: Modeling
With the clean data and selected features, I trained a Multiple Linear Regression Model. I used the scikit-learn library to split the data into training and testing sets, then trained the model to predict Yelp ratings based on the features.

Some important steps included:
- **Feature Scaling**: To ensure that features like `review_count` or `average_number_years_elite` didn’t dominate the model due to their large scale, I used StandardScaler to scale numerical features.
- **Model Evaluation**: I evaluated the model’s performance using metrics such as R-squared and Mean Absolute Error (MAE).

My initial results showed a model performance (R-squared) of around 0.65, which indicated that approximately 65% of the variance in Yelp ratings could be explained by the selected features.

### Step 4: Model Improvement & Hyperparameter Tuning
After building the initial model, I focused on improving performance:
- I explored feature selection techniques, such as recursive feature elimination (RFE), to remove non-significant features that may have been introducing noise.
- I experimented with regularization techniques (Lasso and Ridge regression) to prevent overfitting and improve the generalization of the model.

With some adjustments, I was able to achieve a final model with an R-squared score of around 0.68, showing a slight improvement in predictive power.

### Step 5: Interpretation & Insights
After training the model, I analyzed the coefficients to understand which features had the greatest impact on the Yelp rating. Some of the most influential features included:
- **Average Review Sentiment**: More positive reviews tended to lead to higher ratings.
- **Alcohol Availability**: Restaurants offering alcohol were associated with slightly higher ratings, which could reflect the type of clientele.
- **Wi-Fi Availability**: Restaurants with Wi-Fi had a moderate negative impact on ratings, possibly indicating that such restaurants cater to a different crowd (e.g., students or freelancers).

## Key Lessons Learned
- **Data Cleaning is Crucial**: One of the biggest challenges was cleaning the dataset. Missing values and categorical variables required a lot of preprocessing, but getting this step right was crucial for the accuracy of the model.
- **Feature Engineering is an Art**: Identifying which features to use was a key part of the process. I had to experiment with various combinations of features, analyze correlations, and test how different features impacted the model’s performance.
- **Machine Learning Takes Iteration**: Achieving a good model performance wasn’t easy. I had to iterate multiple times, tuning the model, removing insignificant features, and experimenting with different algorithms to improve accuracy.
- **Interpreting Model Coefficients**: Understanding the relationship between the features and the target (Yelp rating) was a fascinating part of the project. It was insightful to see how certain features like sentiment and price range influenced ratings.

## Conclusion
This project provided me with hands-on experience in data exploration, feature engineering, and machine learning. It not only taught me how to build predictive models but also gave me the opportunity to understand real-world factors that influence a restaurant’s success.

By analyzing Yelp reviews and business data, I was able to uncover several key insights about restaurant ratings. The model I built can be useful for restaurant owners to optimize their operations and improve their reputation on Yelp.

## Project Files
- `yelp_regression.ipynb`: The notebook where I built and trained the model, including all steps for data cleaning, feature engineering, and model evaluation.
- `yelp_regression_solution.ipynb`: A reference notebook that shows how to approach the problem with a fully-solved solution.
- `yelp_business.json`: Contains business-related data such as location, attributes, and amenities.
- `yelp_review.json`: Contains review data, including ratings and review sentiments.
- `yelp_user.json`: Contains user-related data, including user demographics and review history.

## Getting Started
To run this project locally, clone this repository and install the necessary Python libraries:

```bash
git clone https://github.com/your-username/yelp-rating-analysis.git
cd yelp-rating-analysis
pip install -r requirements.txt
