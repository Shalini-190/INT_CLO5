# Serverless Architecture Using AWS Lambda  

## Overview  
This project demonstrates a serverless architecture implemented using AWS Lambda, API Gateway, and DynamoDB. It involves creating a contact form that stores user submissions in DynamoDB through a REST API managed by API Gateway. The project is designed to handle backend logic without managing any servers.

---

## Features  
- AWS Lambda Functions: Backend logic for handling HTTP GET and POST requests.  
- API Gateway: Exposes the Lambda function as a REST API.  
- DynamoDB Integration: Stores form data securely.  
- Event-Driven Architecture: Functions triggered by HTTP events.  

---

## Prerequisites  
- AWS Account  
- IAM Role with appropriate permissions  
- AWS CLI installed and configured  
- Basic knowledge of Python  

---

## Steps  

### 1. Create IAM Role  
- Go to the **IAM Console** and create a new role.  
- Attach the following policies:  
  - `AWSLambdaBasicExecutionRole`  
  - `AmazonDynamoDBFullAccess`  
- Note the **Role ARN** for use in Lambda function configuration.

---

### 2. Create DynamoDB Table  
- Go to the **DynamoDB Console** and create a table:  
  - Table Name: `contact_table`  
  - Primary Key: `email` (String)  

---

### 3. Create Lambda Function  
- Navigate to the **AWS Lambda Console**.  
- Create a new function:  
  - Function Name: `ContactUsHandler`  
  - Runtime: Python 3.x  
  - Execution Role: Select the IAM Role created earlier.  
- Add logic to handle GET and POST requests and interact with DynamoDB.

---

### 4. Configure API Gateway  
- Go to the **API Gateway Console** and create a new REST API.  
- Add a new resource (e.g., `/contact`).  
- Add two methods:  
  - GET: Integrate with the Lambda function for retrieving the form page.  
  - POST: Integrate with the Lambda function for handling form submissions.  
- Deploy the API and note the **Invoke URL**.

---

### 5. Frontend - Contact Us Page  
- Create a simple HTML form to submit data to the API Gateway URL.

---

### 6. Deploy Lambda Function  
- Test the Lambda function locally or on AWS using test events.  
- Deploy updates via the AWS Console or CLI if changes are needed.

---

### 7. Testing  
- Open the contact form in a browser and submit data.  
- Check the **DynamoDB Table** for the stored data.  
- Use tools like **Postman** or **curl** to test API endpoints.  

---

## Outcome  
The serverless application successfully handles form submissions and stores data in DynamoDB without requiring any server management.
