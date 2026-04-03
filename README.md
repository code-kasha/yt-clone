# 📺 YouTube Clone — Full Stack MERN Project

> MongoDB · Express · React · Node.js · Tailwind CSS · JWT

A full-stack YouTube-inspired video platform where users can browse videos, authenticate, manage channels, play videos, and interact through comments and likes.

---

## Project Structure

```
youtube-clone/
├── backend/          # Node.js + Express + MongoDB API
│   ├── src/
│   ├── .env.example
│   ├── package.json
│   └── README.md
├── frontend/         # React + Vite + Tailwind CSS
│   ├── src/
│   ├── .env.example
│   ├── package.json
│   └── README.md
└── README.md         # ← You are here
```

---

## Tech Stack

| Part            | Technologies                                         |
| --------------- | ---------------------------------------------------- |
| Frontend        | React 18, Vite, Tailwind CSS, React Router v6, Axios |
| Backend         | Node.js, Express.js                                  |
| Database        | MongoDB (Atlas or local)                             |
| Auth            | JWT (JSON Web Tokens) + bcryptjs                     |
| Version Control | Git                                                  |

---

## Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/youtube-clone.git
cd youtube-clone
```

### 2. Start the Backend

```bash
cd backend
npm install
cp .env.example .env       # Fill in MONGO_URI and JWT_SECRET
npm run dev                # Runs on http://localhost:5000
```

### 3. Start the Frontend

```bash
cd ../frontend
npm install
cp .env.example .env       # Set VITE_API_URL=http://localhost:5000/api
npm run dev                # Runs on http://localhost:5173
```

Open `http://localhost:5173` in your browser.

---

## Environment Variables

### Backend — `backend/.env`

```env
PORT=5000
MONGO_URI=mongodb+srv://<username>:<password>@cluster.mongodb.net/youtube-clone
JWT_SECRET=your_super_secret_key
JWT_EXPIRES_IN=7d
```

### Frontend — `frontend/.env`

```env
VITE_API_URL=http://localhost:5000/api
```

---

## Features

### 🏠 Home Page

- YouTube-style header with logo, search bar, and auth controls
- Toggleable sidebar with navigation
- Category filter bar (6+ categories)
- Responsive video grid with thumbnails, titles, channels, and view counts

### 🔐 User Authentication

- Register with username, email, and password
- Login with JWT — token persisted in `localStorage`
- Protected routes and actions require authentication
- User's name displayed in header after login

### 🔍 Search & Filter

- Real-time search by video title via the header search bar
- Category-based filtering — at least 6 filter buttons

### 🎬 Video Player

- HTML5 video player
- Title, description, channel name
- Like / Dislike buttons with live counts and toggle behaviour
- Full CRUD comment section (add, edit, delete) for authenticated users

### 📺 Channel Page

- Channel info: banner, name, description, subscriber count
- Grid of channel videos
- Authenticated channel owners can: create, edit, and delete videos
- "Create Channel" option for signed-in users without a channel

### 📱 Responsive Design

- Fully responsive across mobile, tablet, and desktop

---

## API Overview

| Resource | Base Route      |
| -------- | --------------- |
| Auth     | `/api/auth`     |
| Videos   | `/api/videos`   |
| Channels | `/api/channels` |
| Comments | `/api/comments` |

Full API documentation is in [`backend/README.md`](./backend/README.md).

---

## Database

MongoDB collections:

- `users` — account info, hashed passwords, linked channels
- `videos` — metadata, URLs, likes/dislikes, category
- `channels` — owner, banner, subscribers, video list
- `comments` — text, author, video reference, timestamp

### Seeding Sample Data

```bash
cd backend
npm run seed
```

If using MongoDB Compass locally, import the export files from `backend/seed/`.

---

## Folder Responsibilities

### Backend is responsible for:

- All database models and schema definitions
- REST API endpoints (auth, videos, channels, comments)
- JWT issuance, verification, and protected route middleware
- Password hashing and validation
- Business logic (ownership checks, like/dislike toggling)
- Serving the API at port 5000

### Frontend is responsible for:

- All UI components and pages
- Routing with React Router
- Consuming the backend API via Axios
- Global auth state via React Context
- Form validation and user feedback
- Responsive layout with Tailwind CSS

---

## Commit Guidelines

Commits are split by area for clarity. Aim for at least **30 total commits**, roughly:

- 15 backend commits
- 15 frontend commits

Example commit messages:

```
feat(backend): add JWT auth middleware
feat(backend): create video CRUD endpoints
fix(backend): fix ownership check on comment delete
feat(frontend): build Home page layout with sidebar
feat(frontend): add VideoCard component
feat(frontend): implement comment CRUD on video player page
```

---

## Submission Checklist Summary

- [ ] Backend and Frontend both fully functional
- [ ] At least 30 commits across the repository
- [ ] `node_modules/` not committed
- [ ] `.env` files not committed
- [ ] MongoDB seed files or export provided
- [ ] Both READMEs complete
- [ ] Video demo recorded and linked below

---

## Video Demo

> 🎥 Link to demo video: _[add link here]_

---

## Author

| Name          | Role                 |
| ------------- | -------------------- |
| _[Your Name]_ | Full Stack Developer |

---

## License

This project is submitted as a capstone assignment. All code is original work by the author.
