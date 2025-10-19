TASK_1: Java backend and REST API example

Overview

Minimal Spring Boot REST API exposing CRUD for an entity `Server` with fields: `id`, `name`, `language`, `framework`.

How to run

Prerequisites

- JDK 17+
- Maven 3.9+ in PATH (run `mvn -v` to verify)

Steps (Windows PowerShell)

1. Open PowerShell in this `TASK_1` folder.
2. Build and run the app:
   - mvn spring-boot:run
3. API will start on http://localhost:8080

Alternative: build a jar

- mvn -DskipTests package
- java -jar target/task1-api-0.0.1-SNAPSHOT.jar

MongoDB required (local)

- Install MongoDB Community Server and ensure it listens on mongodb://localhost:27017

Endpoints (Task API)

- GET /tasks               (all tasks)
- GET /tasks?id=123        (task by id or 404)
- GET /tasks?name=print    (find by name contains, 404 if none)
- PUT /tasks               (upsert task; body = Task json)
- DELETE /tasks?id=123     (delete by id)
- PUT /tasks/{id}/execute  (run command; app stores TaskExecution)

Sample Task JSON

{
  "id": "123",
  "name": "Print Hello",
  "owner": "John Smith",
  "command": "echo Hello World again!",
  "taskExecutions": []
}

Quick test (PowerShell)

- Upsert:
  - curl -Method PUT -Uri http://localhost:8080/tasks -ContentType "application/json" -Body '{"id":"123","name":"Print Hello","owner":"John Smith","command":"echo Hello World!"}'
- Get by id:
  - curl "http://localhost:8080/tasks?id=123"
- Execute:
  - curl -Method PUT -Uri http://localhost:8080/tasks/123/execute
- Find by name:
  - curl "http://localhost:8080/tasks?name=hello"


