# ACME Sales Analysis

This project parses fictional nested sales data from a JSON object, loads it into a PostgreSQL database, validates its integrity, and performs simple analysis to generate key summary statistics such as total sales and product counts.

## Introduction

This project involves working with fictional nested JSON sales data, which I parsed into CSV files and then used to create several tables in a normalized form within a PostgreSQL database. The focus of the project was to practice the entire data workflow, from extracting and transforming the raw data into structured tables, to validating the integrity of the data, and finally performing simple analysis using SQL. While the analysis itself was basic, the primary goal was to reinforce key skills in parsing, loading, and querying structured data for future use in more complex projects.

## Table of Contents

- [Notebooks Introduction](#notebooks-introduction)
- [Notebook 1: Parsing](#notebook-1-parsing)
- [Notebook 2: Loading](#notebook-2-loading)
- [Notebook 3: Validating](#notebook-3-validating)
- [Notebook 4: Analyzing](#notebook-4-analyzing)
- [Conclusion](#conclusion)

## Notebooks Introduction
 
This project involves processing and analyzing sales data from a nested JSON format. In the first notebook, the raw data is parsed into four separate CSVs—customers, sales, stores, and products—to facilitate easier handling. The second notebook establishes a connection to a locally hosted PostgreSQL database, where the CSV data is loaded into staging tables and verified through basic queries. In the third notebook, data validation is performed by checking data types and running logic checks, such as confirming that total sales amounts align with subtotals, taxes, and quantities. Finally, the fourth notebook conducts simple analysis, calculating summary statistics like total sales, product counts, and average product count per sale, offering an initial overview of the dataset.

## Notebook 1: Parsing

In this notebook, the goal was to transform raw sales data provided in a nested JSON format into a structured form that could be easily analyzed. The JSON data contained multiple layers of information, encapsulating details about sales, stores, customers, and products within a single file. I extracted and parsed these nested elements into separate CSV files for each key entity: sales, stores, customers, and products. By breaking down the complex JSON structure into manageable components, it becomes easier to query and analyze specific aspects of the dataset. Additionally, separating the data aligns with best practices for relational databases, where tables are typically normalized to reduce redundancy and improve data quality.

## Notebook 2: Loading

In this notebook, I established a connection to a locally hosted PostgreSQL server to load the parsed sales, stores, customers, and products data into a structured database. The process began with the creation of staging tables for each of the key entities: customers, sales, stores, and products. These tables mirror the structure of the CSV files generated in the previous notebook, ensuring that the data is stored in a clean, organized manner. Each table was designed with appropriate data types and constraints to maintain data integrity. After loading the CSV data into the respective staging tables, I ran several queries across the entire dataset to verify that the data was loaded correctly. 

## Notebook 3: Validating

In this notebook, I focused on validating the integrity of the data loaded into the PostgreSQL staging tables. The validation process involved both checking that the data types matched their intended formats and performing logical checks to confirm the accuracy of the data. Using SQL casting techniques, I confirmed that the columns in each table adhered to the expected data types (e.g., integers, decimals, or strings). In addition to type validation, I ran several simple yet critical queries to look for entries that violated logical constraints. For example, I confirmed that for each sale, the total was the sum of the subtotal and tax, and that the total also matched the product of price and quantity for each item sold.

## Notebook 4: Analyzing

In this notebook, I performed a simple analysis to get an initial understanding of the sales data. The goal was to generate summary statistics that provide a high-level overview of the key metrics. I started by calculating total sales in both dollars and quantity, giving a sense of the dataset’s overall performance. I then analyzed product data, calculating the total number of each product sold to identify top-selling items. Additionally, I computed the average product count per sale to understand purchasing patterns. These statistics offer early insights and set the stage for deeper analyses and more complex queries in future stages.

## Conclusion

This project was a straightforward exercise designed less around the complexity of the analysis and more as a way to practice key skills in handling data workflows. The primary focus was on parsing nested JSON data into separate CSVs, loading the data into a locally hosted PostgreSQL database, validating the integrity of the data, and performing simple analysis using SQL. By working through these steps, I gained hands-on experience in managing a local database, handling structured and unstructured data, and applying basic validation and querying techniques.

