# Touring-Show-Business-Analysis
## Providing a business insights based on five months worth of data from a fictional touring theater production company.
### Executive Summary
This project analyzes the operational and financial performance of a fictional touring theatre production company. Using SQL for cleaning and aggregating, and Tableau for visualizations, the objective is to simulate a real-world business intelligence workflow.

This project answers questions such as: 
- Which venues/productions generage the highest revenue?
- What is our cost structure per venue?
- How does performance vary month-over-month?
- What is the impact of marketing spend on revenue?

## Project Workflow
1. Clean and transform raw operational data using SQL
2. Build aggregated views for reporting
3. Connect structured outputs to Tableau
4. Design executive-level dashboards focused on revenue, attendance, cost, and profitability
5. The project mirrors a real analytics role in an entertainment or live-events company.

## Key Insights
- One particular venue and one particular production far outperform the others in regards to revenue and profit. Emphasis should be put on touring this production more and performing more in this particular venue.
- Revenue correlates more strongly with production title and venue than marketing spend. Marketing spend should not be increased, and even decreased for larger venues which seem to sell well regardless.

## Next Steps
- Most popular program was a designated "Classical Revival" genre in the Shows table. Next most popular was a "Musical Theater" genre production. Management should consider investing in more shows of these genres.

## Limitations
- Operational costs, i.e. performers' and staff salaries throughout the performance season, are missing. This would give a more complete understanding of the true cost of each tour, and a more accurate profit value.
- Certain ticket sales information was missing and had to be zeroed out for calculations, leading to under-representation of revenue for certain productions and venues.
