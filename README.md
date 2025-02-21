In Power BI, you can calculate the sum of cost by year using DAX (Data Analysis Expressions) and visualizations. Below are different methods to achieve this:

Method 1: Using a DAX Measure
If your dataset has a column named Cost and a date column like Date, you can create a DAX measure to sum the cost by year:

DAX
Copy
Edit
Total Cost by Year = 
CALCULATE(
    SUM('Table'[Cost]), 
    YEAR('Table'[Date])
)
This measure calculates the total cost for each year dynamically when used in a visualization.

Method 2: Using a DAX Calculated Column
If you prefer to create a calculated column for grouping:

DAX
Copy
Edit
Year = YEAR('Table'[Date])
Then, you can create a simple SUM measure:

DAX
Copy
Edit
Total Cost = SUM('Table'[Cost])
Now, you can add Year as a field in your visualizations and use Total Cost to display the sum.

Method 3: Using Power BI Visuals
Create a Table or Matrix Visual:

Drag the Date column to the Values pane.
Change the aggregation to Year using the "Date Hierarchy."
Add the Cost column and set it to Sum.
Create a Bar or Line Chart:

Add Year (created using DAX or hierarchy) to the X-axis.
Add Cost as the Y-axis.
Power BI will automatically aggregate the cost by year.
Bonus: Filtering by Year
To allow users to filter data by year, you can:

Add a Year Slicer by dragging Year into a slicer visual.
Use a Dropdown or Timeline Slicer to filter based on year.
