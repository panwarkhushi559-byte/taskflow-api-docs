# Use Cases

## Use Case 1: Creating Tasks for a Productivity App

### Scenario
A user creates a new task using the TaskFlow API.

### API Workflow
1. The application sends a POST request to `/tasks`.
2. The API validates the request body.
3. The task is created and returned in the response.

---

## Use Case 2: Updating Task Status

### Scenario
A user marks an existing task as completed.

### API Workflow
1. The application sends a PUT request to `/tasks/{task_id}`.
2. The API updates the task status.
3. The updated task is returned.

---

## Use Case 3: Error Recovery and Invalid Requests

### Scenario
A developer sends a request with an invalid task ID.

### Problem
The requested task does not exist.

### API Workflow
1. The application sends a PUT request with an invalid task ID.
2. The API returns a `404 Not Found` error.
3. The application handles the error gracefully.

### Example Request
```http
PUT /tasks/invalid_task_id
