# Job Application Serverless Web Application using AWS

## Overview

A serverless job application portal built with:

- **Frontend:** HTML, CSS(static hosting on Amazon S3)
- **Backend:** AWS Lambda (Python), API Gateway, DynamoDB, and S3

## Features

- 📝 Applicants can submit their details and upload resumes.
- 👀 Recruiters can view all applications and open resumes directly from the portal.
- 📁 Resume files are stored in S3; application data is stored in DynamoDB.
- ☁️ Serverless architecture ensures scalability and low operational cost.

## Architecture Diagram

<img width="1255" height="729" alt="serverless job application architecture diagram" src="https://github.com/user-attachments/assets/1b586e4b-caf4-4721-b72c-0d6840a823f9" />



## How It Works

### 1. Applicant Portal:
- Users fill out a form and upload their resume.
- Data is sent to an API Gateway endpoint, which triggers a Lambda function.
- Lambda stores the application data in DynamoDB and uploads the resume to S3.

### 2. Recruiter Portal:
- Recruiters access a protected page to view all applications.
- The page fetches data from a Lambda GET endpoint via API Gateway.
- Resumes can be opened via public S3 links.

## Configuration

- Update the API endpoint URLs in the frontend HTML as needed.
- To change the S3 bucket for resumes, update the `bucketName` variable in the recruiter portal JavaScript file.

## Deployment

- Deploy Lambda functions using the AWS Console, AWS SAM, or the Serverless Framework.
- Deploy static frontend files to an S3 bucket with static website hosting enabled.
- Ensure **CORS** is enabled on API Gateway for your frontend domain.

---

## 🛠 AWS Services Used

- Amazon S3 – For static hosting and storing resumes.
- AWS Lambda – For backend logic and integration.
- Amazon API Gateway – For exposing Lambda functions as REST APIs.
- Amazon DynamoDB – For storing application metadata.

---

## 🚀 Getting Started

1. Clone this repository and set up your frontend.
2. Deploy backend Lambda functions with the correct IAM roles.
3. Upload frontend files to an S3 bucket with static hosting.
4. Configure API Gateway endpoints and update URLs in the frontend.
5. Test the flow: submit a form, view data, and open resumes.
