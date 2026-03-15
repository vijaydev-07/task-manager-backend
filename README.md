# Task Manager API (Node.js, Express, MongoDB)

A RESTful Task Manager API built using Node.js, Express.js, and MongoDB. This project demonstrates secure CRUD operations for managing tasks with advanced authentication and role-based permissions.

---

## 🌐 Live API Endpoint

You can test this API live using the base URL provided below:
**Base URL:** https://task-manager-backend-y38o.onrender.com

---

## Features

• User Registration & Login (JWT Authentication)
• Role-Based Access Control (Admin vs User)
• Password hashing using bcrypt
• Create and manage tasks
• Update task status (mark as completed)
• Delete tasks (Restricted to Admin only)
• Protected routes using custom middleware
• RESTful API architecture
• MongoDB database integration

---

## Tech Stack

### Backend
• Node.js, Express.js, MongoDB, Mongoose

### Authentication & Security
• JSON Web Token (JWT)
• bcrypt (Password Hashing)
• Role-based Authorization (RBAC)

### Tools
• Git, GitHub, Thunder Client / Postman (API testing)

---

## Project Structure

task-manager-api/
│
├── config/
│   └── db.js                    # MongoDB database connection
│
├── Controllers/
│   ├── authControllers.js       # Authentication logic
│   └── taskControllers.js       # Task CRUD operations
│
├── Models/
│   ├── User.js                  # User schema with roles
│   └── Task.js                  # Task schema
│
├── Routes/
│   ├── authRoutes.js            # Auth endpoints
│   └── taskRoutes.js            # Task endpoints (Protected)
│
├── middleware/
│   ├── authMiddleware.js        # JWT verification
│   └── roleMiddleware.js        # Admin/User access control
│
├── .env                         # Secret environment variables
├── package.json                 # Dependencies & scripts
└── Server.js                    # Main server entry point

---

## Installation

1. Clone the repository:
git clone https://github.com/vijaydev-07/task-manager-api.git

2. Go to the project folder:
cd task-manager-api

3. Install dependencies:
npm install

4. Create a .env file:
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key

5. Start the server:
npm start

---

## API Endpoints

### Authentication
• POST /api/auth/register (Registers as 'user' by default)
• POST /api/auth/login (Returns JWT Token)

### Tasks (Protected - Requires JWT)
• GET /api/tasks (Accessible by User & Admin)
• POST /api/tasks (Accessible by User & Admin)
• PUT /api/tasks/:id (Accessible by User & Admin)
• DELETE /api/tasks/:id (Admin only)

---

## Testing the API

1. **Register/Login:** Get your JWT Token.
2. **Setup Header:** In Postman/Thunder Client, go to 'Auth' and select 'Bearer Token'.
3. **Role Check:** Users can manage tasks, but only users with `role: "admin"` in the database can perform DELETE operations.

---

## Author

Vijay Dinanath Harijan