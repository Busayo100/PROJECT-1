What issues will you address by cleaning the data?
* remove Null values in the 'Ratio' column of the sales_report table
* View and remove duplicates in the "Name" column of sales_report table


Queries:
Below, provide the SQL queries you used to clean your data.

- To remove null values in the 'Ratio' column, I used the query below:
SELECT COALESCE ("Ratio", 0)
FROM "sales_report"

-To view the duplicates in the 'Name' column of the sales_report table< I used the query below: 
SELECT "Name", COUNT ("Name")
FROM "sales_report"
GROUP BY "Name"
HAVING COUNT ("Name") > 1
ORDER BY "Name"

- To remove the duplicate rows
DELETE FROM "sales_report" a
USING "sales_report" b
WHERE a."Productsku" < b."Productsku"
AND a."Name" = b."Name"
