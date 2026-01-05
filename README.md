# Maven-Music-Customer-Churn-Analysis

## 🎵 Music Streaming Customer Churn Prediction Project
### Predicting Subscription Cancellations Using Behavioral & Demographic Data
#### A Machine Learning Case Study in Customer Retention

## 🎯 Project Overview
This project demonstrates my expertise in customer analytics and churn prediction by developing a comprehensive machine learning pipeline to identify customers at risk of cancelling their music streaming subscriptions. Using behavioral data, listening history, and customer demographics, I built predictive models to help Maven Music proactively retain customers and reduce churn. This case study showcases my ability to transform raw business data into actionable insights through data cleaning, feature engineering, and predictive modeling.

## 🌍 Business Context & Problem Statement
**Scenario:** Maven Music, a music streaming service, is experiencing concerning subscription cancellation rates, particularly among customers who joined during promotional periods. Each lost customer represents significant lost revenue and acquisition costs:

- **Revenue Loss:** $2.99-$9.99 monthly per customer
- **Acquisition Costs:** $50-100 to acquire new customers
- **Growth Impact:** High churn rates hinder sustainable growth
- **Competitive Pressure:** Music streaming market is highly competitive with low switching costs

**Business Challenge:** Identify which customers are most likely to cancel their subscriptions within the next 3 months using past behavioral and demographic data.

**Key Questions:**
1. What customer behaviors predict cancellation?
2. Do promotional discounts increase or decrease long-term retention?
3. How does listening behavior affect customer loyalty?
4. Which features are most important for predicting churn?

## 🧩 Technical Challenges
Customer churn prediction in subscription services presents unique analytical challenges:

- **Imbalanced Data:** Only 43% of customers cancelled (13 out of 30)
- **Feature Engineering:** Creating meaningful behavioral features from raw listening data
- **Data Integration:** Merging multiple data sources (customer info, listening history, session logs)
- **Categorical Variables:** Handling subscription plans, genres, and discount status
- **Time-based Analysis:** Understanding membership duration and listening patterns over time

## 🛠️ Technical Implementation

### 1️⃣ Data Preparation & Cleaning
- **Multiple Data Sources:**
  - `maven_music_customers.csv`: 30 customers with 8 demographic/plan features
  - `maven_music_listening_history.xlsx`: 505 listening records across multiple sheets
- **Data Processing:**
  - Handled missing values (17% cancellation dates, 17% subscription plans)
  - Converted data types (datetime for dates, numeric for rates)
  - Cleaned inconsistent text (standardized genres, removed "Email:" prefix)
  - Fixed data entry errors (corrected $99.99 subscription rate to $9.99)
- **Feature Engineering:**
  - Created binary `Cancelled` target variable
  - Calculated membership duration in days
  - Engineered listening behavior features

### 2️⃣ Data Integration & Feature Creation
Successfully merged and transformed multiple datasets:

- **Customer Demographics:** Subscription plan, rate, discount status
- **Listening History:** 505 records across 30 customers
- **Audio Metadata:** Genre, popularity, content type
- **Session Data:** Timing and frequency of listening sessions

**Created Key Features:**
- `Cancelled`: Binary target (1 = cancelled, 0 = active)
- `Discount?`: Binary (1 = received discount, 0 = full price)
- `Number of Sessions`: Count of unique listening sessions per customer
- `Percent Pop`: Percentage of listening history in Pop genre
- `Percent Podcasts`: Percentage of listening to podcast content

### 3️⃣ Exploratory Data Analysis
Conducted comprehensive analysis to understand cancellation patterns:

- **Churn Rate Analysis:** 43.3% overall cancellation rate
- **Discount Impact Analysis:** 85.7% churn with discounts vs. 30.4% without
- **Listening Behavior Analysis:** Sessions per customer, genre preferences
- **Duration Analysis:** Average 46 days before cancellation
- **Correlation Analysis:** Identified relationships between all features

### 4️⃣ Statistical Modeling Preparation
Built a clean modeling dataset with:
- 30 customer records (appropriate for the available data)
- 5 engineered features capturing key behaviors
- Binary target variable for classification
- No missing values after imputation
- Properly scaled and encoded features

## 📊 Results & Key Findings

### 🔍 Exploratory Analysis Insights

#### **1. Dramatic Discount Impact**
```python
# Key Finding: Discounts correlate with higher churn
Discount customers: 85.7% churn rate
Non-discount customers: 30.4% churn rate
