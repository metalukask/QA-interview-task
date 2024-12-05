
# Fullstack Web Application with React and Node.js

This project contains a React frontend and a Node.js backend.


#

## Step 1: Clone the repository
```bash
git clone https://github.com/metalukask/QA-interview-task
```

## Step 2: Docker setup
### Prerequisites

- Docker installed

### Build and start application
1. build application
   ```shell
   docker compose build
   ```

2. run application
   ```shell
   docker compose up -d
   ```
3. stop application (once finished)
   ```shell
   docker compose down
   ```

## Step 3 alternative setup without docker

### Prerequisites
- Node.js (v14 or higher)
- npm (v6 or higher)

###  Set up the Backend (Node.js)
1. Navigate to the `/server` directory:
   ```shell
   cd server
   ```
2. Install dependencies:
   ```shell
   npm install
   ```
3. Start the backend server:
   ```shell
   npm start
   ```
   The server will run at `http://localhost:8000`.

### Set up the Frontend (React)
1. Navigate to the `/client` directory:
   ```shell
   cd client
   ```
2. Install dependencies:
   ```shell
   npm install
   ```
3. Start the React app:
   ```shell
   npm start
   ```
   The React app will run at `http://localhost:3000`.

## Step 4: Login Credentials
- **Username**: `admin`
- **Password**: `admin321`

After logging in, you will be redirected to the homepage, where you can navigate to other pages.

---

### Endpoints:
- **POST /login**: Authenticate the user and return a JWT token.
- **GET /home**: Protected route, only accessible with a valid JWT token.

---

### Troubleshooting
- If the React app is not connecting to the backend, ensure that both the frontend and backend are running simultaneously.
- Make sure the backend is running on port `8000`, and the frontend is on port `3000`.

---

### Disclaimer
- Web Application Created by QA Engineer Using AI. 

This website was developed as part of an assignment for conducting QA Engineer interviews.
The website was created by a QA Engineer using Artificial Intelligence (AI) tools to simulate a real-world 
web application for interview purposes. The purpose of this project is to demonstrate practical 
examples of how QA Engineers can use Cypress for UI testing, API testing, and automation, as well as to 
evaluate candidates' skills in writing and executing automated test cases.

Note: The AI-generated content, including code and components, is intended for educational, testing, and development purposes.

---

### License
This project is licensed under the MIT License.