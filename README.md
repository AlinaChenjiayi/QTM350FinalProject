# Predicting the Unpredictable: Is Amazon Forecast good at predicting weather in Basel?

## Introduction
This project embarked from a personal journey, where an unexpected encounter with erratic weather during our team member's travel in Basel sparked a deeper exploration into weather forecasting. Motivated by this real-world experience, we chose Amazon Forecast for its advanced time-series forecasting capabilities to develop a model that predicts rare weather events with greater accuracy. Focusing on historical weather data from Basel, our aim was to create a tool that addresses the challenges faced by travelers. The result is a refined weather forecasting model, enhancing travel planning with more reliable predictions and better preparedness.

In this GitHub repository, you will find all the resources and documentation necessary to replicate our project. It serves as a comprehensive guide, detailing our use of Amazon Forecast, our data analysis strategies, and the methodologies we employed. This repository is intended as a practical resource for researchers, data scientists, and anyone interested in applying advanced forecasting techniques to real-world scenarios, providing a step-by-step guide to recreate our approach in predicting rare weather events.
### Team Members
- **Audrey Bu:** <audrey.bu@emory.edu>
- **Alina Chen:** <jiayi.chen@emory.edu>
- **Indy Gu:** <indy.gu@emory.edu>
- **Alvin Jiao:** <yiyang.jiao@emory.edu>
- **Yiran Liu:** <yiran.liu@emory.edu> \
Feel free to contact any of us if you have any questions regarding to our project. 


## Table of Contents
- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Blog Post](#blog-post)
- [Workflow](#workflow)
  - [Data Collection and Processing](#data-collection-and-processing)
   - [Architecture Overview](#architecture-overview)
  - [Usage Instructions](#usage-instructions)
- [Resources: AWS Services Integration](#resources-aws-services-integration)
- [Acknowledgments](#acknowledgments)

## Prerequisites

Before beginning with this project, ensure that you have the following prerequisites in place:

**Software and Tools:**
- **Python Environment:** Python installed, along with pip for managing packages.
- **Jupyter Notebook:** For running and understanding the Jupyter notebooks included in the project.
- **AWS Account:** Access to an AWS account with permissions to use Amazon Forecast, S3, Lambda, EC2, and DynamoDB.
  
## Blog Post
Our project blog, hosted on AWS and developed in a Jupyter notebook, offers an engaging narrative and comprehensive analysis of predicting weather using Amazon Forecast. It frames the problem in a data science context, enriched with relevant graphics, background resources, and a clear hypothesis. The blog provides an insightful walkthrough of the Amazon Forecast API, detailing our experiences and findings, including unexpected insights revealed through statistical analysis. For an in-depth understanding of our journey and findings, we invite readers to explore the blog through the provided link: [Blog post](https://amazonforecastbasel.s3.amazonaws.com/Blog.html).

## Workflow
### Data Collection and Processing
The dataset we are using is the open dataset that records the weather in Basel. We have uploaded it in [*Dataset Folder*](https://github.com/AlinaChenjiayi/Group2ProjectFA23/tree/main/Dataset), along with the training and test sets.
### Import Data Guide
This section provides a detailed guide on how to import data into the Amazon Forecast model using AWS S3 Bucket. Follow these steps to ensure a smooth data import process.

**Step 1: Accessing AWS S3**
**Navigate to AWS S3**: Log into your AWS Management Console and open the S3 service.
   
**Locate the Bucket**: In the S3 dashboard, find and click on the bucket, you can use the public bucket you have created before. If you haven't created a bucket, click create a bucket. Please make sure disselect all checking boxes in Block Public Access settings to make the bucket public. 
   ![plot](https://github.com/AlinaChenjiayi/Group2ProjectFA23/blob/main/S3%20bucket%20guide%20pics/Step1.1.png)
   ![Step 1.2](https://github.com/AlinaChenjiayi/Group2ProjectFA23/blob/main/S3%20bucket%20guide%20pics/Step1.2.png)

**Step 2: Uploading Data to S3 Bucket**

**Upload Data Files**: Entering the bucket from step 1, under the tab 'Object', click on the 'Upload' button to add your data files to this folder.
    ![Step 1.3](https://github.com/AlinaChenjiayi/Group2ProjectFA23/blob/main/S3%20bucket%20guide%20pics/Step1.3.png)
   ![Step 1.4](https://github.com/AlinaChenjiayi/Group2ProjectFA23/blob/main/S3%20bucket%20guide%20pics/Step1.5.png)
   ![Step 1.5](https://github.com/AlinaChenjiayi/Group2ProjectFA23/blob/main/S3%20bucket%20guide%20pics/Step1.6.png)

**Step 3: Verifying Data Upload**
 **Check File Upload**: Ensure that all your data files are uploaded successfully and correctly in the folder. You can click on individual files to view their details and confirm the upload. 
   ![Step 1.6](https://github.com/AlinaChenjiayi/Group2ProjectFA23/blob/main/S3%20bucket%20guide%20pics/Step1.7.png)
   ![Step 1.7](https://github.com/AlinaChenjiayi/Group2ProjectFA23/blob/main/S3%20bucket%20guide%20pics/Step1.8.png)

By following these steps, you should have successfully imported your data into the AWS S3 Bucket, ready for use with Amazon Forecast. Make sure the data is correctly formatted and aligned with the requirements of the forecasting model for optimal results.

### Data Preprocessing
- We first add a new column called ID with unique values. Then, we convert the timestamp column to datetime format that's suitable for S3 and Amazon forecast.
- Secondly, we modify the column names to remove spaces and special characters. We also convert the column names to **lower case**. This is required for Amazon Forecast.
- Finally, we perform train-test split with ratio 80%-20% and export to csv file.
For detailed walkthrough of the data loading and preprocessing process, you can refer to [Blog](https://github.com/AlinaChenjiayi/Group2ProjectFA23/blob/main/Blog.html)
  
### Architecture Overview
 ![Diagram](./ArcD.jpg)

  
### Usage Instructions
- For detailed walthrough of using Amazon Forecast, please refer to our uploaded [tutorial](https://github.com/AlinaChenjiayi/Group2ProjectFA23/blob/main/ML%20with%20Amazon%20Forecast.html).
- For the code we've attached, please change the related link and working directory in the code first when you use it. 

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


## Acknowledgments
This project, "Predicting the Unpredictable: Amazon Forecast and Rare Weather Events," owes its inception and development to a dedicated team of individuals whose contributions have been invaluable.

Special thanks to **Professor Dr. Jeremy Jacobson** of QTM350. This course, with its emphasis on programming for data science and its applications in a real-world context, has been the backbone of this project. Dr. Jacobson's guidance in computing concepts, workflow for reproducible research, and utilization of cloud computing resources has been instrumental in shaping our approach.

We would also like to extend our gratitude to [MeteoBlue](https://www.meteoblue.com/en/weather/archive/export) for providing the comprehensive weather data that formed the foundation of our analysis. Their archive has been a vital resource in our endeavor to understand and predict weather patterns.
