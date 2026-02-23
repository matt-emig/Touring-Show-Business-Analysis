# Touring-Show-Business-Analysis
1. Project Overview

This project analyzes the operational and financial performance of a fictional touring theatre production company. The objective is to simulate a real-world business intelligence workflow:

Clean and transform raw operational data using SQL

Build aggregated views for reporting

Connect structured outputs to Tableau

Design executive-level dashboards focused on revenue, attendance, cost, and profitability

The project mirrors a real analytics role in an entertainment or live-events company.

2. Business Context

A touring production company performs shows across multiple cities and venues. Leadership wants data-driven answers to:

Which cities generate the highest revenue?

Where are we underperforming relative to capacity?

What is our cost structure per venue?

Which tours are most profitable?

How does performance vary month-over-month?

The dataset includes:

Performances

Venues

Cities

Ticket sales

Average ticket prices

Operational costs

3. Tech Stack

SQL (data cleaning, transformation, aggregation)

Tableau (dashboard creation & visualization)

Relational database (PostgreSQL / MySQL compatible)

4. Data Model
Core Tables

performances

performance_id

show_id

venue_id

performance_date

tickets_sold

ticket_price_avg

venues

venue_id

venue_name

city_id

capacity

cities

city_id

city_name

country

costs

performance_id

venue_cost

staff_cost

marketing_cost

5. SQL Workflow
Step 1 – Data Cleaning

Remove duplicate performance entries

Handle NULL values in dates and costs

Standardize city names

Ensure numeric types for revenue calculations

Step 2 – Feature Engineering

Create calculated fields:

revenue = tickets_sold * ticket_price_avg
total_cost = venue_cost + staff_cost + marketing_cost
profit = revenue - total_cost
capacity_utilization = tickets_sold / capacity
Step 3 – Aggregated Views

Examples:

Revenue by City

SELECT city_name,
       SUM(revenue) AS total_revenue
FROM performance_summary
GROUP BY city_name;

Monthly Performance

SELECT DATE_TRUNC('month', performance_date) AS month,
       SUM(revenue) AS revenue,
       SUM(profit) AS profit
FROM performance_summary
GROUP BY month;

Venue Performance

SELECT venue_name,
       AVG(capacity_utilization) AS avg_fill_rate,
       SUM(profit) AS total_profit
FROM performance_summary
GROUP BY venue_name;
6. Tableau Dashboards
Executive Overview Dashboard

KPI cards:

Total Revenue

Total Profit

Average Fill Rate

Total Performances

Monthly Revenue & Profit Trend

Top 5 Cities by Revenue

Operational Performance Dashboard

Revenue by Venue (bar chart)

Capacity Utilization by City (heatmap)

Profit by Show

Financial Breakdown Dashboard

Cost composition (stacked bar)

Revenue vs Cost comparison

Margin by venue

7. Key Metrics
Metric	Definition
Revenue	tickets_sold × avg_ticket_price
Total Cost	venue + staff + marketing
Profit	revenue − total_cost
Fill Rate	tickets_sold / capacity
Margin	profit / revenue
8. Insights Generated (Example Findings)

Major metropolitan cities drive 60%+ of total revenue.

Smaller venues often show higher percentage margins.

Certain venues reach 95%+ average capacity utilization.

Marketing-heavy cities do not always translate to higher profit.

9. What This Project Demonstrates

Practical SQL aggregation skills (GROUP BY, HAVING, JOINs)

KPI definition and metric engineering

Business-oriented dashboard design

Storytelling with data

Ability to simulate a real analytics workflow

10. Future Improvements

Add forecasting model for ticket sales

Introduce seasonality analysis

Compare linear vs logistic regression for sell-out prediction

Add geographic visualization in Tableau

Automate ETL pipeline

11. How to Run

Import dataset into SQL database

Run cleaning and transformation scripts

Create summary views

Connect Tableau to the final summary table

Build dashboards using provided metric definitions
