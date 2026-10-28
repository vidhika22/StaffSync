# StaffSync – Modern Human Resource Management System

StaffSync is a web-based Human Resource Management System (HRMS) built using the MERN stack. It helps organizations manage employee information and streamline HR operations through a centralized dashboard.

## 🚀 Features

- **Dashboard:** View employee statistics and HR activity.
- **Employee Management:** Manage employee records and information.
- **Attendance Management:** Track employee attendance.
- **Leave Management:** Submit, review, and manage leave requests.
- **Payroll Management:** Organize employee payroll information.
- **Recruitment:** Manage recruitment-related information.
- **Reports:** Access HR-related summaries and statistics.
- **Settings:** Manage application settings.
- **Database Integration:** Store application data using MongoDB.
- **Responsive Interface:** Access the application through a modern web interface.

*Note: Features may depend on the current implementation and configuration of the application.*

## 🛠️ Technology Stack

### Frontend
- React.js
- TypeScript
- HTML5
- CSS3
- JavaScript
- Vite

### Backend
- Node.js
- Express.js
- REST APIs

### Database
- MongoDB
- MongoDB Atlas

### Development Tools
- Visual Studio Code
- npm
- Git and GitHub
- Postman (for API testing)

## 📁 Project Structure

```text
StaffSync/
├── backend/
│   ├── package.json
│   └── server.js
├── frontend/
│   ├── src/
│   ├── public/
│   └── package.json
├── .gitignore
└── README.md
```

*The exact files and folders may vary depending on the current project version.*

## 💻 System Requirements

- Windows 10/11, macOS, or Linux
- Node.js and npm
- MongoDB Atlas account or a local MongoDB installation
- Visual Studio Code or another code editor
- A modern web browser

## ⚙️ Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/vidhika22/StaffSync.git
cd StaffSync
```

### 2. Set up the backend

```bash
cd backend
npm install
```

Configure the backend environment variables in a local `.env` file according to the variables required by the application.

Example:

```env
PORT=5000
MONGODB_URI=your_mongodb_connection_string
```

Use the actual variable names expected by the backend code. Never commit your real database credentials or secrets.

Start the backend using the command configured in your `backend/package.json`. If the project uses `server.js` directly, run:

```bash
node server.js
```

### 3. Set up the frontend

Open a new terminal from the project root and run:

```bash
cd frontend
npm install
npm run dev
```

Open the local URL displayed by Vite in your terminal, usually `http://localhost:5173`.

## 🔐 Security

- Keep database credentials and secret keys private.
- Store sensitive configuration in environment variables.
- Do not upload `.env` files containing real credentials.
- Use appropriate authentication and authorization controls for protected HR data.

## 🎯 Project Objective

The objective of StaffSync is to simplify HR operations by bringing employee information and common human resource workflows into one centralized application.

## 👩‍💻 Author

**Vidhika Laad**

GitHub: [@vidhika22](https://github.com/vidhika22)

## 📄 License

A license has not yet been specified. Add an appropriate license after deciding how you want others to use and distribute this project.
