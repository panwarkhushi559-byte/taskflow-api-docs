# Getting Started

This guide walks you through making your first request to the TaskFlow API.

---

## Prerequisites

Before you begin, make sure you have:

- An API client (Postman recommended)
- A valid API key
- Internet connection

---

## Base URL

All API requests should be made to:

https://api.taskflow.dev/v1

---

## Step 1: Set Up Authorization

Every request must include your API key in the Authorization header.

Authorization: Bearer YOUR_API_KEY

In Postman:
1. Open your request
2. Go to the Headers tab
3. Add:
   Key: Authorization
   Value: Bearer YOUR_API_KEY

---

## Step 2: Make Your First Request

### Example: Retrieve All Tasks

Method: GET  
Endpoint: /tasks  

Full URL:
https://api.taskflow.dev/v1/tasks

---

## Example Response

[
  {
    "id": "task_101",
    "title": "Complete documentation",
    "priority": "high",
    "status": "pending"
  }
]

---

## Step 3: Create a Task

Method: POST  
Endpoint: /tasks  

Body (JSON):

{
  "title": "Prepare project portfolio",
  "priority": "medium"
}

---
## How the TaskFlow API Works

![TaskFlow API Flow](images/Screenshot 2026-02-24 184500.png)
## You're Ready

You are now ready to interact with the TaskFlow API using:
- GET to retrieve tasks
- POST to create tasks
- PUT to update tasks
- DELETE to remove tasks (if supported)
