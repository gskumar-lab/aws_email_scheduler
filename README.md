# AWS Scheduled Email Marketing System

This project is a serverless, zero-budget email marketing solution using AWS services like SES, S3, Lambda, EventBridge, and IAM.

## ✨ Features
- Schedule-based email delivery (e.g., weekly newsletters)
- Personalized email templates using CSV contacts
- Purely on AWS Free Tier services

## 🛠 Tech Stack
- **AWS Lambda** (Python)
- **Amazon S3** (HTML + CSV storage)
- **Amazon SES** (email delivery)
- **Amazon EventBridge** (scheduling)
- **IAM** (access control)

## 🗂 Project Structure
- `aws-email-scheduler/`  
  - `lambda/`  
    - `lambda_function.py` — AWS Lambda function to send personalized emails  
    - `test_event_lambda.json` — Dummy event to test Lambda  
  - `templates/`  
    - `email_template.html` — HTML template with `{{FirstName}}` placeholder  
  - `data/`  
    - `contacts.csv` — Contact list (`FirstName,Email`)  
  - `iam/`  
    - `iam_policy_s3_ses_permissions.json` — IAM policy for S3 + SES access from lambda  
  - `README.md` — Project overview and setup  

## 🧪 Testing
Use `test_event_lambda.json` to test the Lambda via console or CLI.

## ⚙️ Deployment Steps
1. Upload `email_template.html` and `contacts.csv` to your S3 bucket.
2. Deploy `lambda_function.py` to AWS Lambda.
3. Assign IAM role with `iam_policy_s3_ses_permissions.json`.
4. Set up EventBridge rule to trigger Lambda on schedule.
5. Verify SES "From" email address.

## 📬 Sample Email Preview
See `templates/email_template.html`.

## 📌 Notes
- Ensure SES is out of sandbox mode for production emails.
- Customize the template and CSV headers as needed.

