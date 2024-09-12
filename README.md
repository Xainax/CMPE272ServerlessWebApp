# CMPE272ServerlessWebApp

# Project Description
I built a serverless web application using AWS Lambda and Amazon DynamoDB as the database service.

# Setup Process 
1) To set up the serverless web application, you will need to go to AWS Management Console (https://aws.amazon.com/console/) and log in to your account. If you do not have an account, create a root account. 

2) Once you're on the AWS Management Console, search for DynamoDB and create a new table. The new table should be named `StudentRecords` and have the primary key `student_id`.
![image](https://github.com/user-attachments/assets/7eb821ab-09ad-44fc-89a8-6bfe79db71fe)

3) After creating your DynamoDB table, navigate to AWS Lambda and create a new function. The function name will be `StudentRecordHandler` and choose Python 3.12 as your language. 
![image](https://github.com/user-attachments/assets/41840286-a5b6-4eb3-a748-a14b391018cd)
![image](https://github.com/user-attachments/assets/7a0a5bf3-0881-49b9-be41-ddda0e3ebc5b)

4) After you have created the function you will need to configure the role to allow Lambda to read/write to DynamoDB. Navigate to Configuration, and click on the role name.
![image](https://github.com/user-attachments/assets/66337903-b853-4589-b7bc-742c8853e56a)

6) After clicking the role name, click Add permissions -> Attach policies. Search for AmazonDynamoDBFullAccess and add that permission.
![image](https://github.com/user-attachments/assets/69807b2a-cb8f-4138-a22d-ec6142ae9133)

7) After you have created the function, you can upload the lambda_function.py file that is located in this GitHub repository and deploy it.
![image](https://github.com/user-attachments/assets/5230732d-4f39-44bf-b593-f6f43e18abe8)

8) Now, search for API Gateway and create a new REST API. Download the StudentAPI-dev-swagger.json file and you can import the API.



# Results
Creating a new student record using the command:
` curl -X POST \
  https://l62jip7pib.execute-api.us-west-1.amazonaws.com/dev/students \
  -H 'Content-Type: application/json' \
  -d '{ "student_id": "123", "name": "John Doe", "course": "Enterprise Software" }'
 `
![image](https://github.com/user-attachments/assets/4003fc85-4ee6-43a9-afa8-6c567655e27d)

Reading the newly created student record using the command:
`curl -X GET \ "https://l62jip7pib.execute-api.us-west-1.amazonaws.com/dev/students?student_id=123"`
![image](https://github.com/user-attachments/assets/6b6b30b7-67c8-44dc-a9aa-579e885ea606)

Updating the student record using the command:
` curl -X PUT \ 
  "https://l62jip7pib.execute-api.us-west-1.amazonaws.com/dev/students?student_id=123" \
  -H 'Content-Type: application/json' \
  -d '{ "name": "John Doe", "course": "Advanced Cloud Computing" }'
`
![image](https://github.com/user-attachments/assets/8db0342d-2af8-450c-b597-88098c66798d)

Deleting the student record using the command:
`curl -X DELETE "https://l62jip7pib.execute-api.us-west-1.amazonaws.com/dev/students?student_id=123"`
![image](https://github.com/user-attachments/assets/9ffb31c5-b140-4726-8f93-c819d932ca8f)


# Reflection
Before this assignment, I had no knowledge of AWS Lambda or DynamoDB. Essentially, this whole assignment was full of learning experiences about some of the technologies that can be used in building a serverless web application.
