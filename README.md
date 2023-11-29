# Predicting the Unpredictable: Amazon Forecast and Rare Weather Events

## Introduction
- Brief overview of the project's aim to use Amazon Forecast for predicting rare weather events.
- Discussion on the potential impact of such predictions on various economic sectors.

## Table of Contents
- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Data Collection and Processing](#data-collection-and-processing)
- [Workflow](#workflow)
- [Architecture Overview](#architecture-overview)
- [Usage Instructions](#usage-instructions)
- [Resources: AWS Services Integration](#resources-aws-services-integration)
- [Blog Post](#blog-post)
- [Acknowledgments](#acknowledgments)

## Prerequisites

Before beginning with this project, ensure that you have the following prerequisites in place:

**Software and Tools:**
- **Python Environment:** Python installed, along with pip for managing packages.
- **Jupyter Notebook:** For running and understanding the Jupyter notebooks included in the project.
- **AWS Account:** Access to an AWS account with permissions to use Amazon Forecast, S3, Lambda, EC2, and DynamoDB.

**Data:**
- Access to the weather data from [MeteoBlue](https://www.meteoblue.com/en/weather/archive/export) or similar historical weather datasets.

## Data Collection and Processing
- Sources and methods for weather and economic data collection.
- b
#### Import Data
- Process for transforming and preparing the data for analysis.
#### Data Examples
- Examples of weather data and economic indicators used in the project.
- Sample outputs from the Amazon Forecast predictions.
  
## Workflow
- 
## Architecture Overview
- Diagram
  
## Usage Instructions
- Step-by-step guide on how to execute the project's scripts.
- Examples of command-line operations.

## Resources: AWS Services Integration

* [Amazon S3](https://aws.amazon.com/s3/)
  * A primary bucket for storing collected weather data and economic indicators.
  * A secondary bucket to store processed data and results from Amazon Forecast.
  * An additional bucket for logging and storing miscellaneous project files.

* [Amazon Forecast](https://aws.amazon.com/forecast/)
  * Utilized for creating and training predictive models based on historical weather data.
  * Generating forecasts for rare weather events and analyzing their potential economic impacts.

* [Amazon Lambda](https://aws.amazon.com/lambda/) (x2)
  * A Lambda function for automating the data transformation process with Python, deployed with necessary memory and execution role.
  * Another Lambda function to periodically trigger Amazon Forecast operations and manage data flow.

* [Amazon EC2](https://aws.amazon.com/ec2/)
  * An EC2 instance for conducting heavier data processing and analysis tasks.
  * Hosting the Jupyter Notebook server for detailed data exploration and visualization.

* [AWS DynamoDB](https://aws.amazon.com/dynamodb/)
  * A DynamoDB table to store and manage the forecasts generated by Amazon Forecast for easy retrieval and analysis.

* [Amazon Identity and Access Management](https://aws.amazon.com/iam/)
  * IAM Roles with appropriate permissions for Lambda functions, Amazon Forecast, and EC2 instances to access other AWS resources securely.

* [AWS CloudFormation](https://aws.amazon.com/cloudformation/)
  * Automating the deployment of the AWS infrastructure required for the project.
    
* [Amazon API Gateway](https://aws.amazon.com/api-gateway/)
  * RESTful API endpoints to interact with web appplication

## Blog Post
Our project blog, hosted on AWS and developed in a Jupyter notebook, offers an engaging narrative and comprehensive analysis of predicting rare weather events using Amazon Forecast. It frames the problem in a data science context, enriched with relevant graphics, background resources, and a clear hypothesis. The blog provides an insightful walkthrough of the Amazon Forecast API, detailing our experiences and findings, including unexpected insights revealed through statistical analysis. For an in-depth understanding of our journey and findings, we invite readers to explore the blog through the provided link.



## Acknowledgments
This project, "Predicting the Unpredictable: Amazon Forecast and Rare Weather Events," owes its inception and development to a dedicated team of individuals whose contributions have been invaluable.

**Team Members:**
- **Audrey Bu:** 
- **Alina Chen:**
- **Indy Gu:** 
- **Alvin Jiao:**
- **Yiran Liu:** 

Special thanks to **Professor Dr. Jeremy Jacobson** of QTM350. This course, with its emphasis on programming for data science and its applications in a real-world context, has been the backbone of this project. Dr. Jacobson's guidance in computing concepts, workflow for reproducible research, and utilization of cloud computing resources has been instrumental in shaping our approach.

We would also like to extend our gratitude to [MeteoBlue](https://www.meteoblue.com/en/weather/archive/export) for providing the comprehensive weather data that formed the foundation of our analysis. Their archive has been a vital resource in our endeavor to understand and predict weather patterns.

This project is a testament to the collaborative efforts of everyone involved, and we are immensely thankful for their time, expertise, and enthusiasm.

