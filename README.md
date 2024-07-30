# Customer churn with Powerbi 
# Introduction 
In today’s highly competitive media landscape, Chinooks, a prominent player in the industry, faces the dual challenge of sustaining revenue growth while ensuring high levels of customer retention and engagement. This project provides a comprehensive analysis of Chinooks’ customer base, sales performance across different regions, and potential risks of customer churn. The goal is to leverage these insights to formulate actionable recommendations that will bolster Chinooks’ market position and drive sustained success.
Our analysis reveals critical insights into Chinooks’ customer dynamics, highlighting the concentration of revenue among a few top customers and a notable risk of customer churn. Furthermore, our examination of sales performance by country uncovers both high-performing markets and regions with substantial growth potential.
Based on these insights, we offer strategic recommendations aimed at enhancing customer retention, addressing churn risks, and optimizing sales strategies across various markets. By implementing these recommendations, Chinooks can better align its strategies with market demands, improve customer satisfaction, and ultimately strengthen its competitive edge in the media industry.
## Business Question 
The objective of this project is to find the customers who are at risk of churning i.e the customer who have not made any sales 6 months from 12/31/2013
## Tools 
- PowerBi
- Power Query 
- DAX

## Methodology  
The analysis for Chinooks was conducted using Microsoft Power BI, a robust business analytics tool that enables the integration, visualization, and exploration of data. The methodology for processing the data is detailed below, reflecting a structured approach to ensure comprehensive and actionable insights.

#### 1. **Data Collection and Integration**

- **Data Sources:**
  - Collected data from chinook database.
  - Data was imported into Power BI from chinooks database.

- **Data Integration:**
  - Utilized Power Query Editor to clean, transform, and merge data, ensuring consistency and accuracy across different data points.
- **Data Cleaning:**
  - Addressed missing values and inconsistencies using Power BI's data transformation features.
  - I also addressed the wrong date datatype.
  - Merged the customer firstname and last name.

- **Data Preparation:**
  - Created calculated columns and measures to facilitate detailed analysis.
  - Standardized data formats and units for uniformity across the dataset.

#### 3. **Data Modeling**
- **Building Relationships:**
  - Established relationships between the customer and invoice tables using Power BI’s data modeling features.
  - Developed a relational model to connect customer information and sales data

- **Creating churn column and Date table:**
  - I created a column to determine the last sales date of our customers.
  - I created a churn column that determined which customer was at risk of churn using this DAX;
 ```sql
Churn =
-- create the last sales month and year 
VAR lastyearsales = MAX(Invoice[Date])
-- create the criteria for determing the customers at risk of churn
VAR lastsales = EDATE(lastsales, -6)
-- return the result
RETURN
 Customer[last purchase] >= lastsales
```
![customer churn data for chinooks ](https://github.com/user-attachments/assets/ece41ad5-dfdb-41e1-9e90-8e3d39b2ac33)

## Insights

1. **Top Customers:**
   - The top 5 customers have contributions that are relatively close in value, indicating a high level of revenue concentration among a few individuals.
   
2. **Customer Churn:**
   - There are 28 customers at risk of churn compared to 31 customers who are still active and not at risk. This suggests a potential issue with customer satisfaction or engagement.

3. **Total Sales by Country:**
   - The USA is the largest contributor to sales, followed by Canada, France, and Brazil. Sales figures in many European countries are lower, with a significant drop from the USA to other regions.
   - Countries such as Norway, Austria, Hungary, and Poland have very minimal sales figures, indicating potential areas for growth or reevaluation.

### Recommendations for Churning Customers

1. **Analyze Churn Data:**
   - **Identify Patterns:** Examine the churn list to identify common characteristics or behaviors among these customers. Look for patterns such as customer demographics, purchase history, or interaction frequency.
   - **Determine Causes:** Understand why these customers are churning. Possible reasons could include dissatisfaction with the product/service, pricing issues, or competitive offerings.

2. **Develop Targeted Retention Strategies:**
   - **Personalized Outreach:** Contact churning customers directly through personalized communication. Address their specific concerns and offer solutions or incentives to retain them.
   - **Tailored Offers:** Create customized offers or discounts to entice these customers to stay. Make sure the offers are relevant to their needs and preferences.

3. **Improve Customer Experience:**
   - **Feedback Collection:** Solicit feedback from churning customers to understand their reasons for leaving. Use this feedback to make improvements in your products, services, or customer support.
   - **Enhance Service:** Review and improve customer service practices to address any common issues raised by churning customers. Ensure that the customer experience is consistently positive.

4. **Implement Churn Prevention Programs:**
   - **Loyalty Programs:** Introduce or enhance loyalty programs to reward long-term customers and incentivize continued engagement.
   - **Engagement Initiatives:** Increase engagement with churning customers through targeted content, follow-up communications, and regular check-ins to maintain their interest.

5. **Monitor and Adjust Strategies:**
   - **Track Effectiveness:** Monitor the effectiveness of your retention strategies. Track metrics such as re-engagement rates and customer satisfaction levels.
   - **Refine Approaches:** Continuously refine and adjust your retention efforts based on the outcomes and feedback from your initiatives.

### Next Steps

1. **Data Analysis:**
   - Conduct a detailed analysis of the churn list to identify key trends and root causes of churn.
   - Segment churning customers based on common attributes to tailor retention efforts more effectively.

2. **Action Plan:**
   - Develop a comprehensive action plan that includes personalized outreach, tailored offers, and improved customer experience strategies.
   - Assign responsibilities and timelines for implementing these strategies.

3. **Feedback and Improvement:**
   - Create a system for collecting and analyzing feedback from churning customers.
   - Use this feedback to inform product or service improvements.

4. **Performance Tracking:**
   - Set up mechanisms to track the impact of retention efforts on churn rates and customer satisfaction.
   - Regularly review the performance of retention strategies and make adjustments as necessary.
