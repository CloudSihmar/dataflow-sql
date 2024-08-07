# Apache Beam Dataflow Pipeline Example

This document provides a step-by-step guide to setting up and running an Apache Beam pipeline using Google Cloud Dataflow.

## Prerequisites

- Google Cloud Platform (GCP) account
- Google Cloud SDK installed

## Steps

### 1. Create a Bucket

Create a bucket to store the output or temporary data and upload the CSV file.

### 2. Create a BigQuery Dataset and Table

Create a BigQuery dataset and table with the following schema:

- **Dataset**: `dataset_demo`
- **Table**: `output-sql`
- **Schema**:
  - `products:STRING`
  - `total_sales:INTEGER`

### 3. Set Up a Virtual Environment

Install the `virtualenv` module, create a virtual environment, and then activate it:

```sh
pip3 install virtualenv
python3 -m virtualenv env
source env/bin/activate
```

### 4. Install Apache Beam SDK

```sh
pip3 install apache-beam[gcp]
```


### 5. upload the python script and run the pipeline in the cloudshell

```sh
python dataflow_sql.py \
    --project=techlanders-internal \
    --temp_location=gs://sandeep-apache/temp \
    --input=gs://sandeep-apache/input.csv \
    --output=techlanders-internal.dataset_demo.output-sql \
    --region us-east1  \
    --zone=us-east1-b \
    --runner=DataflowRunner
```

