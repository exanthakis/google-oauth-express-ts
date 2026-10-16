# Google OAuth 2.0 Login — React & Node.js

Full-stack Google OAuth 2.0 authentication application built with **React, TypeScript, Tailwind CSS, shadcn/ui, Node.js, Express.js, MongoDB, Mongoose, and JWT**.

## 📁 Project Structure

```text
.
├── backend/
│   ├── src/
│   │   ├── config/
│   │   ├── controllers/
│   │   ├── libs/
│   │   ├── models/
│   │   ├── routes/
│   │   ├── services/
│   │   ├── types/
│   │   └── app.ts
│   ├── .env.example
│   ├── package.json
│   └── tsconfig.json
│
├── frontend/
│   ├── src/
│   │   ├── assets/
│   │   ├── components/
│   │   ├── config/
│   │   ├── lib/
│   │   ├── pages/
│   │   ├── routes/
│   │   ├── types/
│   │   ├── App.tsx
│   │   └── main.tsx
│   ├── .env.example
│   ├── package.json
│   └── tsconfig.json
│
└── README.md
```

## 🚀 Tech Stack

### Backend

- Node.js
- Express.js
- TypeScript
- MongoDB
- Mongoose
- JSON Web Token (JWT)
- `googleapis`
- Helmet
- CORS

### Frontend

- React
- TypeScript
- Tailwind CSS
- shadcn/ui
- Vite
- React Router
- axios

# 🔑 Google OAuth Setup

## 1. Create a Google Cloud Project

Go to the [Google Cloud Console](https://console.cloud.google.com/auth/clients) and create a project.

## 2. Configure OAuth Consent Screen

Configure the OAuth consent screen for your application.

For local development, configure the application for testing as required by Google.

## 3. Create OAuth Client ID

Create an **OAuth 2.0 Client ID** for a web application.

For local development, add:

```text
http://localhost:3000/api/v1/auth/google/callback
```

to the authorized redirect URIs.

## 4. Get the Client ID

Your Google Client ID will look similar to:

```text
123456789012-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx.apps.googleusercontent.com
```

Use this value in the frontend and backend environment configuration where required.

# ⚙️ Environment Variables

## Backend

Create:

```text
backend/.env
```

using:

```text
backend/.env.example
```

Example:

```env
PORT=3000

MONGODB_URI=mongodb://xxx/xxx

G_CLIENT_ID=your_google_client_id
G_CLIENT_SECRET=your_google_client_secret
G_CLIENT_REDIRECT_URL=http://localhost:3000/api/v1/auth/google/callback

CLIENT_URL=http://localhost:5173

NODE_ENV=development

# Sessions and tokens

ACCESS_TOKEN_SECRET=your_access_token_secret
REFRESH_TOKEN_SECRET=your_refresh_token_secret
SESSION_SECRET=your_session_secret

ACCESS_TOKEN_MAX_AGE=900000  # 900000 = 15 minutes
REFRESH_TOKEN_MAX_AGE=604800000 # 604800000 = 7 days
```

> Never commit your real `.env` file to Git.

# 📦 Installation

Clone the repository:

```bash
git clone <repository-url>
cd <repository-name>
```

## Backend

```bash
cd backend
npm install
```

Create the environment file:

```bash
cp .env.example .env
```

Start the backend:

```bash
npm run dev
```

Backend:

```text
http://localhost:3000
```

## Frontend

Open a new terminal:

```bash
cd frontend
npm install
```

Start the frontend:

```bash
npm run dev
```

Frontend:

```text
http://localhost:5173
```

# 🍃 MongoDB

Users are stored in MongoDB using Mongoose.

Example user document:

```json
{
  "_id": "64xxxxxxxxxxxxxxxxxxxxxx",
  "name": { "first": "Example User", "last": "Example lastName" },
  "email": "user@example.com",
  "photo": { "url": "https://example.com/avatar.jpg" },
  "createdAt": "2026-01-01T00:00:00.000Z",
  "updatedAt": "2026-01-01T00:00:00.000Z"
}
```

The actual schema can be customized based on the application's requirements.
