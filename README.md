# etl_factory

## 🚧 Work in Progress 🚧

> **Note:** This project is currently under active development. Some features may be incomplete, and the API may change in future versions.

## Overview

`etl_factory` is a versatile ETL (Extract, Transform, Load) library designed to streamline data processing across various engines, including PySpark, pandas, and Polars. It supports a wide range of data formats, such as CSV, JSON, Parquet, ORC, Delta Lake, and Apache Iceberg, providing a unified interface for data ingestion, transformation, and validation.

## Features

- **Multi-Engine Support:** Seamlessly switch between PySpark, pandas, and Polars for your ETL tasks.
- **Wide Format Compatibility:** Read and write data in CSV, JSON, Parquet, ORC, Delta Lake, and Apache Iceberg formats.
- **Basic ETL Operations:** Perform essential transformations such as filtering, joining, and aggregating data.
- **Data Validation:** Ensure data quality with built-in schema validation and missing value checks.
- **Delta Lake & Apache Iceberg Integration:** Native support for advanced data formats used in big data environments.

## Installation

### Prerequisites

Before installing `etl_factory`, ensure that you have the following prerequisites:

- Python 3.7+
- Java 8 or later (required for PySpark)
- PySpark
- Delta Lake
- Apache Iceberg

### Install Dependencies

Use the following commands to install the necessary dependencies:

```bash
pip install pyspark
pip install delta-spark
pip install iceberg-spark3
Clone the Repository
If you want to work with the latest version of the project, clone the repository:

bash
Copy code
git clone https://github.com/yourusername/etl_factory.git
cd etl_factory
Install the Package
After cloning the repository, you can install the package locally:

bash
Copy code
pip install .
Usage
PySpark Support
The etl_factory.pyspark_support module provides functions for reading, writing, transforming, and validating data using PySpark.

1. Reading Data
python
Copy code
from etl_factory.pyspark_support import read_data

df = read_data("csv", "/path/to/file.csv")
df.show()
Supported formats:

"csv"
"json"
"parquet"
"orc"
"delta"
"iceberg"
2. Writing Data
python
Copy code
from etl_factory.pyspark_support import write_data

write_data(df, "parquet", "/path/to/output")
3. Transforming Data
python
Copy code
from etl_factory.pyspark_support import filter_data, select_columns, join_data, aggregate_data

# Filter Data
filtered_df = filter_data(df, "Age > 30")

# Select Columns
selected_df = select_columns(df, ["Name"])

# Join DataFrames
joined_df = join_data(df1, df2, "Name")

# Aggregate Data
aggregated_df = aggregate_data(df, ["Age"], {"Age": "avg"})
4. Validating Data
python
Copy code
from etl_factory.pyspark_support import validate_schema, check_missing_values

# Validate Schema
is_valid_schema = validate_schema(df, df.schema)

# Check Missing Values
missing_values = check_missing_values(df, 0)
Delta Lake and Iceberg Specific Operations
Delta Lake
python
Copy code
from etl_factory.pyspark_support import read_delta_with_custom_options, write_delta_with_custom_options

# Reading Delta Lake data
delta_df = read_delta_with_custom_options(spark, "/path/to/delta", options={"mergeSchema": "true"})

# Writing Delta Lake data
write_delta_with_custom_options(delta_df, "/path/to/output", options={"overwriteSchema": "true"})
Apache Iceberg
python
Copy code
from etl_factory.pyspark_support import read_iceberg_with_custom_options, write_iceberg_with_custom_options

# Reading Iceberg data
iceberg_df = read_iceberg_with_custom_options(spark, "iceberg_db.table", options={"snapshot-id": "123456789"})

# Writing Iceberg data
write_iceberg_with_custom_options(iceberg_df, "iceberg_db.table", options={"overwrite": "true"})
Testing
Running Tests
Use pytest to run the unit tests and ensure everything works as expected:

bash
Copy code
pytest tests/
Example Test Script