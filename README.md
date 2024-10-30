# 42-code-challenge-_-uma
Problem Explanation
This task involves sorting a dataset in a hierarchical manner, specifically sorting by net_sales_units in descending order. The key requirements are:
1.	Hierarchical Sorting: Sort the data such that rows containing $total always appear at the top of each grouping level, regardless of their metric value.
2.	Descending Metric Sorting: All other rows within each group should be sorted in descending order based on the net_sales_units column.
3.	Flexible Columns: The solution should be adaptable to datasets with varying numbers of property columns and metric columns.
4.	File Format: The dataset is provided in a pipe (|)-delimited format, which should be retained in the output.

Solution Approach
These steps will be followed to solve this problem.
1.	Parse the Data: Read the dataset from the provided file and identify the columns.
2.	Identify Property and Metric Columns:
o	Property columns follow the naming convention property0, property1, etc., and represent the hierarchy in the data.
o	Metric columns, such as net_sales_units, are the ones we will sort by.
3.	Define Sorting Rules:
o	For each level, rows with $total in a property column should always be at the top.
o	Non-$total rows should be sorted based on the specified metric (net_sales_units) in descending order.
4.	Output the Data: After sorting, the data should be written back to a file in the same pipe-delimited format, making it easy for others to open in Excel or other spreadsheet software
We need to run this script by saving the code with file name called hierarchical_sort.py
Then need to place the input file data-big-input.txt in same directory, later on need to run the script.
python hierarchical_sort.py data-big-input.txt net_sales_units data-big-output.txt

it will create an output file data-big-output.txt with the sorted data,

Testing and Verification
After implementing the code, I ran tests with various datasets to verify:
•	$total rows consistently appear at the top of each hierarchical level.
•	Non-total rows are in strict descending order based on the metric value.
•	The output maintains the original data format (pipe-delimited), ensuring seamless import into tools like Excel.
I have tried handling the Edge cases as well by following
1.	If there are rows missing a value in a property or metric column, the code still gracefully processes the row.
2.	The sort logic should handles negative values, sorting them correctly from highest to lowest.
3.	The solution allows users to specify any metric column (like net_sales or net_sales_units) to sort by, depending on their reporting needs.
