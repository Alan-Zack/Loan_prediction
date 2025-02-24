﻿# Loan_prediction
![Architecture](loan_architecture.png)


## Overview
This project outlines an AWS-based architecture for training and deploying a loan prediction machine learning model using AWS SageMaker. It integrates multiple AWS services to automate data processing, model training, inference, and notification mechanisms.

## Architecture Components

### 1. **Data Storage (S3 Bucket)**
   - Stores raw and processed loan prediction data used for training the ML model.

### 2. **AWS SageMaker**
   - **Notebook**: Develops and preprocesses loan prediction data.
   - **Training**: Trains a machine learning model using the loan dataset.
   - **Model Deployment**: Deploys the trained model as an endpoint for inference.

### 3. **AWS Lambda**
   - Triggers notifications via AWS SNS.
   - Calls the deployed SageMaker endpoint for inference when required.

### 4. **AWS SNS (Simple Notification Service)**
   - Sends email notifications based on Lambda triggers.

### 5. **AWS API Gateway**
   - Acts as an interface for customer applications to interact with the deployed model.

### 6. **Customer Application**
   - Interacts with the API Gateway to fetch loan approval predictions.

## Workflow
1. **Data Ingestion**: Loan prediction data is stored in an S3 bucket.
2. **Model Training**: SageMaker trains a loan prediction model using the provided dataset.
3. **Model Deployment**: The trained model is deployed as an endpoint in SageMaker.
4. **Inference Trigger**: AWS Lambda is triggered to call the deployed model endpoint for loan approval predictions.
5. **Notification**: Lambda triggers AWS SNS to send email notifications.
6. **Customer Application**: Customers interact with the API Gateway to get loan approval predictions from the deployed model.

## Prerequisites
- An AWS account with access to S3, SageMaker, Lambda, SNS, and API Gateway.
- IAM roles with appropriate permissions to allow communication between AWS services.
- A trained machine learning model in SageMaker for loan prediction.
- A GitLab repository set up for managing source code and CI/CD.

## Deployment Steps
1. **Upload Loan Prediction Data to S3**
2. **Launch a SageMaker Notebook Instance** and prepare the dataset.
3. **Train the Loan Prediction Model** using SageMaker.
4. **Deploy the Model** as an endpoint.
5. **Set Up AWS Lambda** functions to trigger SNS and call the model endpoint.
6. **Configure AWS SNS** for notifications.
7. **Set Up API Gateway** to expose the model inference endpoint to external applications.
8. **Deploy and Test** the architecture.

## Usage
- Once deployed, customer applications can send requests to the API Gateway.
- API Gateway routes the request to AWS Lambda.
- AWS Lambda calls the SageMaker endpoint and returns loan approval predictions.
- Notifications are sent through AWS SNS when necessary.

## Conclusion
This architecture provides an automated, scalable, and efficient way to train, deploy, and interact with a loan prediction machine learning model using AWS services.




![Output](out_loan_prediction.png)
