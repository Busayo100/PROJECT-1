Question 1: What is the product with the highest sentimental value?

SQL Queries: SELECT products."name" 
             FROM products
             WHERE products."sentimentScore" = (SELECT MAX(products."sentimentScore") FROM products)

Answer: "USB wired soundbar - in store only"

Question 2: How many visitors are not socially engaged

SQL Queries:SELECT DISTINCT(analytics."visitId") AS Distinct_visitId 
            FROM analytics 
            WHERE analytics."socialEngagementType" = 'Not Socially Engaged'
            GROUP BY "visitId"

Answer:  148642 rows


Question 3: 

SQL Queries:

Answer:






