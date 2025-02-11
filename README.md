# Amazon Prime Users SQL Data Analysis

## Project Overview
This project analyzes the Amazon Prime users dataset to gain insights into user demographics, subscription patterns, engagement levels, and content preferences. The data is loaded into a MySQL database, and various SQL queries are used to extract meaningful insights.

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

## Key Analysis & Insights
### 1. User Demographics
- **Age Distribution:** Majority of users (48.52%) are aged 56+.
```sql
   SELECT Age, COUNT(UserID) AS UserCount 
   FROM Users 
   GROUP BY Age 
   ORDER BY UserCount DESC;
```

- **Top Locations:** Cities with the highest number of users include New Jennifer, East Robert, and Johnsonside.
```sql
   SELECT location, COUNT(user_id) AS user_count
   FROM amazon_prime_users
   GROUP BY location
   ORDER BY user_count DESC
   LIMIT 10;
```

- **Gender Split:** Almost equal distribution between male (50.4%) and female (49.6%) users.
```sql
    SELECT gender, COUNT(*) AS user_count
    FROM amazon_prime_users
    GROUP BY gender;
```


### 2. Subscription Analysis
- **Subscription Plans:** 1,271 users prefer the Annual plan, while 1,229 choose Monthly.
```sql
   SELECT Age, COUNT(UserID) AS UserCount 
   FROM Users 
   GROUP BY Age 
   ORDER BY UserCount DESC;
```

- **Churn Rate:** 11.36% of users did not renew their membership.
```sql
   SELECT Age, COUNT(UserID) AS UserCount 
   FROM Users 
   GROUP BY Age 
   ORDER BY UserCount DESC;
```

- **Average Subscription Duration:** 365 days, indicating a preference for annual plans.
```sql
    SELECT subscription_plan, COUNT(user_id) AS user_count
    FROM amazon_prime_users
    GROUP BY subscription_plan;
```


### 3. User Engagement
- **Engagement Distribution:** High (845 users), Medium (834 users), Low (821 users).
```sql
   WITH UserStatus AS (
    SELECT 
        COUNT(*) AS total_users,
        SUM(CASE WHEN membership_end_date < CURDATE() THEN 1 ELSE 0 END) AS churned_users
    FROM amazon_prime_users
)
   SELECT 
    churned_users / total_users AS churn_rate
   FROM UserStatus;
```

- **Auto-renewal Correlation:** Higher engagement leads to higher auto-renewal rates.
- ```sql
   SELECT Age, COUNT(UserID) AS UserCount 
   FROM Users 
   GROUP BY Age 
   ORDER BY UserCount DESC;
```sql


### 4. Content Preferences
- **Popular Genres:** Drama, Horror, and Action are the most-watched genres for Annual subscribers.
- ```sql
   SELECT Age, COUNT(UserID) AS UserCount 
   FROM Users 
   GROUP BY Age 
   ORDER BY UserCount DESC;
```sql


## Technologies Used
- Python (Pandas, NumPy, Matplotlib, Seaborn)
- MySQL (PyMySQL, SQLAlchemy)
- Jupyter Notebook for analysis

## Future Enhancements
- Predict churn rate using machine learning.
- Recommend personalized content based on engagement trends.
- Integrate with a dashboard for real-time data visualization.

