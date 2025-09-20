# Task-Forge

A web-based task management application where users can register, log in, and manage tasks organized by project. Tasks can be added, edited, deleted, and are displayed in order of priority.

## Tech Stack
- React.js
- Node.js

## Requirements
- Use JWT for user authentication in backend routes (Protect routes with middleware that verifies the `Authorization` header).
- Categorize tasks by project ID and fetch accordingly (Use URL params to specify project).
- Display tasks sorted by priority on the client (Use `Array.sort` in React before rendering).

## Installation

1. Clone the repository:
   bash
   git clone https://github.com/your-username/Task-Forge.git
   cd Task-Forge
   
2. Backend setup:
   bash
   cd backend
   npm install
   
3. Create a `.env` file in the `backend` folder with:
   env
   PORT=5000
   JWT_SECRET=your_jwt_secret_here
   
4. Frontend setup:
   bash
   cd ../frontend
   npm install
   
5. Create a `.env` file in the `frontend` folder with:
   env
   REACT_APP_API_URL=http://localhost:5000/api
   

## Usage

1. Start the backend server:
   bash
   cd backend
   npm run dev
   
2. Start the React development server:
   bash
   cd ../frontend
   npm start
   
3. Open your browser at `http://localhost:3000` to access Task-Forge.

## Implementation Steps

1. Initialize the Node.js project and install dependencies (`express`, `jsonwebtoken`, `cors`, etc.).
2. Create authentication routes (`/api/auth/register`, `/api/auth/login`) using JWT to issue tokens.
3. Build middleware to verify JWT tokens on protected routes.
4. Define task routes under `/api/projects/:projectId/tasks` for CRUD operations.
5. In backend controllers, filter tasks by `projectId` from URL params.
6. Initialize the React app with `create-react-app`.
7. Implement authentication context/hooks to store and send JWT in headers on requests.
8. Build project and task components; fetch tasks using `fetch` or `axios` with the project ID.
9. Sort tasks by a `priority` field in React using `Array.sort` before rendering.
10. Style the UI and add form validation for task management.

## API Endpoints

- POST `/api/auth/register`  — Register a new user.
- POST `/api/auth/login`     — Authenticate and receive a JWT token.
- GET `/api/projects/:projectId/tasks`    — Retrieve tasks for a project.
- POST `/api/projects/:projectId/tasks`   — Create a new task in a project.
- GET `/api/tasks/:taskId`    — Retrieve a single task by ID.
- PUT `/api/tasks/:taskId`    — Update a task.
- DELETE `/api/tasks/:taskId` — Delete a task.