# aws-stepfunctions-local-tutorial
[![LICENSE](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE)

A hands-on beginning guide to build up a AWS Step Functions project in local environment

In this tutorial, you will build up a AWS Step Functions workflow integrating with **AWS Lambda Local**, **AWS Dynamodb** and **AWS Simple Notification Service** natively without triggering by Lambda itself.

## What is Step Functions Local
---
StepFunctionsLocal is a full-featured AWS Step Functions runs locally on your machine. 

## Why we need Step Functions Local
---
SFL enables developers to develop and test applications using a version of Step Functions running in your own development environment.

## Getting Started
---
### Setting Up Step Functions Local 

Please refer to the [Setting Up Step Functions Local (Downloadable Version)](https://docs.aws.amazon.com/step-functions/latest/dg/sfn-local.html) in AWS Official Document website to setup the environment.

### Setting Up AWS SAM Framework

The [AWS Serverless Application Model (AWS SAM)](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/what-is-sam.html) is an open-source framework that you can use to build serverless applications on AWS. We will use AWS SAM to develop and test AWS Lambda Local.

### Initialize the Lambda Local function with AWS SAM

  - Run the following command at an AWS SAM CLI command prompt.
  ```
  sam init --runtime python3.6 
  ```
  - A project folder(sam-app/) will be generated. It is a sample app to display the local ip address.
  - In the sam-app directory, build the project by using command
  ```
  sam build
  ```
  - Test the Lambda function locally
  ```
  sam local start-api
  ```
  The command returns an API Gateway endpoint, which you can send requests to for local testing.
  - In the teminal, use `curl` to test the Lambda function
  ```
  curl http://127.0.0.1:3000/hello 
  {"message": "hello world", "location": "72.21.198.66"}
  ```
  - If the testing works, start the lambda local
  ```
  sam local start-lambda
  ```
### Initialize the Step Functions Local with Docker
  - In this tutorial, we will use docker to launch the Step Functions Local, you might launch it by Jar package
