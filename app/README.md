# 🚀 MERN Blog Application — Deployment & DevOps Essentials

A **fully deployed** MERN stack blog application featuring authentication, CRUD operations, image uploads, categories, comments, and complete CI/CD + monitoring setup.

---

# 📘 Overview

This project demonstrates full-stack development + DevOps skills:

* **MERN Stack (MongoDB, Express.js, React, Node.js)**
* Production-ready backend deployed on **Render**
* Optimized React frontend deployed on **Vercel**
* CI/CD automation using **GitHub Actions**
* Environment variable management for dev & production
* Monitoring, uptime checks & health endpoints

 **Features:**
  - User registration and login with JWT authentication
  - CRUD operations for blog posts
  - Category management
  - Image uploads for blog posts
  - Commenting system
  - Pagination, search, and filtering
  - Role-based access control (user/admin)
  - Slug generation for SEO-friendly URLs


---

# 📂 Project Structure

```
mern-blog/
├── client/                 # React Frontend (Vite)
│   ├── public/
│   └── src/
│       ├── components/
│       ├── pages/
│       ├── hooks/
│       ├── services/
│       ├── context/
│       └── App.jsx
│   └── package.json
│
├── server/                 # Express Backend
│   ├── config/
│   ├── controllers/
│   ├── models/
│   ├── routes/
│   ├── middleware/
│   ├── utils/
│   ├── server.js
│   └── package.json
│
└── README.md
```

---

# ⚙️ Getting Started (Local Development)

## 1️⃣ Clone The Repository

```bash
git clone https://github.com/PLP-MERN-Stack-Development/deployment-and-devops-essentials-The-Williams.git
cd deployment-and-devops-essentials-The-Williams
```

---

# 🛠 Backend Setup (`server/`)

### 2️⃣ Install Dependencies

```bash
cd server
npm install
```

### 3️⃣ Create `.env` File

Create a file at `server/.env`:

```
MONGO_URI=mongodb+srv://edgeriowilliams_db_user:Edgerio3137@mern1.sgloynp.mongodb.net/mern-blog?retryWrites=true&w=majority
PORT=5000
JWT_SECRET=mysecretjwt
```

---

# 🖥 Start Backend

```bash
cd server
npm run dev
```

API will run on:

```
http://localhost:5000/api
```

---

# 🌐 Frontend Setup (`client/`)

### 1️⃣ Install Dependencies

```bash
cd ../client
npm install
```

### 2️⃣ Start Frontend

```bash
npm run dev
```

Frontend runs on:

```
http://localhost:5173
```

---

# 🔌 API Endpoints

### 🔐 Auth

| Method | Endpoint           | Description        |
| ------ | ------------------ | ------------------ |
| POST   | /api/auth/register | Register user      |
| POST   | /api/auth/login    | Login              |
| GET    | /api/auth/me       | Get logged-in user |

### 📝 Posts

| Method | Endpoint                | Description     |
| ------ | ----------------------- | --------------- |
| GET    | /api/posts              | Get all posts   |
| GET    | /api/posts/:id          | Get single post |
| POST   | /api/posts              | Create post     |
| PUT    | /api/posts/:id          | Update post     |
| DELETE | /api/posts/:id          | Delete post     |
| POST   | /api/posts/:id/comments | Add comment     |

### 🏷 Categories

| Method | Endpoint        |
| ------ | --------------- |
| GET    | /api/categories |
| POST   | /api/categories |

---

# 🚀 Deployment

## ✅ Backend Deployment — Render

Backend URL:
**[https://deployment-and-devops-server.onrender.com](https://deployment-and-devops-server.onrender.com)**

### Steps:

1. Go to **Render → New Web Service**
2. Connect GitHub repo
3. Select:

   * Root folder: `server/`
   * Runtime: **Node**
4. Environment Variables:

```
MONGO_URI=mongodb+srv://edgeriowilliams_db_user:Edgerio3137@mern1.sgloynp.mongodb.net/mern-blog?retryWrites=true&w=majority
JWT_SECRET=mysecretjwt
PORT=10000

5. Build Command:

```
npm install
```

6. Start Command:

```
npm start
```

7. Add **Health Check**:

```
/health
```

---

## 🎨 Frontend Deployment — Vercel

Frontend URL:
**[https://deployment-and-devops-client.vercel.app](https://deployment-and-devops-client.vercel.app)**

### Steps:

1. Vercel → New Project
2. Import GitHub repo
3. Select **client** folder
4. Build command:

```
npm run build
```

5. Output directory:

```
dist
```

6. Add environment variable:

```
VITE_API_URL=https://deployment-and-devops-server.onrender.com/api
```

---

# ⚙️ CI/CD Pipeline — GitHub Actions

File: `.github/workflows/deploy.yml`

```yaml
name: CI/CD Pipeline

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Code
        uses: actions/checkout@v3

      - name: Setup Node
        uses: actions/setup-node@v3
        with:
          node-version: 18

      - name: Install Server Dependencies
        working-directory: server
        run: npm install

      - name: Install Client Dependencies
        working-directory: client
        run: npm install

      - name: Build Client
        working-directory: client
        run: npm run build

      - name: Run Tests (placeholder)
        run: echo "No tests yet"

      - name: Deploy Backend (Render)
        run: echo "Render auto-deploys through GitHub"

      - name: Deploy Frontend (Vercel)
        run: echo "Vercel auto-deploys through GitHub"
```

---

# 🔍 Monitoring & Maintenance

### 🩺 Health Check

Backend `/health` route returns:

```
{ "status": "OK", "timestamp": Date.now() }
```

### 📈 Tools Used:

* **Render Logs**
* **Vercel Analytics**
* **MongoDB Atlas Performance Monitor**
* **UptimeRobot (optional)**

---

# 📦 Environment Variables Template

Create a file in the root repo:

### `.env.example`

```
# Server
MONGO_URI=mongodb+srv://edgeriowilliams_db_user:Edgerio3137@mern1.sgloynp.mongodb.net/mern-blog?retryWrites=true&w=majority
JWT_SECRET=mysecretjwt
PORT=5000

# Client
VITE_API_URL=https://deployment-and-devops-server.onrender.com/api
```

---

# 🌍 Deployed URLs

| Service            URL                                                                                                            |
| --------------------- | -------------------------------------------------------------------------------------------------------------- |
| **Frontend (Vercel)** | [https://deployment-and-devops-client.vercel.app]
| **Backend (Render)**  | [https://deployment-and-devops-server.onrender.com]
| **API Base URL**      | [https://deployment-and-devops-server.onrender.com/api]


# 🔗 Resources

MongoDB

Express.js

React

Node.js

Mongoose


---

# 📸 Screenshots

(login, register, posts screenshots)

---

## Author

The-Williams(Awino Edger Williams)

# 📝 License

This project is for educational purposes as part of the **Deployment & DevOps Essentials** module.

