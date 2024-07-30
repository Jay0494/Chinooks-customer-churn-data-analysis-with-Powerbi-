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
![Customer churn 2](https://github.com/user-attachments/assets/2f52d17d-a0a4-4829-8b98-b1e53ce0670c)

### **Analysis**

1. **Top Customers:**
   - The top 5 customers are contributing a significant portion of revenue, but the total contribution is relatively low, suggesting a limited number of high-value customers. 

2. **Customer Churn:**
   - There are 28 customers at risk of churn, which is a notable proportion compared to the 31 customers who are not at risk. This indicates that maintaining current customers is critical for stability.

3. **Sales by Country:**
   - **USA** is the highest revenue generator, contributing $85.14. 
   - **Canada** follows with $72.27.
   - **France** and **Brazil** are also notable contributors but with significantly lower amounts.

4. **Churn by Country:**
   - Churn risk is spread across multiple countries, with **Canada**, **Germany**, and **USA** having the highest number of at-risk clients (4 each).
   - Other countries have fewer clients at risk, with a mix of countries having only 1 client at risk.

5. **Clients by Country:**
   - The USA has the highest number of clients (13), followed by Canada (8).
   - Other countries have significantly fewer clients, with some having just one.

### **Recommendations**

1. **Focus on Retention Strategies:**
   - **High-Risk Clients:** Since there is a considerable number of clients at risk of churn, implement targeted retention strategies. Consider offering personalized incentives or loyalty programs to retain these customers.
   - **Top Customers:** Engage more with top customers (e.g., Helena Holy, Diego Gutierrez) to ensure their satisfaction and prevent churn.

2. **Market Expansion and Focus:**
   - **High Revenue Countries:** Given that the USA and Canada are major revenue sources, consider focusing marketing and sales efforts in these regions. Tailor offers and promotions to these markets.
   - **Underperforming Markets:** Explore why countries like Germany, Brazil, and France have lower sales and fewer clients. Investigate market conditions and adjust strategies accordingly.

3. **Address Churn by Country:**
   - **High Churn Countries:** For countries with higher churn rates (Canada, Germany, USA), analyze specific factors contributing to churn and address them. This may include improving customer service or customizing offerings.
   - **Low Churn Countries:** For countries with lower churn rates, continue to nurture relationships and consider expanding these markets.

4. **Customer Segmentation:**
   - **Segment Customers:** Implement segmentation to better understand the needs of different customer groups. Tailor marketing and sales approaches based on these segments to enhance retention and acquisition.

5. **Monitor and Evaluate:**
   - **Track Performance:** Regularly track performance metrics for both sales and churn rates. Adjust strategies based on performance data to ensure continuous improvement.

### **Next Steps**

1. **Detailed Churn Analysis:**
   - Conduct a deeper analysis to understand the reasons behind customer churn. Surveys or feedback from at-risk customers can provide valuable insights.

2. **Targeted Marketing Campaigns:**
   - Develop and launch targeted marketing campaigns aimed at retaining high-risk customers and boosting sales in high-potential markets.

3. **Customer Engagement Initiatives:**
   - Enhance customer engagement through personalized communication, loyalty programs, and exclusive offers to reduce churn and increase satisfaction.

4. **Expand Market Research:**
   - Conduct market research to identify opportunities for growth in underperforming countries and adapt strategies based on local conditions.

5. **Regular Review and Adaptation:**
   - Set up a regular review process to assess the effectiveness of implemented strategies and make necessary adjustments based on new data and feedback.
