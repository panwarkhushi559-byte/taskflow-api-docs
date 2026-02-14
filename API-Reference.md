# TaskFlow API Reference

## Overview
TaskFlow API enables developers to manage tasks within productivity applications. It supports creating, updating, retrieving, and listing task resources using RESTful endpoints.

## Base URL
https://api.taskflow.dev/v1

## Authentication
All endpoints require a valid API key in the Authorization header.

Authorization: Bearer YOUR_API_KEY

Endpoints
## POST /tasks

Creates a new task resource.

### Request Body

| Field | Type | Required | Description |
|-------|------|----------|------------|
| title | string | Yes | Title of the task |
| description | string | No | Detailed description |
| priority | string | No | low, medium, high |

### Example Request
POST /tasks
Authorization: Bearer YOUR_API_KEY
Content-Type: application/json

{
  "title": "Complete documentation",
  "priority": "high"
}

### Example Response
{
  "id": "task_101",
  "title": "Complete documentation",
  "priority": "high",
  "status": "pending"
}
## PUT /tasks/{task_id}

Updates an existing task.

### Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|------------|
| task_id | string | Yes | Unique identifier of the task |

### Example Request
PUT /tasks/task_101
Authorization: Bearer YOUR_API_KEY

{
  "status": "completed"
}

### Example Response
{
  "id": "task_101",
  "status": "completed"
}
## GET /tasks

Retrieves a list of tasks.

### Query Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|------------|
| status | string | No | Filter by task status |
| priority | string | No | Filter by priority |
| page | integer | No | Page number |
| limit | integer | No | Number of tasks per page |

### Example Request
GET /tasks?page=1&limit=10

### Example Response
[
  {
    "id": "task_101",
    "title": "Complete documentation",
    "status": "completed"
  }
]
## Error Responses

| Code | Meaning |
|------|---------|
| 400 | Invalid request |
| 401 | Unauthorized |
| 404 | Task not found |
| 500 | Internal server error |
# Authentication

TaskFlow API uses token-based authentication.

## API Key

Each request must include an API key in the Authorization header.

Authorization: Bearer YOUR_API_KEY

## Security Notes

- Keep your API key confidential.
- Do not expose keys in client-side applications.
- Rotate keys periodically for security.
- # Getting Started

This guide helps you make your first request to the TaskFlow API.

## Prerequisites

- Postman or any API client
- A valid API key

## Step 1: Set Base URL

https://api.taskflow.dev/v1

## Step 2: Add Authorization Header

Authorization: Bearer YOUR_API_KEY

## Step 3: Make Your First Request

GET /tasks

You should receive a JSON response containing task data.
# Error Handling

TaskFlow API uses standard HTTP status codes.

## Error Response Format

{
  "success": false,
  "error": {
    "code": 404,
    "message": "Task not found"
  }
}

## Common Errors

| Code | Description | Solution |
|------|------------|----------|
| 400 | Bad Request | Check required fields |
| 401 | Unauthorized | Verify API key |
| 404 | Not Found | Confirm task_id exists |
| 500 | Server Error | Retry later |
# Release Notes

## v1.1.0
- Added task filtering by priority
- Improved error response structure
- Updated authentication documentation

## v1.0.0
- Initial release
- Create, Update, and List task endpoints
- Token-based authentication
