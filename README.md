# Databricks Medallion Architecture Pipeline

An end-to-end data engineering project on Databricks that ingests raw [type of data, e.g. sales/retail/taxi trip] data and transforms it through Bronze, Silver, and Gold layers using PySpark and Delta Lake.

## Architecture

Raw Data (CSV) → Bronze (raw ingestion) → Silver (cleaned, validated) → Gold (business-ready aggregates)

| Layer | Purpose | Key operations |
|-------|---------|----------------|
| Bronze | Land raw data as-is in Delta tables | [e.g. ingestion, schema definition, ingestion timestamp] |
| Silver | Clean and standardize | [e.g. dedupe, null handling, type casting, joins] |
| Gold | Business-level tables for analytics | [e.g. aggregations, reporting tables] |

## Tech Stack

- Databricks (Community/Free Edition or workspace used)
- Apache Spark / PySpark
- Delta Lake
- SQL
- [Unity Catalog / DBFS / Azure / AWS, whichever applies]

## Repository Structure

├── Bronze Notebooks/        # Raw data ingestion
├── Silver Notebooks/        # Cleaning and transformation
├── Gold Notebooks/          # Aggregations and business tables
├── DataSets/                # Source data files
└── Create Tables.dbquery.ipynb   # Table/schema creation

## Dataset

[Describe the data: source, number of rows, key columns.]

## How to Run

1. Import the notebooks into your Databricks workspace.
2. Upload the files from `DataSets/` to [DBFS / a volume / cloud storage].
3. Run `Create Tables.dbquery.ipynb` to create the schemas and tables.
4. Run the notebooks in order: Bronze → Silver → Gold.


## Future Improvements

- Orchestrate with Databricks Workflows / Jobs
- Add incremental loading with Auto Loader

## Author

[Rohit Khosla] [https://www.linkedin.com/in/rohit-khosla/]

