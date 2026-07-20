# 🚀 Data Redundancy Removal System Using AWS

A serverless AWS project that detects duplicate employee records, stores only unique records, creates JSON backups, sends email notifications, and maintains logs using AWS services.

---

## 📖 Project Overview

The **Data Redundancy Removal System** validates incoming employee records before storing them in the database.

### Workflow

- Validate employee details.
- Check whether the employee record already exists.
- If the record is duplicate:
  - Reject the record.
  - Send a duplicate notification via Amazon SNS.
- If the record is unique:
  - Store the record in Amazon DynamoDB.
  - Create a JSON backup in Amazon S3.
  - Send a success notification via Amazon SNS.
  - Store execution logs in Amazon CloudWatch.

---

## 🛠️ AWS Services Used

| AWS Service | Purpose |
|-------------|---------|
| AWS Lambda | Executes business logic |
| Amazon API Gateway | Exposes REST API |
| Amazon DynamoDB | Stores employee records |
| Amazon S3 | Stores JSON backup files |
| Amazon SNS | Sends email notifications |
| AWS IAM | Manages permissions |
| Amazon CloudWatch | Stores application logs |
| Postman | Tests REST APIs |

---

## 🔄 System Architecture

```text
                User
                  │
                  ▼
              Postman
                  │
                  ▼
          Amazon API Gateway
                  │
                  ▼
             AWS Lambda
                  │
       Validate Employee Data
                  │
         Check Duplicate Record
                  │
        ┌─────────┴─────────┐
        │                   │
        ▼                   ▼
   Duplicate             Unique
        │                   │
        ▼                   ▼
 Amazon SNS          Amazon DynamoDB
 Notification               │
                             ▼
                      Amazon S3 Backup
                             │
                             ▼
                    Amazon SNS Success Mail
                             │
                             ▼
                    Amazon CloudWatch Logs
```

---

# 📷 Project Screenshots

## 1. Amazon DynamoDB

![DynamoDB Table](Screenshots/1-dynamodb-table.png)

![Stored Records](Screenshots/2-dynamodb-record.png)

---

## 2. Amazon S3 Bucket

![S3 Bucket](Screenshots/3-s3-bucket.png)

![Stored Backup](Screenshots/4-s3-files.png)

---

## 3. Amazon SNS

![SNS Topic](Screenshots/5-sns-topic.png)

![SNS Subscription](Screenshots/6-sns-subscription.png)

![SNS Email](Screenshots/7-sns-email.png)

---

## 4. AWS Lambda

![Lambda Function](Screenshots/8-lambda-function.png)

![Environment Variables](Screenshots/9-lambda-environment.png)

![Lambda Test](Screenshots/10-lambda-test.png)

![Lambda Result](Screenshots/11-lambda-result.png)

---

## 5. Amazon API Gateway

![API Gateway](Screenshots/12-api-gateway.png)

![API Deployment](Screenshots/13-api-deployment.png)

---

## 6. Postman Testing

### Successful Request

![Postman Success](Screenshots/14-postman-success.png)

![Success Response](Screenshots/15-postman-response.png)

### Duplicate Request

![Duplicate Response](Screenshots/16-postman-duplicate.png)

---

## 7. Amazon CloudWatch Logs

![CloudWatch Logs](Screenshots/17-cloudwatch-logs.png)

![Execution Logs](Screenshots/18-cloudwatch-details.png)

---

## 8. Email Notifications

![Success Email](Screenshots/19-email-success.png)

![Duplicate Email](Screenshots/20-email-duplicate.png)

---

## 9. JSON Backup in Amazon S3

![JSON Backup](Screenshots/21-s3-json-backup.png)

---

# 📤 Sample API Request

```json
{
    "employeeId": "101",
    "name": "Navnath",
    "email": "Navnath@example.com"
}
```

---

# ✅ Success Response

```json
{
    "statusCode": 200,
    "body": "Record Added Successfully"
}
```

---

# ❌ Duplicate Response

```json
{
    "statusCode": 400,
    "body": "Duplicate Record Found"
}
```

---

# 💻 Technologies Used

- Python
- AWS Lambda
- Amazon API Gateway
- Amazon DynamoDB
- Amazon S3
- Amazon SNS
- AWS IAM
- Amazon CloudWatch
- REST API
- Postman
- Git
- GitHub

---

# 📂 Project Structure

```text
Data-Redundancy-Removal-System
│
├── lambda_function.py
├── requirements.txt
├── README.md
├── .gitignore
├── LICENSE
└── Screenshots
    ├── 1-dynamodb-table.png
    ├── 2-dynamodb-record.png
    ├── 3-s3-bucket.png
    ├── 4-s3-files.png
    ├── 5-sns-topic.png
    ├── 6-sns-subscription.png
    ├── 7-sns-email.png
    ├── 8-lambda-function.png
    ├── 9-lambda-environment.png
    ├── 10-lambda-test.png
    ├── 11-lambda-result.png
    ├── 12-api-gateway.png
    ├── 13-api-deployment.png
    ├── 14-postman-success.png
    ├── 15-postman-response.png
    ├── 16-postman-duplicate.png
    ├── 17-cloudwatch-logs.png
    ├── 18-cloudwatch-details.png
    ├── 19-email-success.png
    ├── 20-email-duplicate.png
    └── 21-s3-json-backup.png
```

---

# ▶️ How to Run the Project

1. Clone the repository.

```bash
git clone https://github.com/navnath12345/Data-Redundancy-Removal-System.git
```

2. Navigate to the project directory.

```bash
cd Data-Redundancy-Removal-System
```

3. Deploy the Lambda function to AWS.

4. Configure:
   - Amazon DynamoDB
   - Amazon S3
   - Amazon SNS
   - API Gateway
   - IAM Roles

5. Test the API using Postman.

---

# ✨ Features

- Detects duplicate employee records
- Prevents redundant data storage
- Stores only unique records
- Creates automatic JSON backups
- Sends email notifications
- REST API integration
- Serverless AWS architecture
- CloudWatch monitoring and logging

---

# 👩‍💻 Author

**Navnath Monde**

AWS Cloud Internship Project

**CodeAlpha**

---

## ⭐ Support

If you found this project helpful, please consider giving it a **⭐ Star** on GitHub.
