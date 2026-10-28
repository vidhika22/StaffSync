# StaffSync — Modern Human Resource Management System

StaffSync is a web-based Human Resource Management System (HRMS) built with the MERN ecosystem. It brings common HR workflows into one application, including employee records, attendance, leave requests, payroll records, and role-based dashboards.

> **Project note:** This repository is a customized version of an existing HRMS codebase. Before publishing, make sure you have permission to reuse the original code and comply with its license/attribution requirements. Update this note with the original source/author if applicable. Do not claim third-party code as entirely your own.

## Key features

- **Role-based access:** Admin, HR, and Employee experiences with protected routes.
- **Employee management:** Create and maintain employee records.
- **Attendance:** Punch-in/punch-out and attendance history.
- **Leave management:** Submit leave requests, view balances/history, and review requests where authorized.
- **Payroll:** Payroll records and payslip PDF support.
- **Dashboards:** Role-specific views for HR/admin and employees.
- **Authentication:** JWT-based authentication and hashed passwords.

Feature availability depends on the current implementation and configured database.

## Technology stack

- **Frontend:** React 18, TypeScript, Vite, Tailwind CSS
- **Backend:** Node.js, Express.js
- **Database:** MongoDB with Mongoose
- **Authentication/security:** JSON Web Tokens (JWT), bcrypt
- **Other tools:** Axios, React Router, Zustand, React Hook Form, Zod, PDFKit

## Project structure

```text
StaffSync/
├── backend/
│   ├── src/
│   │   ├── config/
│   │   ├── controllers/
│   │   ├── middleware/
│   │   ├── models/
│   │   ├── routes/
│   │   └── server.js
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── api/
│   │   ├── components/
│   │   ├── layout/
│   │   └── pages/
│   └── package.json
└── README.md
```

## Requirements

- Windows 10/11, macOS, or Linux
- Node.js 18 or newer and npm
- MongoDB Atlas account or a local MongoDB instance
- Visual Studio Code (recommended)
- A current browser such as Chrome or Firefox
- Recommended: 8 GB RAM or more and at least 1 GB of free disk space

## Run locally

### 1. Clone or download the repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd StaffSync
```

### 2. Configure the backend

```bash
cd backend
npm install
```

Create a `backend/.env` file (do not commit this file):

```env
PORT=5000
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=replace_with_a_long_random_secret
JWT_EXPIRE=7d
NODE_ENV=development
```

Use your own MongoDB connection string and credentials. Never publish database passwords, JWT secrets, or other private environment values.

Start the backend:

```bash
npm run dev
```

The API is expected to run at `http://localhost:5000` unless you configure a different port.

### 3. Configure and run the frontend

Open a second terminal from the project root:

```bash
cd frontend
npm install
npm run dev
```

Open the local URL printed by Vite in the terminal.

## Before publishing to GitHub

1. Ensure `.env`, credentials, tokens, and private database URLs are not committed.
2. Check that the project has a suitable license and attribution for any reused code/assets.
3. Replace screenshots with screenshots of your own customized application.
4. Verify both frontend and backend run locally and update this README if commands or features differ.
5. Do not upload `node_modules`, build outputs, or personal files.

## Skills demonstrated

HTML, CSS, JavaScript/TypeScript, React, Node.js, Express.js, MongoDB, REST APIs, asynchronous JavaScript, JWT authentication, and responsive UI development.
