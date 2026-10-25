# Chat-app

Real-time one-to-one chat. Sign up, search for people, and message them — new messages and who's online update
instantly over WebSockets.

![React](https://img.shields.io/badge/React-0F2540?style=flat-square&logo=react&logoColor=61DAFB)
![Socket.io](https://img.shields.io/badge/Socket.io-0F2540?style=flat-square&logo=socketdotio&logoColor=white)
![Express](https://img.shields.io/badge/Express-0F2540?style=flat-square&logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-0F2540?style=flat-square&logo=mongodb&logoColor=47A248)

## Features

- **Auth** — sign up / log in, password hashed with bcrypt, JWT on protected routes
- **People** — sidebar of conversations and a user search
- **Messages** — send and load a conversation's history, stored in MongoDB
- **Live presence** — Socket.io broadcasts who is online (`getOnlineUsers`)

## Stack

| Part | Tech |
| --- | --- |
| Frontend (`frontend/`) | React + Vite, Zustand, React Router, Tailwind CSS, axios, socket.io-client |
| Backend (`backend/`) | Node.js, Express, Socket.io, MongoDB + Mongoose, JWT, bcryptjs |

## API

| Method | Route | What it does |
| --- | --- | --- |
| POST | `/api/auth/signup` | Create an account |
| POST | `/api/auth/login` | Log in, returns a JWT |
| GET | `/api/users` | Users for the sidebar (protected) |
| GET | `/api/users/search` | Search users (protected) |
| GET | `/api/messages/:id` | Conversation with a user (protected) |
| POST | `/api/messages/send/:id` | Send a message (protected) |

## Run it locally

```bash
# backend — create backend/.env with PORT, MONGO_URI, JWT_SECRET
cd backend && npm install && npm run dev

# frontend (another terminal)
cd frontend && npm install && npm run dev
```
