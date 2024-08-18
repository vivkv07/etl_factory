# etl_factory

## Overview

`etl_factory` is a versatile ETL library designed to streamline data processing using multiple engines, including PySpark, pandas, and Polars. The library supports various data formats such as CSV, JSON, Parquet, ORC, Delta Lake, and Apache Iceberg, providing a unified interface for data ingestion, transformation, and validation.

## Features

- **Multi-Engine Support:** Choose between PySpark, pandas, and Polars for your ETL tasks.
- **Wide Format Compatibility:** Read and write data in CSV, JSON, Parquet, ORC, Delta Lake, and Apache Iceberg formats.
- **Basic ETL Operations:** Perform filtering, joining, aggregation, and more.
- **Data Validation:** Ensure data quality with schema validation and missing value checks.

## Installation

### Prerequisites

- Python 3.7+
- PySpark
- Delta Lake
- Apache Iceberg

### Install Dependencies

```bash
pip install pyspark
pip install delta-spark
pip install iceberg-spark3


