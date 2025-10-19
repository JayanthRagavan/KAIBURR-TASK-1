Task 1 - Java Backend and REST API
Overview

This task involves developing a Java-based REST API application to manage "Task" objects.
Each task represents a shell command that can be executed and stored in MongoDB along with execution details.

Technologies Used

Java 17

Spring Boot Framework

MongoDB

Maven

Features Implemented

Create a new task

Get all tasks or fetch a task by ID

Delete a task

Search for tasks by name

Execute a command by task ID

Store multiple executions for each task, including start time, end time, and command output

Database Integration

All task data is stored in MongoDB.
The connection details are configured in the application.properties file.

Testing

The API was tested using Postman and cURL commands.
Screenshots of request and response results are included in the screenshots folder.
