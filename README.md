
# Ola and Uber Data Engineering Project

## Overview

This project showcases an end-to-end data engineering solution for processing and analyzing ride data in a manner similar to Uber. The pipeline is built on Google Cloud Platform (GCP) and utilizes BigQuery for data storage, Dataflow for stream processing, and Compute Engine for batch processing.

## Project Structure

- `data/`: Contains sample ride data in CSV format.
- `scripts/`: Includes scripts for data preprocessing and loading.
- `stream_processing/`: Dataflow pipeline for real-time data processing.
- `batch_processing/`: Compute Engine scripts for batch processing.
- `sql_queries/`: SQL queries for data analysis in BigQuery.

## Getting Started

### Prerequisites

1. Install Google Cloud SDK: [Installation Guide](https://cloud.google.com/sdk/docs/install)
2. Set up a GCP project and enable necessary APIs.

### Configuration

1. Set up authentication for GCP:
   ```bash
   gcloud auth application-default login
   ```

2. Create a BigQuery dataset:
   ```bash
   bq mk <dataset_name>
   ```

3. Update configuration files in `stream_processing/` and `batch_processing/` with your GCP project details.

## Usage

### Stream Processing

1. Run the Dataflow stream processing pipeline:
   ```bash
   cd stream_processing/
   python process_stream_data.py --input_topic=<input_topic> --output_table=<output_table>
   ```

### Batch Processing

1. Upload batch data to GCS:
   ```bash
   cd batch_processing/
   ./upload_data_to_gcs.sh
   ```

2. Run the batch processing job on Compute Engine:
   ```bash
   ./run_batch_processing.sh --input_path=<input_path> --output_table=<output_table>
   ```

### Analysis

1. Run SQL queries in BigQuery for analysis:
   ```bash
   bq query --use_legacy_sql=false < sql_queries/analysis_query.sql
   ```

## Contributing

Feel free to contribute by opening issues or submitting pull requests.
