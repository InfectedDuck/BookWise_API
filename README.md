# Bookshop Express Application

## Overview
The project leverages Express server to seamlessly incorporate CRUD functionalities via HTTP methods, tested efficiently with Postman. Emphasizing security, Session and JWT authentication are integrated to exclusively permit authenticated users for specific operations. The code is optimized through the adoption of Promises, Callbacks, or Async/Await functions, facilitating concurrent interactions by multiple users without dependencies on each other's operations.

## Features

- Retrieve a list of all books available in the bookshop
- Search for specific books and retrieve their details based on the book’s ISBN code, author names and titles
- Retrieve reviews/comments for specified books
- Register as a new user of the application
- Login to the application
- Add a new review for a book (logged in users only)
- Modify a book review (logged in users can modify only their own reviews)
- Delete a book review (logged in users can delete only their own reviews)
- (Multiple users) Access the application at the same time to view and manage different book reviews simultaneously
  
## Tech Stack

- **Express.js**: Web application framework for Node.js.
- **jsonwebtoken**: Library for creating and verifying JSON Web Tokens.
- **express-session**: Middleware for session management.
- **nodemon**: Utility for auto-reloading the server during development.


## Installation
### Prerequisites

Ensure you have [Node.js](https://nodejs.org/) and [npm](https://www.npmjs.com/) installed on your machine.

### Clone the Repository

```bash
git clone https://github.com/yourusername/bookshop-express.git
cd bookshop-express
```

### Install Dependencies
```bash
npm install
```

### Start the Application
```bash
npm start
```

The server will start on http://localhost:5000.

# API Endpoints

## User Management

### `POST /customer/register`
- **Description**: Register a new user.
- **Request Body**:
  ```json
  {
    "username": "string",
    "password": "string"
  }
  ```

### `POST /customer/login`
- **Description**: Login a new user.
- **Request Body**:
  ```json
  {
    "username": "string",
    "password": "string"
  }
  ```

## Routes

### Public Routes

- **GET /**: Get the list of all books.
- **GET /isbn/:isbn**: Get details of a book by ISBN.
- **GET /author/:author**: Get books by a specific author.
- **GET /title/:title**: Get books by title.
- **GET /review/:isbn**: Get reviews for a book by ISBN.

### Authenticated Routes

- **PUT /customer/auth/review/:isbn**: Add a review for a book (requires login).  
  **Request Body:**
  ```json
  {
    "review": "string"
  }
  
- **DELETE /customer/auth/review/:isbn**: Delete a review for a book (requires login).
