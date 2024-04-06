# Nofrills_Price_Comparison

Nofrills Price Comparison
This repository contains a SQL query for comparing product prices between two backup datasets from Nofrills, specifically dated August 25, 2023, and August 18, 2023. The query calculates the price difference for each product and sorts the results in descending order based on the price difference.

Overview
The provided SQL query retrieves data from the Backup_Nofrills_08_25_2023 and Backup_Nofrills_08_18_2023 tables and compares the prices of products with the same product_id and zip. It calculates the price difference between the two datasets for each product and sorts the results based on the price difference in descending order.

SQL Query
_**SELECT DISTINCT
    a.product_id,
    CAST(a.eprice AS FLOAT),
    CAST(b.eprice AS FLOAT),
    (CAST(a.eprice AS FLOAT) - CAST(b.eprice AS FLOAT)) AS diff
FROM Backup_Nofrills_08_25_2023 AS a
LEFT JOIN Backup_Nofrills_08_18_2023 AS b
ON a.product_id = b.product_id AND a.zip = b.zip 
WHERE a.zip = 'E2M 4X5'
ORDER BY diff DESC;**_


Description
This SQL query facilitates the comparison of product prices between two backup datasets from Nofrills, focusing on a specific ZIP code ('E2M 4X5'). By comparing prices for products with identical IDs and ZIP codes but different dates, users can gain insights into any changes in pricing over time.

How to Use
Clone this repository to your local machine.
Execute the provided SQL query in your SQL Server environment, ensuring that you have access to the Backup_Nofrills_08_25_2023 and Backup_Nofrills_08_18_2023 tables.
Review the output to understand the price differences between the two datasets for products in the specified ZIP code.
Utilize the insights gained from the analysis to make informed decisions related to pricing strategies and product management.
