
# 💬 Real-Time Chat System

A scalable real-time chat application built using WebSockets (Socket.IO), designed with an event-driven architecture and production-ready backend practices.

---

## 🚀 Features

- 🔐 JWT-based Authentication
- 💬 Real-time messaging using WebSockets
- 👥 One-to-one & room-based chat
- 📦 Message persistence with PostgreSQL
- 📁 File sharing support
- ⚡ Event-driven architecture
- 🐳 Dockerized services (DB + app)
- 📊 Swagger API documentation

---

## 🧠 System Design Overview

This application follows an **event-driven architecture** using WebSockets:

- Client connects via Socket.IO
- Server authenticates using JWT
- Events handled:
  - `msg_send` → send message
  - `msg_receive` → receive message
  - `msg_send:file` → send files

Messages are:
1. Validated
2. Stored in DB
3. Emitted to recipient in real-time

---

## 🏗️ Tech Stack

### Backend
- Node.js
- TypeScript
- Socket.IO
- Express / NestJS

### Database
- PostgreSQL
- db-migrate

### DevOps
- Docker
- Docker Compose

### Tools
- Swagger
- Nodemon

---

## ⚙️ Setup Instructions

### 1️⃣ Clone the repository

```bash
git clone https://github.com/Mm240/real-time-chat-system.git
cd real-time-chat-system
2️⃣ Install dependencies
npm install
3️⃣ Setup environment variables
cp .env.sample .env

Update values like:

DB credentials
JWT secret
4️⃣ Start Docker services
docker-compose up
5️⃣ Run database migrations
npm run up
6️⃣ Start the server
npm run start:dev
🌐 API Documentation

Swagger available at:

http://localhost:PORT/swagger
🔌 WebSocket Endpoint
ws://localhost:PORT/chat
Headers:
Authorization: Bearer <JWT_TOKEN>
📡 Socket Events
Send Message
{
  "room": "room-id",
  "interlocutorId": 2,
  "message": "Hello!"
}
Receive Message
{
  "id": 10,
  "room": "room-id",
  "message": "Hello!",
  "from": 4,
  "to": 2
}
Send File
{
  "room": "room-id",
  "interlocutorId": 2,
  "file": "file-content",
  "extension": "txt"
}
📈 Future Improvements
🟢 Online/offline presence tracking
✍️ Typing indicators
📩 Read receipts
⚡ Redis pub/sub for scaling
🧵 Group chat support
🎯 Key Highlights
Built a real-time system using WebSockets
Implemented event-driven backend architecture
Designed scalable messaging flow
Integrated persistent storage with PostgreSQL