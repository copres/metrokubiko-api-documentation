# MetroKUBIKO API Documentation

## Getting Started

### Introduction

Welcome to the MetroKUBIKO API documentation. This API provides various endpoints for managing and interacting with your MetroKUBIKO platform data. Before using the API, ensure you have the necessary credentials and authorization token.

### Base URL

All API requests are made to the following base URL:

'''plaintext
https://us-central1-copres-firebase.cloudfunctions.net/app-api
'''

### Authentication

To interact with the MetroKUBIKO API, you must first generate an authentication token using your email and password.

### Generate Auth Token

This endpoint generates a token using the user's email and password, which is required for authenticating subsequent requests.

| -Key-            | -Value-                                                      |
|------------------|--------------------------------------------------------------|
| **Method**       | **POST**                                                     |
| **Path**         | `/auth/get-token`                                            |
| **Headers**      | `{ 'Content-Type': 'application/json' }`                     |

### Params

'''typescript
interface Params {
    email: string;
    password: string;
}
'''

### Response

'''typescript
export type Response = {
  token: string;
  expires: Date;
}
'''

### Example Request

'''http
POST https://us-central1-copres-firebase.cloudfunctions.net/app-api/auth/get-token
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "yourPassword"
}
'''

### Example Response

'''json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "expires": "2024-09-01T00:00:00.000Z"
}
'''

### Usage

Once you have obtained the token, include it in the `Authorization` header of your requests to authenticate.

'''http
Authorization: Bearer YOUR_TOKEN_HERE
'''

With the token, you can now interact with other endpoints provided by the MetroKUBIKO API.

---

### Additional Endpoints

After obtaining the authentication token, you can explore and interact with various other endpoints of the MetroKUBIKO API. These will be covered in the subsequent sections of the documentation.
