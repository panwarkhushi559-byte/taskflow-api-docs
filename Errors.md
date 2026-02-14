# Error Handling

The TaskFlow API uses standard HTTP status codes to indicate whether a request was successful or failed.

Understanding these responses helps developers debug issues quickly.

---

## Standard HTTP Status Codes

| Status Code | Meaning |
|-------------|----------|
| 200 | Request successful |
| 201 | Resource created successfully |
| 400 | Bad request (invalid input) |
| 401 | Unauthorized (missing or invalid API key) |
| 404 | Resource not found |
| 500 | Internal server error |

---

## Error Response Format

When an error occurs, the API returns a structured JSON response:

{
  "success": false,
  "error": {
    "code": 400,
    "message": "Invalid request data."
  }
}

---

## Common Errors Explained

### 400 – Bad Request
Occurs when required fields are missing or incorrectly formatted.

Solution:
- Check request body fields
- Verify JSON structure
- Ensure required parameters are included

---

### 401 – Unauthorized
Occurs when the API key is missing or invalid.

Solution:
- Verify Authorization header
- Ensure correct API key format:
  Authorization: Bearer YOUR_API_KEY

---

### 404 – Not Found
Occurs when the requested resource does not exist.

Solution:
- Check task_id
- Confirm resource exists in system

---

### 500 – Internal Server Error
Occurs when something unexpected happens on the server.

Solution:
- Retry the request
- Contact API support if issue persists
