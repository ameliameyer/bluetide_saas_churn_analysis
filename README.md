# SaaS Churn Dashboard
## Overview
This project analyzes customer churn for a SaaS business, with a focus on how churn impacts revenue, which plans are most affected, and where early warning signals appear.

The goal was to move beyond just “churn rate” and understand:
- What is driving revenue loss
- Where growth is offsetting churn
- Whether product usage or support activity signals churn risk

## Dashboard
A PDF version of the dashboard is available here: `/workbook/dashboard.pdf`

## Key Metrics
1. Churn % (MoM): ↓ 3.9%
2. Revenue Lost: $2,475
3. Net Growth: $18,460

## Analysis Breakdown
1. Churn by Plan Type
- Compares churn rates across subscription tiers (Enterprise, Free, Pro, Team)
- Highlights which segments are most volatile and where retention efforts should focus

2. Revenue Lost vs Gained
- Combines revenue loss (churn) with revenue gained (new subscriptions)
- Shows how acquisition offsets churn and where net growth is coming from

3. Geographic Churn
- State-level churn visualization
- Identifies regions with concentrated churn risk

4. Product Usage Trends
- Tracks average usage metrics per company:
    - Active users
    - Commits
    - Deployments
    - Pipelines
- Used to identify potential early warning signs of churn

5. Support Ticket Trends
- Monitors average support tickets per company over time
- Helps detect spikes that may correlate with churn risk

# Data & Modeling
- Data was simulated to represent a SaaS company with subscriptions, product usage, and support activity
- SQL views were created to calculate KPIs and aggregate metrics:
    - vw_kpis
    - vw_product_usage_monthly
    - vw_support_tickets_monthly

## Tools Used
- Python (Kaggle) - data generation and preprocessing
- SQL (Snowflake) – data modeling and KPI calculations
- Tableau – dashboard creation and visualization

## Insights
- Churn is decreasing, but not solved. Month-over-month churn dropped by 3.9%, which is a positive signal. However, churn is still present across all plan types, meaning retention improvements are incremental rather than structural.
- Revenue growth is outpacing churn losses. Despite $2,475 in lost revenue, the business generated $18,460 in net growth, indicating that acquisition is currently strong enough to offset churn. This suggests a growth-driven model, but one that still leaks revenue.
- Free and Pro plans show higher churn concentration. Churn rates for lower-tier plans (Free: 25.20%, Pro: 21.37%) are significantly higher than other tiers, suggesting weaker engagement or lower switching costs. These segments represent the largest opportunity for retention improvements.
- Enterprise and Team plans are more stable but still exposed. Even higher-value plans show churn (Enterprise: 18.18%, Team: 15.83%), which is more concerning due to their higher revenue impact. This indicates that churn is not limited to low-value users.
- Revenue trends suggest inconsistency in acquisition vs retention. Fluctuations in revenue gained vs lost across months indicate that growth is not steady. Spikes in revenue gained are offset by periods of higher churn, pointing to a lack of balance between acquisition and retention strategies.
- Churn risk is geographically concentrated. The state-level map shows clusters of higher churn, suggesting that external factors (market differences, customer segments, or regional support quality) may be influencing retention.

## Notes
- Dashboard is exported as a PDF due to Tableau Personal Edition limitations
- All data is synthetic and created for analysis purposes
