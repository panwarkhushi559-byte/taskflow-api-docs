# Use Cases

This document describes common real-world scenarios where developers use the TaskFlow API.

Each use case explains the problem, the API workflow, and the expected outcome.

---

## Use Case 1: Creating Tasks in a Productivity Application

### Scenario
A developer is building a productivity app where users can create and manage daily tasks.

When a user adds a new task, the application sends a request to the TaskFlow API to store it.

### API Workflow
1. User enters task details in the app.
2. Application sends a POST request to the API.
3. API validates the request.
4. API creates the task and returns task data.

### Example Request
POST /tasks
## Use Case 2: Updating Task Status

### Scenario
A user completes a task in a productivity application and marks it as finished.

The application updates the task status using the TaskFlow API.

### API Workflow
1. The application already has the task ID from a previous request.
2. The user marks the task as completed.
3. The application sends a PUT request with the updated status.
4. The API updates the task and returns the modified task data.

### Example Request
PUT /tasks/{task_id}

```json
{
  "status": "completed"
}


```json
{
  "title": "Finish project documentation",
  "priority": "high"
}
Use Case 3: Error Recovery and Invalid Requests
Scenario
A developer integrates the TaskFlow API into an application. During usage, the application sends an invalid request or references a task that does not exist.

The API responds with an error, and the application must handle it gracefully.

Scenario A: Updating a Non-Existent Task
Problem
The application attempts to update a task using an incorrect or deleted task ID.

API Workflow
Application sends a PUT request with an invalid task ID.
The API cannot find the task.
The API returns a 404 Not Found error.
Example Request
PUT /tasks/invalid_task_id

{
  "status": "completed"
}

