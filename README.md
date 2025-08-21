# To-Do-Application

Description: A full-stack To-Do web application built with React, Tailwind CSS, Node.js, Express, and PostgreSQL featuring user authentication, task CRUD functionality, and private user tasks.

## Tech Stack
- Node.js & Express.js
- React
- Tailwind CSS
- PostgreSQL
- Docker

## Requirements
- Implement CRUD operations for tasks with title, description, status, due date
- Implement user authentication with signup, login, logout
- Ensure tasks are private to each user
- Create a responsive UI using React and Tailwind CSS
- Dockerize the application for deployment

## Installation
### Prerequisites
- Docker & Docker Compose (for containerized setup)
- Node.js & npm (v14+)
- PostgreSQL (if running locally)

### Clone the Repository

git clone https://github.com/your-username/to-do-application.git
cd to-do-application


### Environment Variables
Create a `.env` file in the `backend` directory:

PORT=5000
DATABASE_URL=postgresql://<username>:<password>@localhost:5432/todo_app
JWT_SECRET=your_jwt_secret

Create a `.env` file in the `frontend` directory:

REACT_APP_API_URL=http://localhost:5000/api


### Running Locally
1. Start PostgreSQL and ensure the database `todo_app` exists.
2. Backend:
   bash
   cd backend
   npm install
   npm run dev
   
3. Frontend:
   bash
   cd frontend
   npm install
   npm start
   

### Using Docker Compose
bash
docker-compose up --build


## Usage
1. Open your browser and navigate to http://localhost:3000
2. Sign up for a new account or log in.
3. Create, view, edit, and delete your private tasks from the dashboard.

## Implementation Steps
1. Initialize the `backend` folder with Express.js and configure PostgreSQL connection.
2. Define database schema and run migrations for `users` and `tasks` tables.
3. Implement authentication routes (`signup`, `login`, `logout`) using JWT and middleware.
4. Create Express routes for tasks CRUD operations, ensuring `userId` is included in queries.
5. Set up the `frontend` folder with Create React App and Tailwind CSS.
6. Build responsive components: `Login`, `Signup`, `TaskList`, `TaskForm`, and `TaskItem`.
7. Integrate Axios to communicate with backend API, handling JWT tokens in headers.
8. Implement client-side routing with React Router.
9. Write Dockerfiles for both `backend` and `frontend` services.
10. Configure `docker-compose.yml` to orchestrate services and the PostgreSQL database.

## API Endpoints
### Authentication
- POST /api/auth/signup — Register a new user
- POST /api/auth/login — Authenticate and obtain JWT
- POST /api/auth/logout — Invalidate user session

### Tasks
- GET /api/tasks — Retrieve all tasks for authenticated user
- GET /api/tasks/:id — Retrieve a single task by ID
- POST /api/tasks — Create a new task
- PUT /api/tasks/:id — Update an existing task
- DELETE /api/tasks/:id — Delete a task