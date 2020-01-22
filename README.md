# Sparkify Airflow Data Pipelines

ETL automation for Sparkify data via Airflow DAG

## Setup

### Requirements

You'll need an [AWS](https://aws.amazon.com/) account with the resources to make ~20k Simple Storage Service Requests ($0.004 per request, more pricing details [here](https://aws.amazon.com/s3/pricing/))

You'll also need this software installed on your system 
* [Python](https://www.python.org/downloads/)
* [Airflow](https://airflow.apache.org/)


## Project Structure

```
sparkify-airflow/
 ├── dags
    └── sparkify_dag.py             Primary dag for running the project  
 ├── plugins     
    ├── helpers
    ├── operators
         ├── data_quality.py        Operator checks row count in given table
         ├── load_dimension.py      Inserts rows from source to given destination
         ├── load_fact.py
         └── stage_redshift.py
 ├── README.md                      Documentation of the project
 ├── dwh.cfg                        Configuration file for setting up S3 sources/destinations & AWS credentials
 └── create_tables.sql              SQL DDL code setting up tables in Redshift 
```