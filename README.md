# Amazon Prime Users SQL Data Analysis

## Project Overview
This project analyzes Amazon Prime user data to gain insights into user demographics, subscription trends, engagement metrics, content preferences, and customer feedback. The goal is to identify patterns and trends that can help improve user retention, engagement, and overall satisfaction.

## Problem Statement
The goal of this project is to analyze Amazon Prime user data to:
1. Understand user demographics (age, gender, location).
2. Analyze subscription trends (plan preferences, churn rate, subscription duration).
3. Evaluate user engagement (engagement scores, renewal rates).
4. Identify content preferences (popular genres, devices used).
5. Assess customer feedback and support interactions.

## Data Processing Steps
1. **Import Libraries**
   - Pandas, NumPy, Matplotlib, Seaborn for data handling and visualization.
   - PyMySQL and SQLAlchemy for database connection.

2. **Load and Clean Data**
   - Read the dataset into a Pandas DataFrame.
   - Rename columns for consistency.
   - Convert date columns to datetime format.
   - Check for missing and duplicate values.
   - Identify numerical, categorical, and date columns.

3. **Outlier Detection**
   - Use Seaborn boxplots to visualize potential outliers in numerical data.

4. **Database Setup**
   - Connect to MySQL and create the `amazon_prime` database if it doesn't exist.
   - Load the cleaned DataFrame into MySQL.


## Key Insights

### User Demographics
1. **Age Distribution**:
   - The majority of users (48.52%) are aged 56+.
   - Younger users (18-25) constitute the smallest proportion (8.92%).
2. **Gender Distribution**:
   - The user base is almost equally distributed between genders: 50.4% male and 49.6% female.
3. **Location**:
   - The top locations with the highest number of users are **New Jennifer** and **East Robert**, each with 5 users.

### Subscription Analysis
1. **Subscription Plans**:
   - **Annual Plan**: 1,271 users.
   - **Monthly Plan**: 1,229 users.
2. **Churn Rate**:
   - The churn rate is **11.36%**, indicating a need for improved retention strategies.
3. **Subscription Duration**:
   - The average subscription duration is **365 days**, suggesting a preference for annual plans.

### User Engagement
1. **Engagement Scores**:
   - Users on the **Monthly Plan** have a slightly higher average engagement score (2.01) compared to the **Annual Plan** (2.0063).
2. **Engagement Distribution**:
   - High engagement: 845 users.
   - Medium engagement: 834 users.
   - Low engagement: 821 users.
3. **Renewal Rates**:
   - High engagement users have a **53.4% auto-renew rate**, indicating stronger retention.

### Content Preferences
1. **Popular Genres**:
   - **Horror** and **Action** are the most frequently purchased genres.
   - **Sci-Fi** is the least purchased genre.
2. **Devices Used**:
   - **Smartphones** are the most commonly used device (867 users), followed by **Tablets** (853 users) and **Smart TVs** (780 users).

### Customer Feedback and Support
1. **Feedback Ratings**:
   - Both subscription plans receive similarly high feedback ratings: **4.00 (Annual Plan)** and **4.01 (Monthly Plan)**.
2. **Support Interactions**:
   - Feedback ratings are not significantly impacted by the number of customer support interactions.

### Trend Analysis
1. **New Users Over Time**:
   - **January 2024** saw the highest number of new users (773), while **April 2024** had the lowest (332).
2. **Seasonal Trends**:
   - **Winter** has the highest number of new subscriptions (1,424 users).
3. **Engagement of Recent Users**:
   - A similar proportion of new users from the last year belong to each engagement category, indicating even distribution.

## Recommendations:

-**Retention Strategies:** Personalized re-engagement campaigns, loyalty rewards, and flexible subscription plans.

-**Engagement Optimization:** Referral programs, exclusive content perks, and targeted push notifications.

-**Content Strategy:** Expanding popular genres like Horror & Action, promoting Sci-Fi, and introducing seasonal content offers.

-**Device Optimization:** Enhancing mobile and Smart TV experiences with interactive features and offline downloads.

-**Customer Support Improvements:** AI chatbots for faster query resolution and premium-tier support.

-**Seasonal Marketing:** Winter-exclusive promotions and predictive trend-based campaigns.
