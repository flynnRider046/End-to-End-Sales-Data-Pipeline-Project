# End-to-End Data Engineering Project using Sales Data in AWS

## Introduction
This project performs data engineering pipeline project on Sales data using Amazon Web Services. The main focus of this project is to implement the data engineering concepts using AWS tools.

## Architecture
This project uses following AWS Services
* <strong>Amazon S3</strong>: Used as the source for data pipeline.
* <strong>AWS Glue</strong>: catalog the data using crawler and process the data using pySpark with the interactive jupyter notebook.
* <strong>Amazon Cloudwatch</strong>: Monitor, log and push notifications into cloudwatch
* <strong>Amazon RedShift</strong>: Used to load the transformed data into target data store (Redshift).

## Implementation
To implement this a cloudformation template is created which provisions resources for an ETL(Extract, Transform and Load) pipeline using AWS Glue, Amazon Redshift and S3.

## Step by Step Implementation
* A CloudFormation stack is created with the existing .yaml file which contains all the resource configurations.
* We navigate to the source data bucket and upload the sales data into it.
* A sales database is created in AWS Glue and a glue crawler is created for the tables.
* ETL job is performed using GLue Studio by uploading the jupyter notebook which performs necessary data Extraction, Transformation and Loading.

## Steps performed under the Jupyter notebook.
* Creating Spark DataFrame from DynamicFrame from the table and removing null records.
* Perform necessary Data transformations.
* Group together region, region and perform aggregation metrics.
* Sort the data and convert the Spark DataFrame to Dynamic DataFrame.
* Load the final Dynamic DataFrame into Amazon Redshift cluster.

## Credits
<strong>DataTech By AnandKumar</strong>

## References
https://www.youtube.com/watch?v=6VJKR3sLTow&t=791s
