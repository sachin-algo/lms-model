# Algoleap Lead Management System (LMS)

Algoleap LMS is a high-fidelity CRM (Customer Relationship Management) and Opportunity Management platform. It provides a robust interface for managing leads, accounts, contacts, and pipeline deals efficiently.

## 🚀 Tech Stack

### Frontend (`/web`)
- **React.js** (via **Vite**) for fast, modern UI development.
- **Tailwind CSS** for comprehensive utility-first styling.
- **React Router** for seamless single-page application navigation.
- **Lucide React** for beautiful, consistent iconography.
- **Axios** for API requests.

### Backend (`/api`)
- **Node.js & Express.js** for a lightweight, fast REST API.
- **Prisma ORM** for type-safe database access and schema management.
- **PostgreSQL** (hosted on **Supabase**) as the primary database.
- **Bcrypt & JWT** for secure user authentication and session management.

---

## 📁 Project Structure

```
lms-model/
│
├── web/                  # Frontend React Application (Vite)
│   ├── src/
│   │   ├── components/   # Reusable UI elements and Forms
│   │   ├── pages/        # Main route views (Dashboard, Pipeline, etc.)
│   │   └── App.jsx       # Routing and layout wrapping
│   └── .env              # Frontend environment variables (VITE_API_URL)
│
├── api/                  # Backend Node/Express Application
│   ├── prisma/           # Prisma schema and database seeds
│   ├── src/
│   │   ├── controllers/  # API route logic and database interactions
│   │   ├── routes/       # Express route definitions
│   │   └── server.js     # Express app entry point
│   └── .env              # Backend secrets (DATABASE_URL, JWT_SECRET, etc.)
│
└── archive/              # (Ignored) Old temporary scripts and design specs
```

---

## 🛠️ Local Setup Instructions

### 1. Database Configuration
Ensure you have a PostgreSQL database (like Supabase) ready. 
Inside the `/api` directory, create a `.env` file based on `.env.example` and set your `DATABASE_URL`.

### 2. Backend Setup (`/api`)
Open a terminal and navigate to the `api` folder:
```bash
cd api
npm install
```
Push the database schema to your database:
```bash
npx prisma db push
```
Seed the database with initial admin users and roles:
```bash
npm run db:seed
```
Start the backend server:
```bash
npm start
```
*(The backend typically runs on `http://localhost:4000`)*

### 3. Frontend Setup (`/web`)
Open a second terminal and navigate to the `web` folder:
```bash
cd web
npm install
```
Ensure your `web/.env` contains the correct API URL pointing to your backend:
```env
VITE_API_URL=http://localhost:4000/api
```
Start the frontend development server:
```bash
npm run dev
```
*(The frontend typically runs on `http://localhost:5173` or `http://localhost:5174`)*

---

## 🚀 Deployment

- **Backend:** Designed to be deployed on platforms like **Render**, **Railway**, or **Heroku** as a Node Web Service. Be sure to run `npx prisma generate` in your build step to ensure the ORM is ready.
- **Frontend:** Designed to be deployed on static hosting platforms like **Vercel** or **Netlify**. Ensure your backend URL is provided as an environment variable (`VITE_API_URL`) in your deployment dashboard.
