What are your risk areas? Identify and describe them.

- Possible Null values in all the tables
- Duplicate values in the tables
- Inconsistent fields in tables, for example, inthe sales_by_sku table, in the produc_sku column which is character varying, some fields were big integer



QA Process:
Describe your QA process and include the SQL queries used to execute it.
- I performed data assertion: looked for problems in the dataset by checking if there are Null values in the table
- I checked for duplicate rows

Queries
- SELECT s."productsku", s."name"
  FROM "sales_repor"t s
  WHERE s."productsku" IS NULL

  SELECT all."fullVisitorId", COUNT()
  FROM "All_sessions" all
  GROUP BY all."fullVisitorId"
  HAVING COUNT() > 1
