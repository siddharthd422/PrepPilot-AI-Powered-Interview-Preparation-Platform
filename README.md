# PrepPilot — AI-Powered Interview Preparation Platform

PrepPilot helps job seekers prepare for interviews by generating personalized interview reports and tailored resume PDFs based on their self-description, resume content, and target job description — powered by Google's Generative AI.

## 🔗 Live Demo

Link :https://preppilot-ai-ljq3.onrender.com

## ✨ Features

- **User Authentication** — Secure register/login/logout flow with JWT-based auth and token blacklisting on logout
- **AI-Generated Interview Reports** — Upload your resume and job description to receive a personalized interview preparation report
- **Resume PDF Generation** — Generates a tailored resume PDF based on your profile, resume content, and the target job description
- **Report History** — View all past interview reports tied to your account

## 🛠️ Tech Stack

**Frontend**
- React 19 + Vite
- React Router
- Axios
- Sass

**Backend**
- Node.js + Express 5
- MongoDB + Mongoose
- JWT authentication (`jsonwebtoken`, `cookie-parser`)
- Multer (in-memory file uploads)
- Puppeteer (PDF generation)
- Google Generative AI (`@google/genai`)

## 📁 Project Structure

This is a monorepo with two independently deployable apps:

```
.
├── Frontend/   # React + Vite client
└── Backend/    # Express REST API
```

## 🚀 Getting Started

### Prerequisites
- Node.js
- A MongoDB connection string
- A Google Generative AI API key

### Backend Setup

```bash
cd Backend
npm install
```

Create a `.env` file in `Backend/` with:

```
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
GOOGLE_GENAI_API_KEY=your_google_genai_api_key
PORT=3000
```

Run the server:

```bash
npm start
```

### Frontend Setup

```bash
cd Frontend
npm install
```

Create a `.env` file in `Frontend/` with:

```
VITE_API_URL=http://localhost:3000
```

Run the dev server:

```bash
npm run dev
```

## 📡 API Overview

| Method | Endpoint | Description | Access |
|---|---|---|---|
| POST | `/api/auth/register` | Register a new user | Public |
| POST | `/api/auth/login` | Log in with email and password | Public |
| GET | `/api/auth/logout` | Log out and blacklist the token | Public |
| GET | `/api/auth/get-me` | Get the current logged-in user | Private |
| POST | `/api/interview/` | Generate a new interview report from resume + job description | Private |
| GET | `/api/interview/` | Get all interview reports for the logged-in user | Private |
| GET | `/api/interview/report/:interviewId` | Get a specific interview report | Private |
| POST | `/api/interview/resume/pdf/:interviewReportId` | Generate a tailored resume PDF | Private |

## 📄 License

This project currently has no license specified.
