# Rule Engine Project

## Objective: 

Develop a simple 3-tier rule engine application (Simple UI, API and Backend, Data) to determine user eligibility based on attributes like age, department, income, spend etc. The system can use Abstract Syntax Tree (AST) to represent conditional rules and allow for dynamic creation, combination, and modification of these rules. 

## Project Structure 

/your-project 

├── controllers 

│   └── ruleController.js 

├── routes 

│   └── ruleRoutes.js 

├── server.js 

└── README.md 
 

## Technologies Used 

Node.js 

Express 

JavaScript 

JSON for data interchange 

## Prerequisites 

Node.js (v14 or higher) 

npm (Node Package Manager) 

## Installation 

Clone the repository: 

git clone https://github.com/KanneNagakeerthana/Rule-Engine-Ast.git 

cd Rule-Engine-Ast 
 

### Install the dependencies: 

npm install 

 ### backend

 cd backend

 npm start

 ### frontend

 cd frontend

 npm start
 

The server will start and listen on http://localhost:3000, where your_port is the port number specified in your server.js file . 

## API Endpoints 

1. Create Individual Rules 

Endpoint: POST /create 

Description: Creates a new rule and returns its AST representation. 

Request Body: 

json 

{ 
    "rule_string": "age > 18" 
} 
 

Response: Returns the AST of the created rule. 

### Example Request: 

curl -X POST http://localhost:3000/create -H "Content-Type: application/json" -d '{"rule_string": "age > 18"}' 
 

2. Combine Rules 

Endpoint: POST /combine 

Description: Combines multiple rules into a single AST. 

Request Body: 

json 

{ 
    "rules": ["age > 18", "income < 50000"] 
} 
 

Response: Returns the combined AST of the provided rules. 

### Example Request: 

curl -X POST http://localhost:3000/combine -H "Content-Type: application/json" -d '{"rules": ["age > 18", "income < 50000"]}' 
 

3. Evaluate Rules 

Endpoint: POST /evaluate 

Description: Evaluates the given AST against specified data and returns the result. 

Request Body: 

json 

{ 
    "ast": { /* your combined AST here */ }, 
    "data": { "age": 25, "income": 40000 } 
} 
 

Response: Returns the evaluation result (true or false). 

### Example Request: 

curl -X POST http://localhost:5000/evaluate -H "Content-Type: application/json" -d '{"ast": { /* your combined AST */ }, "data": {"age": 25, "income": 40000}}' 
 

## Error Handling 

The API provides meaningful error messages for invalid inputs: 

If required fields are missing or improperly formatted, a 400 Bad Request status will be returned with an error message. 

## Testing the API 

You can test the API endpoints using tools like Thunder Client or Postman. Follow the instructions provided in the respective sections above. 

### Example Testing Using Thunder Client 

Create Rule: 

Set up a POST request to http://localhost:3000/create with a JSON body containing the rule. 

Combine Rules: 

Set up a POST request to http://localhost:3000/combine with a JSON body containing an array of rules. 

Evaluate Rules: 

Set up a POST request to http://localhost:3000/evaluate with a JSON body containing the AST and data for evaluation. 



## Sample Output

rule : age>30 AND department = 'Sales'

data :

 age:36
 
 department: Marketing

 result:Not eligible

![image](https://github.com/user-attachments/assets/ab80323e-8bca-4ee1-a121-eddf4b89e297)

![image](https://github.com/user-attachments/assets/0856a7d4-761d-44c1-8c43-846c6326745a)


## Contributing

Feel free to submit issues or pull requests for improvements. Contributions are welcome!

## License

This project is licensed under the MIT License.



