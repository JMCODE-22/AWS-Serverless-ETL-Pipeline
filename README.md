# Project Report: AWS-Serverless-ETL-Pipeline
A serverless ETL pipeline built on AWS using services like S3, AWS Lambda, Glue and Athena

**Author:** Jesna Menezes   **Date:** April 30,2026
<hr>

## Table of Contents
   1. [Project Overview](https://github.com/JMCODE-22/AWS-Serverless-ETL-Pipeline/edit/main/README.md#1-project-overview)
   2. [Architecture Diagram](https://github.com/JMCODE-22/AWS-Serverless-ETL-Pipeline/edit/main/README.md#2-architecture-diagram)
   3. [Step 1: Identity and Access Management(IAM) User Creation](https://github.com/JMCODE-22/AWS-Serverless-ETL-Pipeline/edit/main/README.md#3-step-1-identity-and-access-managementiam-user-creation)
   4. [Step 2: Simple Storage Service(S3) Bucket](https://github.com/JMCODE-22/AWS-Serverless-ETL-Pipeline/edit/main/README.md#4-step-2-simple-storage-services3-bucket)
   5. [Step 3: AWS Lambda with trigger](https://github.com/JMCODE-22/AWS-Serverless-ETL-Pipeline/edit/main/README.md#5-step-3-aws-lambda-with-trigger)
   6. [Step 4: AWS Glue and Data Catalog](https://github.com/JMCODE-22/AWS-Serverless-ETL-Pipeline/edit/main/README.md#6-step-4-aws-glue-and-data-catalog)
   7. [Step 4: AWS Athena](https://github.com/JMCODE-22/Superstore_DataAnalysis_using_AWS/edit/main/README.md#6-step-4-aws-athena)
   8. [Step 5: Amazon Quicksight](https://github.com/JMCODE-22/Superstore_DataAnalysis_using_AWS/edit/main/README.md#7-step-5-amazon-quicksight)
   
<hr>

### 1. Project Overview

This document outlines the step-by-step process to creating a end-to-end serverless ETL pipeline built on AWS using services like S3, AWS Lambda, Glue and Athena.
<hr>

### 2. Architecture Diagram
<img width="721" height="246" alt="AWS_Eventdriven_Serverless_Datapipeline_architecture" src="https://github.com/user-attachments/assets/8e026611-3cb1-4b4a-9f18-bbd175a6bdf2" />



### 3. Step 1: Identity and Access Management(IAM) User Creation
- Navigate to IAM and click on **Create User**
- Specify the usedetails and enable **Provide user access to the AWS Management Console - optional**
- Attached admin access directly to the user under set permissions.
- The user is created as below,
 
  <img width="1877" height="275" alt="image" src="https://github.com/user-attachments/assets/fe4bceb7-026c-4b62-9896-da875e0f7825" />
  
- Login using IAM user credentials

<hr>

### 4. Step 2: Simple Storage Service(S3) Bucket 
- Navigate to S3 and click on **Create bucket**
- Create a general purpose bucket with a unique bucket name in the specific AWS Region.
- Create a **orders_json_input** folder in the S3 bucket where the input files are received in json format.

<img width="1866" height="557" alt="image" src="https://github.com/user-attachments/assets/c233fad7-0946-4d1c-ae24-5d463df0809e" />

<hr>

### 5. Step 3: AWS Lambda with trigger
- Create a Lambda function which is invoked when new file is received in S3. 
- Add the S3 trigger to invoke the function

<img width="950" height="527" alt="image" src="https://github.com/user-attachments/assets/499c3ea8-79d7-4d92-8fe2-fce89a0433ea" />

<hr>

### 6. Step 4: AWS Glue and Data Catalog
- Navigate to **AWS Glue-> Databases -> Add Database**
- Create a Database as below,
<img width="1541" height="277" alt="image" src="https://github.com/user-attachments/assets/5b063b00-6d63-4387-8009-15d238154891" />

- Navigate to **AWS Glue->Crawlers->Add crawler**
- Create a crawler on S3 bucket
- Add a IAM user Role for the AWS services to use
- Run the crawler on the data available to create a table definition without storing the data. This is creating the Data catalog/meteadata for the data.
  
<img width="1507" height="270" alt="image" src="https://github.com/user-attachments/assets/ee6a6e50-a812-4680-9241-c371040e45de" />

<hr>

### 6. Step 4: AWS Athena
- Navigate **Athena->Query Editor**
- Select the appropriate Databa source and Database 
- Create a S3 folder to save the Athena results
- Preview the orders table

  <img width="1865" height="727" alt="image" src="https://github.com/user-attachments/assets/4f23878e-1c01-4b62-851c-9f5b45ea0070" />

<hr>

### 7. Step 5: Amazon Quicksight
- Navigate to **Quicksight**
- Create the Database under Athena
- Start analysing the data using quicksight and create the dashboard and publish the same.

<hr>





   

