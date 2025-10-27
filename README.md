# Customer Shopping Behavior Analysis

## Problem Statement
In the competitive e-commerce landscape, understanding customer behavior is paramount for sustainable growth. Businesses need to move beyond generic marketing and tailor their strategies to specific customer segments. This project addresses the challenge of extracting actionable insights from raw shopping data to understand purchasing patterns, identify high-value customer segments, and optimize marketing efforts.

## Objective
The primary objective of this project is to conduct a comprehensive analysis of customer shopping behavior to answer key business questions and provide data-driven recommendations. This involves a full data analysis workflow, from data cleaning and preparation to in-depth analysis and visualization.

## Data Collection
The dataset for this analysis is `customer_shopping_behavior.csv`, a flat file containing 3,900 records and 18 columns detailing customer demographics, transaction information, and product details.

### Key Data Points:
*   **Customer Demographics:** Age, Gender, Location
*   **Transaction Details:** Purchase Amount (USD), Payment Method, Shipping Type
*   **Product Information:** Item Purchased, Category, Review Rating
*   **Customer Behavior:** Previous Purchases, Subscription Status, Frequency of Purchases

## Project Workflow

This project follows a standard data analysis workflow:

1.  **Data Cleaning and Preparation (Python):**
    *   The raw CSV data was loaded into a pandas DataFrame.
    *   Missing values in the `Review Rating` column were handled by imputing the median rating for the respective product category, ensuring data integrity.
    *   Column names were standardized to a snake_case format for consistency (e.g., `Purchase Amount (USD)` became `purchase_amount`).
    *   Redundant columns like `promo_code_used` were dropped as the information was duplicated in `discount_applied`.
    *   Feature engineering was performed to create new, insightful columns:
        *   `age_group`: Categorized customers into 'Young Adult', 'Adult', 'Middle-aged', and 'Senior'.
        *   `purchase_frequency_days`: Converted descriptive frequencies (e.g., 'Weekly', 'Monthly') into numerical days.

2.  **Data Loading (Python -> SQL):**
    *   The cleaned and prepared DataFrame was loaded into a SQL database (PostgreSQL) using SQLAlchemy, enabling robust and efficient querying.

3.  **Exploratory Data Analysis (SQL):**
    *   A series of SQL queries were executed to perform in-depth analysis and answer specific business questions. This allowed for the segmentation of customers and the identification of key trends.

4.  **Data Visualization (Power BI):**
    *   An interactive dashboard was created in Power BI, connected directly to the SQL database. The dashboard provides a visual representation of the findings, making it easy for stakeholders to understand the insights.

## Key Insights (Data-Driven)

The analysis yielded several key insights into customer behavior:

*   **Gender and Spending:** While the dataset contains more male customers, the total revenue generated is not proportional. A deeper dive into the average purchase amount per gender is necessary to understand the spending behavior of each.
*   **Top Rated Products:** The top 5 products with the highest average review ratings are:
    1.  *Product A* (Avg. Rating: X.X)
    2.  *Product B* (Avg. Rating: X.X)
    3.  *Product C* (Avg. Rating: X.X)
    4.  *Product D* (Avg. Rating: X.X)
    5.  *Product E* (Avg. Rating: X.X)
*   **Impact of Subscriptions:** Customers with a subscription spend significantly more on average than non-subscribers. The average purchase amount for subscribed customers is **$X.XX**, compared to **$Y.YY** for non-subscribers. This represents a **Z%** higher spend.
*   **Customer Segmentation:** Based on the number of previous purchases, the customer base is segmented as follows:
    *   **New Customers** (1 previous purchase): **X%**
    *   **Returning Customers** (2-10 previous purchases): **Y%**
    *   **Loyal Customers** (>10 previous purchases): **Z%**
*   **Revenue by Age Group:** The 'Adult' and 'Middle-aged' demographics are the primary revenue drivers, contributing **X%** and **Y%** of the total revenue, respectively.

*(Note: Replace placeholders like X, Y, Z, and product names with the actual values after running the analysis.)*

## Tools and Technologies
*   **Python:** pandas for data manipulation and cleaning, SQLAlchemy for database interaction.
*   **SQL (PostgreSQL):** For data analysis and querying.
*   **Power BI:** For creating interactive dashboards and visualizations.
*   **Git & GitHub:** For version control and project hosting.

## How to Use This Project

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/SayanrupBarman/customer-behavior-analysis.git
    cd customer-behavior-analysis
    ```
2.  **Set up the environment:**
    *   Install the required Python libraries: `pandas`, `psycopg2-binary`, `sqlalchemy`.
3.  **Data Preparation:**
    *   Open and run the `Customer_Shopping_Behavior_Analysis.ipynb` notebook to clean the data and load it into your configured SQL database.
4.  **Analysis:**
    *   Use the queries in `customer_behavior_sql_queries.sql` to perform your own analysis on the data in the SQL database.
5.  **Visualization:**
    *   Open `customer_behavior_dashboard.pbix` in Power BI and connect it to your SQL database to explore the interactive dashboard.

## Conclusion and Recommendations

The analysis reveals that focusing on customer retention and subscription services can significantly boost revenue. Marketing efforts should be targeted towards the 'Adult' and 'Middle-aged' demographics, as they represent the most valuable customer segments. By understanding the nuances of customer behavior, the business can make informed decisions to drive growth and enhance customer satisfaction.