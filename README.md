# User Authentication System

This project demonstrates a secure user authentication system that allows users to sign up, log in, and access protected routes. The system uses secure password hashing, session management, and role-based access control to ensure the safety and integrity of the user data.

## Features

- *User Registration*: Users can create an account with their email and password.
- *Secure Login*: Users can log in securely using their credentials.
- *Protected Routes*: Only authenticated users can access certain routes.
- *Password Hashing*: Passwords are securely hashed using bcrypt or similar algorithms.
- *Session Management*: Sessions are used to maintain user authentication across requests.

## Requirements

- *Node.js*,*Express.js*: For building the server.
- *bcryptjs*: For password hashing.
- *express-session*: For session management.
- *jsonwebtoken*: For token-based authentication.
- *dotenv*: For environment variable management.

## Installation

1. Clone the repository:
   ~~~
   git clone "https://github.com/Monishalakshmipathy/CODECRAFT_FS_01.git"
   ~~~
2. Navigate to the project directory:
   ~~~
   cd user-authentication
   ~~~

3. Install the dependencies:
   ~~~
   npm install
   ~~~

4. Create a .env file and configure the required environment variables:
   ~~~
   SESSION_SECRET=your_session_secret_key
   DATABASE_URL=your_database_url
   JWT_SECRET=your_jwt_secret_key (optional)
   ~~~

5. Start the server:
   ~~~
   npm start
   ~~~

6. The server will run on http://localhost:3000.

## Usage

### Registering a User

- Endpoint: POST /register
- Body (JSON):
  json
  {
    "email": "user@example.com",
    "password": "securepassword"
  }
  

  On success, the user is registered, and a session is created.

### Logging In

- Endpoint: POST /login
- Body (JSON):
  json
  {
    "email": "user@example.com",
    "password": "securepassword"
  }
  

  On success, the user is logged in, and a session token is created to manage user authentication.

### Accessing Protected Routes

- Endpoint: GET /protected
- This route is protected and requires the user to be authenticated. The user needs to have a valid session or token.

  - On success, the protected data is returned.
  - If the user is not authenticated, a 401 Unauthorized error is returned.

### User Roles (Optional)

- Admin users can have elevated access to routes or specific functionality.
- Roles can be assigned during user registration or updated via an admin panel.

## Technologies Used

- *Node.js*: Runtime environment for JavaScript.
- *Express.js*: Web framework for building the server.
- *bcryptjs*: Library for hashing passwords.
- *express-session*: Middleware for session management.
- *dotenv*: To manage environment variables.
- *jsonwebtoken*: For token-based authentication and authorization.
- *MongoDB*: For storing user data (if using NoSQL).

## Security Considerations

- Passwords are securely hashed using bcryptjs.
- Sessions are protected with a session secret to prevent session hijacking.
- Passwords and sensitive information should never be stored in plain text.

## Optional Enhancements

- Add email verification for account registration.
- Implement password reset functionality.
- Use JWT (JSON Web Tokens) for stateless authenticatio
