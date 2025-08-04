SALES DASHBOARD

Problem Statement :

The Sales Dashboard is designed to help businesses analyze regional sales trends, product performance, and profitability. By visualizing critical sales metrics, the dashboard enables better strategic decisions, improves forecasting, and identifies top-performing products and regions.

Key outcomes include:

1.Tracking total sales, profit margins, and quantity sold

2.Understanding time-based trends in revenue

3.Monitoring performance by region, category, and product

Steps Followed :

1.Data Import: Loaded raw sales and master datasets into Power BI (via CSV or SQL source).

2.Power Query Editor: Performed data cleaning and transformation:

*Handled null values

*Standardized category names

*Merged sales data with product and regional info

3.Data Modeling :

*Established relationships between:

*Sales ↔ Products

*Sales ↔ Regions

4.Calculated Columns and Measures :

*Profit = SalesAmount - Cost

*Profit Margin = DIVIDE(Profit, SalesAmount)

*Total Sales, Sales by Region, etc.

5.Visuals Used :

*Cards for KPIs (Total Sales, Total Profit, etc.)

*Bar/Column Charts for top products and region-wise analysis

*Line Chart for monthly/quarterly trends

*Slicers for dynamic filtering (Category, Region, Time)

6.Dashboard Design :

Applied consistent theme

Added company logo and background image

Used tooltips and bookmarks for better interactivity

7.Publishing: Published the dashboard to Power BI Service for sharing and access control.

🧮 DAX Measures Used

Total Sales = SUM(Sales[SalesAmount])

Total Profit = SUM(Sales[SalesAmount]) - SUM(Sales[Cost])

Profit Margin = DIVIDE([Total Profit], [Total Sales])

Sales Qty = SUM(Sales[Quantity])

🗃️ Sample Data Schema

Products Table CREATE TABLE Products ( ProductID INT PRIMARY KEY, ProductName VARCHAR(100), Category VARCHAR(50), Cost DECIMAL(10,2) );

Regions Table CREATE TABLE Regions ( RegionID INT PRIMARY KEY, RegionName VARCHAR(100) );

Sales Table CREATE TABLE Sales ( SaleID INT PRIMARY KEY, ProductID INT, RegionID INT, SaleDate DATE, Quantity INT, SalesAmount DECIMAL(12,2), FOREIGN KEY (ProductID) REFERENCES Products(ProductID), FOREIGN KEY (RegionID) REFERENCES Regions(RegionID) );
