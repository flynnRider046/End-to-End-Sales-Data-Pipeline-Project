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
![stackCreation](https://github.com/flynnRider046/End-to-End-Sales-Data-Pipeline-Project/blob/69900dd951f74f5be71bfec5e2b1d24fa56660fa/Images/CloudFormation%20ETL%20stack%20creation.png)
* We navigate to the source data bucket and upload the sales data into it.
![S3databucket](https://github.com/flynnRider046/End-to-End-Sales-Data-Pipeline-Project/blob/69900dd951f74f5be71bfec5e2b1d24fa56660fa/Images/Source%20bucket%20data%20.png)
* A sales database is created in AWS Glue and a glue crawler is created for the tables.
![glueCrawler](https://github.com/flynnRider046/End-to-End-Sales-Data-Pipeline-Project/blob/69900dd951f74f5be71bfec5e2b1d24fa56660fa/Images/Glue%20crawler%20runs.png)
* ETL job is performed using GLue Studio by uploading the jupyter notebook which performs necessary data Extraction, Transformation and Loading.

## Steps performed under the Jupyter notebook.
* Creating Spark DataFrame from DynamicFrame from the table and removing null records.
* Perform necessary Data transformations.
* Group together region, region and perform aggregation metrics.
* Sort the data and convert the Spark DataFrame to Dynamic DataFrame.
* Load the final Dynamic DataFrame into Amazon Redshift cluster.

## Results
Below are the analysis which are performed on the transformed data using <strong>Redshift Query editor v2</strong>.
Analysis 1: Query to Calculating the profit margin
![Analysis1](https://github.com/flynnRider046/End-to-End-Sales-Data-Pipeline-Project/blob/438868c24db7faf1dedd1c44603f4ec60d0c5a19/Images/Analysis%201.png)

Analysis 2: Query to filter data by Region 'Europe' an Year '2017'
![Analysis2](https://github.com/flynnRider046/End-to-End-Sales-Data-Pipeline-Project/blob/438868c24db7faf1dedd1c44603f4ec60d0c5a19/Images/Analysis%202.png)

Analysis 3: Query to count the number of regional sales
![Analysis 3](https://github.com/flynnRider046/End-to-End-Sales-Data-Pipeline-Project/blob/438868c24db7faf1dedd1c44603f4ec60d0c5a19/Images/Analysis%203.png)

Analysis 4: Query to showcase revenue, Cost, and Profit Trends Over Quarters
![Analysis 4](https://github.com/flynnRider046/End-to-End-Sales-Data-Pipeline-Project/blob/438868c24db7faf1dedd1c44603f4ec60d0c5a19/Images/Analysis%204.png)

Analysis 5: Query to calculate highest Revenue Generating Country in Each Year
![Analysis 5](https://github.com/flynnRider046/End-to-End-Sales-Data-Pipeline-Project/blob/438868c24db7faf1dedd1c44603f4ec60d0c5a19/Images/Analysis%205.png)

Analysis 6: Query to calculate total revenue and profit by year.
![Analysis 6](https://github.com/flynnRider046/End-to-End-Sales-Data-Pipeline-Project/blob/438868c24db7faf1dedd1c44603f4ec60d0c5a19/Images/Analysis%206.png)

## Credits
<strong>DataTech By AnandKumar</strong>

## References
https://www.youtube.com/watch?v=6VJKR3sLTow&t=791s
