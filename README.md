# MOVR — Backend

Node/Express/TypeScript API for Movr, a sports & activity community app. Handles auth, events, and user data, backed by MongoDB.

- live deployed app on render: 

## About this project

Movr started as the final project for my Web Development bootcamp at WBS Coding School, built in two weeks by a two-person team. The original repo lives under https://github.com/Movr-Sportsapp . This repo is my own copy, which I've continued refining and updating independently after the bootcamp ended.

## Tech Stack

- Node.js + Express + TypeScript
- MongoDB (Atlas) + Mongoose
- Cookie-based JWT authentication (access + refresh tokens)
- bcrypt for password hashing

## Features

- Signup/login with cookie-based session (access + refresh JWT)
- Demo user seed script for quick recruiter/demo access
- CRUD for events (create, browse/filter, join/leave)
- User profile management (created/joined events)

## Team & Contribution:
- Riya Alex (github: riya1997) : Main owner and contributor of backend, additional help in Frontend
- Antonia Albrecht (github: MarlaSinger2025) : Main owner and contributor of frontend, additional help in Backend

## Getting Started

```bash
npm install
npm run dev
```

### Environment Variables

Create a `.env` file in the project root with the following:

```
MONGO_URI=your-mongodb-connection-string
NODE_ENV=development
SALT_ROUNDS=10
REFRESH_TOKEN_TTL=2592000
CLIENT_BASE_URL=http://localhost:5173 or deployed frontend URL 
ACCESS_JWT_SECRET=your-access-token-secret
```

**Variable notes:**

| Variable | Description |
|---|---|
| `MONGO_URI` | Your MongoDB connection string (e.g. from MongoDB Atlas). |
| `NODE_ENV` | `development` or `production`. |
| `SALT_ROUNDS` | Number of bcrypt salt rounds used for password hashing. |
| `REFRESH_TOKEN_TTL` | Refresh token lifetime in seconds (`2592000` = 30 days). |
| `CLIENT_BASE_URL` | URL of the frontend app, used for CORS and cookie settings. Update to your deployed frontend URL in production. |
| `ACCESS_JWT_SECRET` | Secret key used to sign access tokens. Use a long, random string — never commit the real value. Command line generation with e.g. Node.js : node -e "console.log(require('crypto').randomBytes(32).toString('hex'))" |

> ⚠️ Never commit your `.env` file. Make sure it's listed in `.gitignore`.