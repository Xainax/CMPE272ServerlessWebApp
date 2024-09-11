# CMPE272ServerlessWebApp

# Project Description
I built a serverless web application using AWS Lambda and Amazon DynamoDB as the database service.

# Setup Process 
To set up the serverless web application, you will need to go to AWS Management Console (https://aws.amazon.com/console/) and log in to your account. If you do not have an account, create a root account. 

Once you're on the AWS Management Console, search for DynamoDB and create a new table. The new table should be named `StudentRecords` and have the primary key `student_id`.

After creating your DynamoDB table, navigate to AWS Lambda and create a new function. The function name will be `StudentRecordHandler` and choose Python 3.12 as your language. Make sure you also attach the proper role to handle basic CRUD operations with DynamoDB.

After you have created the function, you can upload the lambda_function.py file that is located in this GitHub repository and deploy it.

Now, search for API Gateway and create a new REST API.



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
