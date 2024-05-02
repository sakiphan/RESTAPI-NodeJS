# REST API Server

This repository contains the source code for a REST API server implemented using Express.js and Mongoose for MongoDB integration. The API handles user authentication, registration, and user management functions such as retrieving user details, updating user information, and deleting users. It includes middleware for authentication and ownership checks, ensuring that users can only access and modify their own data.

## Features

- User registration and login.
- CRUD operations on user data.
- Session management using cookies.
- Enhanced security with hashed passwords and session tokens.
- Middleware for authentication and ownership validation.

## Prerequisites

- Node.js installed on your machine.
- MongoDB account and database setup.
- Properly set environment variables or `.env` file with database connection string and other configurations.

## Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/sakiphan/RESTAPI-NodejS.git
   cd RESTAPI-NodejS
## Install dependencies
 ```bash
   npm install
   ```
## Set up environment variables:
Create a .env file in the root directory and fill in your MongoDB URI and any other configurations:
```bash
MONGO_URL=your_mongodb_connection_string
SECRET=your_secret_key
```
## Running the Application
Start the server with:

```bash
   npm install
   ```
This will launch the server on http://localhost:8080/, ready to accept requests.

# API Endpoints

| HTTP Method | Endpoint           | Description                            | Authentication           |
|-------------|--------------------|----------------------------------------|--------------------------|
| POST        | /auth/register     | Register a new user.                   | Not required             |
| POST        | /auth/login        | Login an existing user.                | Not required             |
| GET         | /users             | Retrieve all users.                    | Required                 |
| DELETE      | /users/:id         | Delete a user.                         | Required (owner only)    |
| PATCH       | /users/:id         | Update user details.                   | Required (owner only)    |




```bash
curl -X POST http://localhost:8080/auth/register \
-H 'Content-Type: application/json' \
-d '{"username": "newuser", "email": "newuser@example.com", "password": "yourpassword"}'
```