# StaffSync — Modern Human Resource Management System

StaffSync is a web-based Human Resource Management System (HRMS) built with the MERN ecosystem. It brings common HR workflows into one application, including employee records, attendance, leave requests, payroll records, and role-based dashboards.

> **Project note:** This repository is a customized version of an existing HRMS codebase. Before publishing, make sure you have permission to reuse the original code and comply with its license/attribution requirements. Update this note with the original source/author if applicable. Do not claim third-party code as entirely your own.

---

## Key Features

- **Role-based access control (RBAC):** Admin, HR, and Employee roles with protected frontend routes and backend middleware.
- **Employee management:** Create, view, edit, activate/deactivate employee records, and assign salaries.
- **Attendance tracking:** Punch-in/punch-out functionality, regularization requests, and date-filtered attendance history.
- **Leave management:** Submit leave requests, view leave balances and status history, and review/approve/reject requests.
- **Payroll & Payslips:** Monthly payroll generation, payslip PDF rendering and downloads using PDFKit.
- **Role-specific dashboards:** Tailored metrics and quick actions for Admin, HR, and Employees.
- **Authentication & Security:** JWT-based stateless authentication, bcrypt password hashing, and protected endpoints.

---

## Technology Stack

- **Frontend:**
  - React 18
  - TypeScript
  - Vite (fast build tool and dev server)
  - Tailwind CSS (responsive styling)
  - Zustand (state management)
  - React Router DOM v6 (routing)
  - React Hook Form & Zod (form validation)
  - Axios (HTTP client)
  - Lucide React (modern icon library)
  - Date-fns & React Hot Toast
- **Backend:**
  - Node.js & Express.js (ES modules)
  - MongoDB with Mongoose ODM
  - JSON Web Tokens (`jsonwebtoken`)
  - `bcryptjs` for secure password hashing
  - `pdfkit` for payslip generation
  - `dotenv` & `cors`
- **Database:**
  - MongoDB (local or MongoDB Atlas cloud)

---

## Project Structure

```text
StaffSync/
├── .env.example
├── .gitignore
├── README.md
├── backend/
│   ├── .env.example
│   ├── .gitignore
│   ├── package.json
│   ├── package-lock.json
│   ├── setup-env.js
│   ├── start-server.js
│   ├── controllers/
│   ├── middleware/
│   ├── routes/
│   └── src/
│       ├── config/
│       │   └── database.js
│       ├── controllers/
│       │   ├── attendanceController.js
│       │   ├── authController.js
│       │   ├── employeeController.js
│       │   ├── leaveController.js
│       │   └── payrollController.js
│       ├── middleware/
│       │   └── auth.js
│       ├── models/
│       │   ├── Attendance.js
│       │   ├── Employee.js
│       │   ├── Leave.js
│       │   ├── Payroll.js
│       │   └── User.js
│       ├── routes/
│       │   ├── adminRoutes.js
│       │   ├── attendanceRoutes.js
│       │   ├── authRoutes.js
│       │   ├── employeeRoutes.js
│       │   ├── leaveRoutes.js
│       │   └── payrollRoutes.js
│       ├── scripts/
│       │   ├── createAdmin.js
│       │   ├── createAllUsers.js
│       │   └── createHR.js
│       ├── utils/
│       │   └── generateToken.js
│       └── server.js
└── frontend/
    ├── .gitignore
    ├── index.html
    ├── package.json
    ├── package-lock.json
    ├── postcss.config.js
    ├── tailwind.config.js
    ├── tsconfig.json
    ├── tsconfig.node.json
    ├── vite.config.ts
    └── src/
        ├── api/
        │   ├── admin.ts
        │   ├── attendance.ts
        │   ├── auth.ts
        │   ├── axios.ts
        │   ├── employees.ts
        │   ├── leaves.ts
        │   └── payroll.ts
        ├── components/
        │   ├── ui/
        │   ├── ErrorBoundary.tsx
        │   ├── ProtectedRoute.tsx
        │   └── Sidebar.tsx
        ├── layout/
        │   ├── AdminLayout.tsx
        │   ├── EmployeeLayout.tsx
        │   └── HRLayout.tsx
        ├── pages/
        │   ├── admin/
        │   ├── auth/
        │   ├── employee/
        │   └── hr/
        ├── store/
        │   └── authStore.ts
        ├── utils/
        │   └── cn.ts
        ├── AdminDashboard.tsx
        ├── App.tsx
        ├── index.css
        └── main.tsx
```

---

## Requirements

- **Node.js:** v18.0.0 or higher
- **npm:** v9.0.0 or higher
- **Database:** MongoDB Atlas account or local MongoDB instance (`mongodb://localhost:27017/staffsync`)
- **OS:** Windows 10/11, macOS, or Linux
- **Browser:** Modern web browser (Chrome, Edge, Firefox, Safari)

---

## Environment Variables

A template file `.env.example` is provided in both the project root and `backend/`.

### Backend Configuration (`backend/.env`)

| Variable | Description | Default / Example |
| :--- | :--- | :--- |
| `PORT` | The port the Express server listens on | `5000` |
| `MONGODB_URI` | MongoDB connection URI string | `mongodb://localhost:27017/staffsync` |
| `JWT_SECRET` | Secret key used to sign and verify JSON Web Tokens | *Random 64-char string* |
| `JWT_EXPIRE` | Expiry duration for authentication tokens | `7d` |
| `NODE_ENV` | Application environment (`development` / `production`) | `development` |

> ⚠️ **Security Warning:** Never commit `.env` files to source control. Always use strong, randomly generated secrets in production environments.

---

## Local Setup & Installation

### 1. Clone the repository

```bash
git clone https://github.com/vidhika22/StaffSync.git
cd StaffSync
```

### 2. Configure and run the Backend

```bash
cd backend
npm install
```

Create a `backend/.env` file:

```bash
# On Windows PowerShell:
Copy-Item .env.example .env

# On macOS/Linux:
cp .env.example .env
```

Update `backend/.env` with your MongoDB connection string and a secret key:

```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/staffsync
JWT_SECRET=replace_with_a_long_random_secret
JWT_EXPIRE=7d
NODE_ENV=development
```

*(Optional)* Seed default administrator and HR accounts into the database:

```bash
node src/scripts/createAllUsers.js
```

Default credentials created by the seed script:
- **Admin:** `admin@staffsync.local` / `admin123`
- **HR:** `hr@staffsync.local` / `123456`

*(Remember to update these credentials immediately after first login!)*

Start the backend API server:

```bash
# Development mode with nodemon:
npm run dev

# Or standard start:
npm start
```

The backend server will run on `http://localhost:5000`. You can verify it via `http://localhost:5000/api/health`.

### 3. Configure and run the Frontend

Open a new terminal window or tab and navigate to the `frontend/` directory:

```bash
cd frontend
npm install
npm run dev
```

The Vite development server will start (default: `http://localhost:3000`).
Open the displayed URL in your browser to access the StaffSync application.

---

## Deployment Guide

### 1. Database (MongoDB Atlas)

1. Create a free cluster on [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).
2. Under **Database Access**, create a database user and generate a secure password.
3. Under **Network Access**, add IP address `0.0.0.0/0` (allow access from anywhere) or whitelist your hosting provider's IPs.
4. Click **Connect** > **Drivers** > copy the connection string:
   ```text
   mongodb+srv://<username>:<password>@cluster0.xxxxx.mongodb.net/staffsync?retryWrites=true&w=majority
   ```

### 2. Backend Deployment (Render / Railway)

#### Deploying on Render:
1. Connect your GitHub repository `https://github.com/vidhika22/StaffSync`.
2. Create a new **Web Service**:
   - **Root Directory:** `backend`
   - **Environment:** `Node`
   - **Build Command:** `npm install`
   - **Start Command:** `npm start`
3. Under **Environment Variables**, add:
   - `PORT`: `5000` (or leave default, Render sets `PORT` automatically)
   - `NODE_ENV`: `production`
   - `MONGODB_URI`: `<your MongoDB Atlas connection string>`
   - `JWT_SECRET`: `<your generated random 64-char secret>`
   - `JWT_EXPIRE`: `7d`
4. Deploy the service and note your live backend URL (e.g., `https://staffsync-api.onrender.com`).

### 3. Frontend Deployment (Vercel / Netlify)

#### Deploying on Vercel:
1. Import your GitHub repository into [Vercel](https://vercel.com).
2. Set the **Root Directory** to `frontend`.
3. Framework Preset: **Vite**.
4. Build Command: `npm run build`.
5. Output Directory: `dist`.
6. Configure API proxy or rewrite if needed:
   Add a `vercel.json` in `frontend/` if you want Vercel to route `/api/*` directly to your backend:
   ```json
   {
     "rewrites": [
       { "source": "/api/(.*)", "destination": "https://<your-backend-url>/api/$1" },
       { "source": "/(.*)", "destination": "/index.html" }
     ]
   }
   ```
7. Click **Deploy**.

---

## Security & Best Practices

- Real `.env` files, database connection strings, credentials, and tokens are ignored by `.gitignore` and must never be committed.
- Sensitive environment variables are kept safe with placeholder `.env.example` templates.
- Passwords are encrypted with `bcryptjs` using 10 salt rounds before storage.
- All admin, HR, and employee API endpoints require valid JSON Web Tokens in the `Authorization: Bearer <token>` header.

---

## License

This project is licensed under the ISC License. Refer to third-party packages and asset authors for respective licenses and attributions.
