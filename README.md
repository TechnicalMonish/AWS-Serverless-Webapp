# Job Application Serverless Web Application using AWS

## Overview

A serverless job application portal built with:
- **Frontend:** HTML, CSS, JavaScript (static hosting on S3)
- **Backend:** AWS Lambda (Python), API Gateway, DynamoDB, S3

## Features

- Applicants can submit their details and upload resumes.
- Recruiters can view all applications and open resumes directly from the portal.
- Resume files are stored in S3; application data is stored in DynamoDB.
- Serverless architecture for scalability and low cost.

## Architecture Diagram
![image](https://github.com/user-attachments/assets/2d2e3f78-182c-4281-bcc7-dad027eebdf6)


## How it works

1. **Applicant Portal:**  
   - Users fill out a form and upload their resume.
   - Data is sent to an API Gateway endpoint, which triggers a Lambda function.
   - Lambda stores the application data in DynamoDB and uploads the resume to S3.

2. **Recruiter Portal:**  
   - Recruiters access a protected page to view all applications.
   - The page fetches data from a Lambda GET endpoint via API Gateway.
   - Resumes can be opened via public S3 links.

## Configuration

- Update the API endpoint URLs in the frontend JavaScript as needed.
- To change the S3 bucket for resumes, update the `bucketName` variable in the recruiter portal JS.


## Deployment

- Deploy Lambda functions using AWS Console or SAM/Serverless Framework.
- Deploy static frontend files to an S3 bucket with static website hosting enabled.
- Ensure CORS is enabled on API Gateway for your frontend domain.
