# ✅ Full Project Checklist — YouTube Clone (MERN)

Use this as your **master submission checklist**. Each item maps to marks in the rubric.
Detailed per-area checklists are in `backend/CHECKLIST.md` and `frontend/CHECKLIST.md`.

---

## 📦 Repository & Setup (Pre-Requisite)

- [ ] Single GitHub repository with both `backend/` and `frontend/` folders
- [ ] At least **30 commits** total across the project
- [ ] At least **15 commits** in backend section
- [ ] At least **15 commits** in frontend section
- [ ] Commits are descriptive and atomic
- [ ] `node_modules/` not committed (confirmed by `.gitignore`)
- [ ] `.env` files not committed (confirmed by `.gitignore`)
- [ ] `.env.example` files committed for both backend and frontend
- [ ] MongoDB seed script or Compass export files provided
- [ ] Root `README.md` complete
- [ ] Backend `README.md` complete
- [ ] Frontend `README.md` complete
- [ ] Video demo recorded

---

## 🔐 User Authentication — 40 marks (Frontend + Backend)

- [ ] **Backend:** `POST /api/auth/register` — creates user with hashed password
- [ ] **Backend:** `POST /api/auth/login` — returns JWT on valid credentials
- [ ] **Backend:** JWT signed with secret key, includes `userId` payload
- [ ] **Backend:** Auth middleware protects all write/update/delete routes
- [ ] **Backend:** Invalid token returns `401 Unauthorized`
- [ ] **Frontend:** Register form — username, email, password fields
- [ ] **Frontend:** Register form — inline validation errors (empty, format, length)
- [ ] **Frontend:** Successful registration redirects to Login page
- [ ] **Frontend:** Login form — email and password
- [ ] **Frontend:** JWT stored in `localStorage` after login
- [ ] **Frontend:** Header shows "Sign In" button when logged out
- [ ] **Frontend:** Header shows username/avatar when logged in
- [ ] **Frontend:** Logout clears token and resets state

---

## 🏠 Home Page UI/UX — 40 marks (Frontend)

- [ ] YouTube-style Header with logo
- [ ] Hamburger icon in Header toggles Sidebar
- [ ] Sidebar renders navigation links
- [ ] Sidebar shows/hides correctly on toggle
- [ ] Filter bar with at least **6 category buttons**
- [ ] Default "All" filter shows all videos
- [ ] Category buttons filter displayed videos correctly
- [ ] Video grid is displayed in a card layout
- [ ] Each video card shows: Thumbnail, Title, Channel Name, View Count
- [ ] Clicking a video card navigates to the video player page
- [ ] Layout is clean and resembles YouTube structure

---

## 🎬 Video Player Page — 50 marks (Frontend + Backend)

- [ ] **Backend:** `GET /api/videos/:id` returns video data and increments views
- [ ] **Backend:** `PUT /api/videos/:id/like` toggles like (protected)
- [ ] **Backend:** `PUT /api/videos/:id/dislike` toggles dislike (protected)
- [ ] **Backend:** `GET /api/comments/:videoId` returns all comments
- [ ] **Backend:** `POST /api/comments/:videoId` adds a comment (protected)
- [ ] **Backend:** `PUT /api/comments/:commentId` edits a comment (author only)
- [ ] **Backend:** `DELETE /api/comments/:commentId` deletes a comment (author only)
- [ ] **Frontend:** Video player renders and plays video
- [ ] **Frontend:** Title and description displayed
- [ ] **Frontend:** Channel name displayed (linked to channel page)
- [ ] **Frontend:** Like button shows count, toggles state
- [ ] **Frontend:** Dislike button shows count, toggles state
- [ ] **Frontend:** Like and Dislike are mutually exclusive
- [ ] **Frontend:** Comments section displays all comments
- [ ] **Frontend:** Authenticated user can add a comment
- [ ] **Frontend:** User can edit their own comment
- [ ] **Frontend:** User can delete their own comment
- [ ] **Frontend:** Edit/Delete buttons only visible on own comments

---

## 📺 Channel Page — 40 marks (Frontend + Backend)

- [ ] **Backend:** `GET /api/channels/:id` returns channel info + videos
- [ ] **Backend:** `POST /api/channels` creates a channel (protected)
- [ ] **Backend:** `POST /api/videos` creates a video in a channel (protected)
- [ ] **Backend:** `PUT /api/videos/:id` updates a video (owner only)
- [ ] **Backend:** `DELETE /api/videos/:id` deletes a video (owner only)
- [ ] **Frontend:** Channel banner, name, description, subscriber count displayed
- [ ] **Frontend:** Grid of channel's videos displayed
- [ ] **Frontend:** Owner sees "Upload Video" button
- [ ] **Frontend:** Owner can fill form and create a new video
- [ ] **Frontend:** New video appears in channel grid after creation
- [ ] **Frontend:** Owner sees Edit button on each video
- [ ] **Frontend:** Edit form pre-filled with video data, saves changes
- [ ] **Frontend:** Owner sees Delete button on each video
- [ ] **Frontend:** Delete removes video with confirmation
- [ ] **Frontend:** "Create Channel" option visible only to signed-in users
- [ ] **Frontend:** Non-owner sees read-only channel view

---

## 🔍 Search & Filter Functionality — 40 marks (Frontend + Backend)

- [ ] **Backend:** `GET /api/videos?search=<query>` filters by title (case-insensitive)
- [ ] **Backend:** `GET /api/videos?category=<cat>` filters by category
- [ ] **Frontend:** Search bar in Header is visible and functional
- [ ] **Frontend:** Typing in search bar filters video grid by title
- [ ] **Frontend:** Clearing search restores full video list
- [ ] **Frontend:** At least 6 category filter buttons present
- [ ] **Frontend:** Clicking a category correctly filters the video grid
- [ ] **Frontend:** "All" button resets category filter

---

## 📡 Back-End API Design — 40 marks (Backend)

- [ ] Auth routes: `/api/auth/register`, `/api/auth/login`, `/api/auth/me`
- [ ] Video routes: GET all, GET one, POST, PUT, DELETE, like, dislike
- [ ] Channel routes: GET one, POST, PUT, DELETE
- [ ] Comment routes: GET by video, POST, PUT, DELETE
- [ ] All routes follow REST conventions (correct HTTP methods and status codes)
- [ ] Controllers are separated from route definitions
- [ ] ES Module syntax (`import`/`export`) used throughout
- [ ] CORS configured to accept requests from the frontend origin

---

## 🗄️ Data Handling (MongoDB) — 40 marks (Backend)

- [ ] User model correctly defined and stored
- [ ] Video model correctly defined with all required fields
- [ ] Channel model correctly defined and linked to owner
- [ ] Comment model correctly defined and linked to video
- [ ] Data is correctly stored on creation
- [ ] Data is correctly fetched and returned in responses
- [ ] Passwords are hashed — never stored as plain text
- [ ] Passwords never returned in API responses
- [ ] Relationships maintained (video removed from channel on delete, etc.)
- [ ] Seed data provided for evaluators

---

## 🔒 JWT Integration — 40 marks (Backend)

- [ ] JWT issued on login with `userId` payload
- [ ] JWT signed with `JWT_SECRET` environment variable
- [ ] Token expiry set (`JWT_EXPIRES_IN`)
- [ ] Auth middleware verifies token on protected routes
- [ ] `req.user` populated from token payload
- [ ] Missing or invalid token returns `401`
- [ ] Ownership verified before update/delete actions (returns `403` if not owner)
- [ ] Frontend attaches token via Axios interceptor on all requests

---

## 📱 Responsive Design — 30 marks (Frontend)

- [ ] Mobile layout (< 640px): 1-column grid, sidebar hidden
- [ ] Tablet layout (640–1024px): 2-column grid, sidebar collapsible
- [ ] Desktop layout (> 1024px): 4-column grid, sidebar visible
- [ ] Header is responsive
- [ ] Video Player page is usable on mobile
- [ ] Channel page is usable on mobile
- [ ] Comment section is usable on mobile
- [ ] No horizontal scrollbar on any page/device

---

## 🧹 Code Quality & Documentation — 40 marks (Both)

- [ ] Clean folder structure in both backend and frontend
- [ ] ES Modules used throughout (no `require()`)
- [ ] Vite used (no CRA)
- [ ] No commented-out dead code left in submission
- [ ] Consistent naming conventions
- [ ] Complex logic has inline comments
- [ ] `README.md` — root (full project setup and overview)
- [ ] `README.md` — backend (API reference, models, setup)
- [ ] `README.md` — frontend (pages, components, setup)
- [ ] Video demo recorded and link added to root README

---

## 🏁 Final Submission Checks

- [ ] Both backend and frontend run without errors from a fresh `npm install`
- [ ] Registration and login work correctly end-to-end
- [ ] Videos load on the Home page
- [ ] Search and filters work
- [ ] Video player loads and plays a video
- [ ] Comments can be added, edited, and deleted
- [ ] Like / Dislike buttons work
- [ ] Channel page loads with videos
- [ ] Channel owner can create, edit, and delete videos
- [ ] App is responsive on at least two screen sizes
- [ ] GitHub repository link ready for submission
- [ ] Demo video link ready for submission
