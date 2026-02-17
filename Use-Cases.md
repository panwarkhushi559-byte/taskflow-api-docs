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

```json
{
  "title": "Finish project documentation",
  "priority": "high"
}
