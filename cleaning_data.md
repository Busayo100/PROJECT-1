What issues will you address by cleaning the data?
* remove Null values in the 'Ratio' column of the sales_report table
* View and remove duplicates in the sales_report table
* View and remove duplicates in the "All_sessions" table
*Assign primary and foreign keys


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

- To assign primary key in the sales_report table
  
ALTER TABLE "sales_report" 
ADD PRIMARY KEY ("Productsku")

- To view duplicates in the All_sessions table

SELECT "FullVisitorId", COUNT ("FullVisitorId")
FROM "All_Sessions"
GROUP BY "FullVisitorId"
HAVING COUNT ("FullVisitorId") > 1
ORDER BY "FullVisitorId"

- To remove duplicates in the All_sessions table

DELETE FROM "All_Sessions" a
USING "All_Sessions" b
WHERE a."FullVisitorId" < b."FullVisitorId"
AND a."ChannelGrouping" = b."ChannelGrouping"

- To view duplicates in the analytics table
SELECT "VisitId", COUNT ("VisitId")
FROM "Analytics"
GROUP BY "VisitId"
HAVING COUNT ("VisitId") > 1
ORDER BY "VisitId"
