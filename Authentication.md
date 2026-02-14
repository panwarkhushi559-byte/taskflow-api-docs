# Authentication

The TaskFlow API uses token-based authentication to secure all endpoints.

Every request must include a valid API key in the request header.

---

## API Key

To access the API, you must provide your API key using the `Authorization` header.

Authorization: Bearer YOUR_API_KEY

Replace `YOUR_API_KEY` with your actual key.

---

## Example Request

GET /tasks
Host: api.taskflow.dev
Authorization: Bearer sk_test_123456789

---

## If Authentication Fails

If the API key is missing or invalid, the API will return:

Status Code: 401 Unauthorized

Example response:

{
  "success": false,
  "error": {
    "code": 401,
    "message": "Unauthorized. Invalid or missing API key."
  }
}

---

## Security Best Practices

- Never expose your API key in public repositories.
- 
- Do not store API keys in frontend applications.
- Rotate API keys periodically.
- Use environment variables to manage secrets securely.
