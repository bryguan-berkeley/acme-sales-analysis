# ACME Sales Analysis



## Introduction

/

## Table of Contents

- [Notebooks Introduction](#notebooks-introduction)
- [Notebook 1: Parsing](#notebook-1-scraping)
- [Notebook 2: Loading](#notebook-2-loading)
- [Notebook 3: Validating](#notebook-3-preprocessing)
- [Notebook 4: Analyzing](#notebook-4-analyzing)
- [Results](#results)
- [Conclusion](#conclusion)

## Notebooks Introduction
 
 /

## Notebook 1: Parsing

In this notebook, the goal was to transform raw sales data provided in a nested JSON format into a structured form that could be easily analyzed. The JSON data contained multiple layers of information, encapsulating details about sales, stores, customers, and products within a single file. To enable more focused analysis, I extracted and parsed these nested elements into separate CSV files for each key entity: sales, stores, customers, and products.

The decision to separate the data into distinct CSV files was driven by the need for modularity and clarity. By breaking down the complex JSON structure into manageable components, it becomes easier to query and analyze specific aspects of the dataset. Additionally, separating the data aligns with best practices for relational databases, where tables are typically normalized to reduce redundancy and improve data quality.

Through this parsing process, I established a clear and organized structure for the project, ensuring that each entity—whether it’s a store, a customer, or a product—can be analyzed independently while retaining the relationships between them for more advanced analyses in later stages of the project.

## Notebook 2: Loading

In this notebook, I established a connection to a locally hosted PostgreSQL server to load the parsed sales, stores, customers, and products data into a structured database. The choice to use PostgreSQL was motivated by its reliability, scalability, and strong support for handling relational data, making it an ideal fit for managing our newly parsed datasets.

The process began with the creation of staging tables for each of the key entities: customers, sales, stores, and products. These tables mirror the structure of the CSV files generated in the previous notebook, ensuring that the data is stored in a clean, organized manner. Each table was designed with appropriate data types and constraints to maintain data integrity and prepare for any future transformations or analyses.

After loading the CSV data into the respective staging tables, I ran several queries across the entire dataset to verify that the data was loaded correctly. This process ensures that the database is not only properly populated but also ready for the next stages of the project, where more complex queries and transformations will be applied.

## Notebook 3: Validating

In this notebook, I focused on validating the integrity of the data loaded into the PostgreSQL staging tables. Data validation is a crucial step to ensure that the datasets are accurate and reliable before proceeding with further analysis or modeling. The validation process involved both checking that the data types matched their intended formats and performing logical checks to confirm the accuracy of the data.

Using SQL casting techniques, I confirmed that the columns in each table adhered to the expected data types (e.g., integers, decimals, or strings). This step is vital for avoiding potential errors in later stages of the project, especially when performing complex queries or calculations.

In addition to type validation, I ran several simple yet critical queries to look for entries that violated logical constraints. For example, I confirmed that for each sale, the total was the sum of the subtotal and tax, and that the total also matched the product of price and quantity for each item sold. By addressing any inconsistencies at this stage, I ensured that the data was both logically sound and ready for more advanced analysis.

## Notebook 4: Analyzing

/

## Results

/

## Conclusion

/

