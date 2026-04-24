# Student Team Members Management Application

A full-stack web application for adding, storing, and viewing student team members with profile image uploads.

## Tech Stack

- Frontend: React.js, React Router, Axios, CSS
- Backend: Node.js, Express.js, MongoDB, Mongoose, Multer

## Project Structure

```text
student-team-members-management-app/
|-- controllers/
|   |-- memberController.js
|-- frontend/
|   |-- public/
|   |   |-- index.html
|   |-- src/
|   |   |-- pages/
|   |   |   |-- AddMember.js
|   |   |   |-- Home.js
|   |   |   |-- MemberDetails.js
|   |   |   |-- ViewMembers.js
|   |   |-- api.js
|   |   |-- App.js
|   |   |-- index.js
|   |   |-- styles.css
|   |-- .env.example
|   |-- package.json
|-- models/
|   |-- Member.js
|-- routes/
|   |-- memberRoutes.js
|-- uploads/
|   |-- .gitkeep
|-- .env.example
|-- .gitignore
|-- package.json
|-- server.js
```

## Features

- Add a team member with name, role, email, contact, and profile image
- View all members in a card layout
- View complete details for a single member
- Upload and serve profile images from the backend
- Handle loading states, validation, and API errors

## MongoDB Connection Setup

1. Install MongoDB locally or use MongoDB Atlas.
2. Copy the backend environment file:

```bash
cp .env.example .env
```

3. Update `MONGODB_URI` inside `.env`.

Example local URI:

```env
MONGODB_URI=mongodb://127.0.0.1:27017/student-team-members
```

Example Atlas URI:

```env
MONGODB_URI=mongodb+srv://<username>:<password>@cluster.mongodb.net/student-team-members?retryWrites=true&w=majority
```

## Setup Instructions

### 1. Install backend dependencies

```bash
npm install
```

### 2. Install frontend dependencies

```bash
cd frontend
npm install
```

### 3. Configure environment variables

Backend `.env`:

```env
PORT=5000
MONGODB_URI=mongodb://127.0.0.1:27017/student-team-members
CLIENT_URL=http://localhost:3000
```

Frontend `.env`:

```env
REACT_APP_API_BASE_URL=http://localhost:5000/api
```

## How To Run The Project

### Start the backend server

From the project root:

```bash
npm run dev
```

or

```bash
npm start
```

### Start the frontend app

From the `frontend` folder:

```bash
npm start
```

Frontend URL:

```text
http://localhost:3000
```

Backend URL:

```text
http://localhost:5000
```

## API Endpoints

### Add member

- Method: `POST`
- URL: `http://localhost:5000/api/members`
- Body type: `form-data`
- Fields:
  - `name`
  - `role`
  - `email`
  - `contact`
  - `image`

### Get all members

- Method: `GET`
- URL: `http://localhost:5000/api/members`

### Get member by ID

- Method: `GET`
- URL: `http://localhost:5000/api/members/:id`

## Sample API Test URLs

- Health check: `http://localhost:5000/api/health`
- Get all members: `http://localhost:5000/api/members`
- Get one member example: `http://localhost:5000/api/members/661f3f5d8a4c7d2b12345678`

## Notes

- Uploaded images are stored in the `/uploads` folder.
- The backend serves uploaded files statically.
- Make sure MongoDB is running before starting the backend.
