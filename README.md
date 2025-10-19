🧱 Task 1 – Java Backend and REST API
📘 Overview

Developed a Spring Boot REST API that manages and executes “Task” objects.
Each Task represents a shell command and stores execution details in MongoDB.

🧩 Features

CRUD operations for Task objects

Search tasks by ID or name

Execute shell commands via a PUT /taskExecution/{id} endpoint

MongoDB persistence using Spring Data

Validation to prevent unsafe/malicious commands

📄 Entity Model

Task

{
  "id": "123",
  "name": "Print Hello",
  "owner": "John Smith",
  "command": "echo Hello World!",
  "taskExecutions": [
    {
      "startTime": "2025-04-21T15:51:42Z",
      "endTime": "2025-04-21T15:51:43Z",
      "output": "Hello World!"
    }
  ]
}

⚙️ Endpoints
Method	Endpoint	Description
GET	/tasks	Get all tasks
GET	/tasks/{id}	Get task by ID
GET	/tasks/find?name=	Search by name substring
PUT	/tasks	Create or update a task
DELETE	/tasks/{id}	Delete a task
PUT	/taskExecution/{id}	Run a task’s shell command
🧠 Tech Stack

Java 17

Spring Boot 3+

MongoDB

Maven

Postman / cURL for testing

🖥️ Sample Run
curl -X PUT http://localhost:8080/tasks \
  -H "Content-Type: application/json" \
  -d '{"id":"1","name":"Say Hello","owner":"Jayanth","command":"echo Hello Kaiburr!"}'
