
# Maven Market Sales-Dashboard

### Dashboard Video Link : https://www.loom.com/share/234a9ba06e3a47d091ec90aa95d14e63?sid=b226bd86-3db3-489d-86ea-cc3f5c63bce3

## Project Summary

This time I'll be working with data from Maven Market, a multi-national grocery chain with locations in Canada, Mexico and the United States.

Just like the AdventureWorks project, I'll work through the entire business intelligence workflow: connecting and shaping the data, building a relational model, adding calculated fields, and designing an interactive report.


The Maven Market Sales Dashboard offers insights into sales, customer trends, and product profitability. It tracks revenue, profit, return rate, and top customers across three reports. Built with Power BI, it uses DAX, Power Query, and interactive features for a seamless experience.


### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in Products table under low fat column null values were present, so replaced null values with 0.
- Step 5 : Added new columns in Stores table using Power Query merged column function to concat City,State,Country to create Full Address.
- Step 6 : Modify global settings and disabled automatic relationship detection after loading data, deactivate time intellegence and in regional settings selected English US.
- Step 7 : Created Three Different reports for Topline Performance, Product Brand and Customers for detailed view and insights.
- Step 8 : Used Card, line chart, matrix, Map, slicers, guage, horizontal bar charts, area charts and filters for data visualizations.
- Step 9 : Three card visuals were added to the Topline Performance canvas, representing current month transactions, Profit and Returns.
- Step 10 : A column chart added to showcase weekly revenue tranding, utilized guage chart to represent total revenue vs Target.

    Matrix view to showcase Top 30 Products brand with comparision of  Total transactions,profit,profit margin and return rate.

    Used map to represent Stores based on total transactions in different states and countries. 
- Step 11 : For Product Brand report utilized three guage charts to represent monthly transactions, monthly profit and monthly returns in comparision with Monthly Target for each matrics. 
    
    Created matrix to show top 25 Brands with highest transactions 

    Created clusterd column and line chart to showcase top 10 profitable brand and their return rates.

    Used funnel chart to represent bottom 10 profitable brands

    Used horizontal bar chart to showcase top 10 brands with less return rates.
- Step 12 : In Customer report page, used line chart to represent weekly revenue Per Customer trends over the time.
    Also added, donut chart to represent Profit by Occupation and pie chart to showcase Profit by Countries.
    Used Matrix view to represent data of Top 100 Customers by revenue per customers and quantity sold.
    Slicer Added to filter data by Years, to represent Top 5 and bottom 5 Customers by profit. 
    
- Step 13 : Page Navigation and clear filter button added for user friendly experience.
- Step 14 : Multiple Measures were created in order to get deeper insights from data for examples. Total Returns, Total revenue, Total cost, Total profits, YTD revenue, Weekends transactions, Total transactions, revenue per customers, Revenue target, return rate, quantity sold, quantity returned, profit margin, last month revenue, last month return, last month profit, 60 Days revenue, return rate, etc.  

for creating new measure for Weekend transactions DAX expression was written;
       
       Weekend Transactions = SUMX(FILTER('Calendar','Calendar'[Weekend] = "Y"),[Total Transactions])

        
- Step 15 : New measure was created to find 60-Days Revenue.

Following DAX expression was written for the same,
        
        60-Day Revenue = CALCULATE(
    [Total Revenue],
    DATESINPERIOD(
        'Calendar'[date],MAX('Calendar'[date]),-60,DAY)
        )
        

        
 - Step 16 : New measure was created to find Last month revenue,
 
 Following DAX expression was written to find the same,
 
         Last Month Revenue = CALCULATE(
    [Total Revenue],PREVIOUSMONTH('Calendar'[date]))
 
 
 - Step 17 : New measure was created to calculate last Month Profit.
 
 Following DAX expression was written to find the same,
 
         Last Month Profit = CALCULATE([Total Profit], PREVIOUSMONTH('Calendar'[date]))
    
 Step 18 : New Calculated column was created for year since remodel in store table.
    Following DAX expression was written to find the same,


    Years_Since_Remodel = ABS(DATEDIFF(TODAY(),Stores[last_remodel_date],YEAR))

  ![Image](https://github.com/user-attachments/assets/8e8146c9-3716-4b0c-a75e-df05b59e01a1) 
 
 - Step 19 : The report was then published to Power BI Service.
 

# Snapshot of Topline Performance Dashboard 

![Image](https://github.com/user-attachments/assets/7e2be45e-9ea8-4842-8715-bc1d1efe3287)

# Snapshot Product Brand Report

 ![Image](https://github.com/user-attachments/assets/68f60ebb-0e71-4ed5-a302-ef49ca7ed871)

 # Snapshot Customer Report

 ![Image](https://github.com/user-attachments/assets/51d442ba-b735-4be5-81a6-8bc0e23ce6c5)

# Insights

Three pages report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### [1] Topline Performance Dashbord Key Insights:

   Current Month Transaction Was: 18,325

   Current Month Profit Was: $71,682

   Current Month Return Was: 496

    Top Product Brand by Total Transaction was : Tell Tale with 5112 transactions.
    Top Product Brand by Total Profit was : Tell Tale with $19,982 Profit.
    Top Product Brand by Profit Margin was : Quick with 68.48% Profit Margin.
    Top Product Brand by Return Rate was : Tip Top with 1.64% Return Rate.

   Maximum Transactions are from USA with 93,986 transactions.
           
    
  ### [2] Top 3 Product:
  
      a) Highest Transaction is from: Hermanos with 8,071 transactions. 
      b) Top Brand with less return rate was: James bay with Return rate 0.27%
      c) Top Brand with least profit was: King with only $234 Profit.
     

Most Ordered Product Type: Tires and Tube

Most Returend Product Type: Shorts
        
 ### [3] Customer insights
 
    1. Revenue Per Customer: $172
    2. Unique Customers: 10.3K
    3. Top Customer: Ida Rodriguez with 1,021 quantity sold and $2.23K Revenue.


 
 
 ## Thank you for reviewing the report!!!
