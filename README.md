# ACME Sales Analysis

This project for ACME, a pre-made meal company, involves processing and integrating large datasets from both their internal database and an external vendor using PostgreSQL, with extensive data validation and documentation. 

## Introduction

This project involves working with large datasets in PostgreSQL through an end-to-end data processing pipeline for ACME, a client that specializes in selling pre-made meals. The workflow is divided into two main parts:

- Internal Data: This section focuses on processing ACME's internal data from their own database, which is stored in CSV files. The data includes sales, products, and customer information related to their pre-made meal offerings. These files are loaded into PostgreSQL tables, where SQL queries are run to explore and analyze the data for insights into ACME's business operations.

- External Data: The second part involves handling data from an external vendor that ACME uses to help sell their meals. This data is stored in a nested JSON format. After parsing the JSON into CSV files, the external data is loaded into PostgreSQL tables and validated against ACME's internal data to ensure consistency and accuracy. SQL queries are then performed on both datasets, including cross-table queries that integrate data from both ACME and the vendor.

The project includes extensive documentation, such as Entity-Relationship Diagrams (ERDs) and data dictionaries for over 14 tables, showcasing a robust approach to data integration and validation within a real-world retail environment.

**The data used in this project is fictional and is intended for demonstration purposes only.**

## Table of Contents

- [Notebooks Introduction](#notebooks-introduction)
- [Notebook 1: Loading](#notebook-1-loading)
- [Notebook 2: Querying Sales](#notebook-2-querying-sales)
- [Notebook 3: Querying Customers](#notebook-3-querying-customers)
- [Notebook 4: Querying Products](#notebook-4-querying-products)
- [Notebook 5: Parsing](#notebook-5-parsing)
- [Notebook 6: Loading](#notebook-6-loading)
- [Notebook 7: Validating](#notebook-7-validating)
- [Notebook 8: Querying](#notebook-8-querying)
- [Conclusion](#conclusion)

## Notebooks Introduction
 
This project is structured into eight Jupyter notebooks that showcase the handling and analysis of both internal and external data from a retail company. The notebooks are divided into two sections based on the data sources:

**Internal Data (Notebooks 1 - 4)**

These notebooks work with the internal retail data stored in the "Data 1" folder, focusing on sales, products, and customers.

- Notebook 1: Drops any existing tables, creates staging tables for the internal data, loads the CSV files into these tables, and verifies that the data has been successfully loaded.

- Notebook 2: Runs SQL queries to analyze sales, including gross sales, sales volumes by product, store, and time.

- Notebook 3: Focuses on customer-related queries, such as the distribution of customers by store, city, and sales metrics.

- Notebook 4: Queries product-related data, including metrics by month, store, and other relevant factors.

**External Data (Notebooks 5 - 8)**

These notebooks deal with external data provided by a third party, stored in the "Data 2" folder.

- Notebook 5: Parses the external data, which is in nested JSON format, into CSVs for further processing.

- Notebook 6: Loads the parsed external data into staging tables in the PostgreSQL database.

- Notebook 7: Validates the external data to ensure it makes sense independently and aligns with the existing internal data by cross-referencing both datasets.

- Notebook 8: Runs SQL queries on the external data, similar to those performed on the internal data, allowing for comparison and analysis across both datasets.

All data and tables with a _1 suffix relate to internal data, while those with a _2 suffix correspond to external data. This structured approach demonstrates how both internal and external datasets can be integrated, validated, and queried within a unified database system.

## Notebook 1: Loading

This notebook sets up the staging tables for internal retail data in a local PostgreSQL database. After dropping any existing tables, new staging tables are designed and created, followed by loading data from CSV files into these tables. The data load is then verified to ensure accuracy. You can click the links below to view the ERD and data dictionary, which help clarify the table structure and data relationships for the project.

[Entity Relationship Diagram 1](Data%201/Entity%20Relationship%20Diagram%201.pdf)


[Data Dictionary 1](Data%201/Data%20Dictionary%201.pdf)

## Notebook 2: Querying Sales

In this notebook, I perform a comprehensive analysis of sales data, starting with overall metrics like gross sales, sales volume, and average order value. These metrics are then broken down for more detailed insights by store, month, day of the week, and combinations such as store and month, as well as store and day of the week. This deeper analysis helps uncover sales patterns and trends across various time periods and locations.

## Notebook 3: Querying Customers

In this notebook, the focus is on analyzing customer data from the internal retail dataset. The queries explore customer distribution and behavior by identifying customers by store and city. Additionally, customer-related metrics such as total sales and purchase quantity are calculated, providing insights into customer activity and engagement across different regions and stores.

## Notebook 4: Querying Products

This notebook focuses on querying the product data to gain insights into product performance. Key metrics include units sold by product, as well as more granular breakdowns such as units sold by product and store, by month, by month and product, and by day of the week and product. These queries help identify sales trends and product demand patterns, offering a detailed view of how different products perform across various dimensions.

## Notebook 5: Parsing

In this notebook, I perform a recursive walk through a nested JSON file provided as external data. The goal is to parse the complex, hierarchical structure of the JSON and transform it into flat CSV files that can be easily loaded into PostgreSQL for further analysis. This step is crucial for preparing the external data for validation and integration with the internal retail data in subsequent notebooks.

## Notebook 6: Loading

In this notebook, I create staging tables in PostgreSQL to load the external data that was parsed into CSV files in the previous step. The tables are designed to accommodate the structure of the external data, ensuring smooth integration with the internal data. You can view the relationships and table information in the linked ERD 2 and data dictionary, which provide detailed documentation of the external data schema.

[Entity Relationship Diagram 2](Data%202/Entity%20Relationship%20Diagram%202.pdf)


[Data Dictionary 2](Data%202/Data%20Dictionary%202.pdf)

## Notebook 7: Validating

In this notebook, I focus on validating the external data loaded into staging tables. First, the external data is validated independently to ensure its integrity. Then, I cross-validate it against the primary and secondary tables from the internal data, checking for consistency and alignment between the two datasets. This step is essential for ensuring that the external data is reliable and compatible with the internal retail data for further analysis.

## Notebook 8: Querying

In this notebook, I run queries on the external data to calculate key metrics such as gross sales, sales volume, average order value (AOV), and customer activity. Additionally, I perform comparative analysis between the external and internal datasets, calculating the external retail gross sales, sales volume, AOV, and customer metrics as a percentage of their internal counterparts. These comparisons help evaluate the contribution of external data relative to internal performance, offering deeper insights into the overall retail business.

## Conclusion

This project demonstrates a complete ELT (Extract, Load, Transform) process for managing and analyzing internal and external retail data using PostgreSQL. While the queries and insights—such as sales metrics, customer behavior, and product performance—are straightforward, the main objective was to ensure the entire data pipeline is organized, clean, and efficient. The data is first extracted from CSV and JSON files, loaded into PostgreSQL staging tables, and then transformed through validation and queries within the database. The project emphasizes the importance of a solid data foundation, not just for analysis but for ensuring that the data is prepared and structured for deeper insights and more complex analysis.