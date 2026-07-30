# 🤝 DevCollab Lite

A lightweight full-stack collaboration platform for development teams to manage projects and tasks with JWT-based authentication, PostgreSQL persistence, and a modern React interface.

## 🚀 Overview

DevCollab Lite solves the need for a simple project/task collaboration system where teams can:

- Create accounts and log in securely
- Create and manage projects
- Create, update, and organize tasks by status

It combines a React frontend, an Express backend API, and PostgreSQL storage, with optional Docker-based deployment and CI/CD automation.

## ✨ Features

Implemented features (based on repository code and configuration):

- User authentication with signup/login endpoints
- JWT-based protected API access
- Password hashing using bcrypt
- Project management API (`GET` / `POST`)
- Task management API (`GET` / `POST` / `PUT`)
- Task board workflow with drag-and-drop support (as documented in project notes)
- Backend health endpoints (`/` and `/api/health`)
- PostgreSQL schema bootstrap via `backend/src/db/schema.sql`
- Docker support for frontend, backend, and database using `docker-compose.yml`
- Frontend built with React and Tailwind CSS
- GitHub Actions CI/CD workflow for install, build, and Docker image build

## 🛠️ Tech Stack

### Programming Languages
- JavaScript
- SQL

### Frameworks
- React (frontend)
- Express.js (backend)
- Node.js runtime

### Libraries
- Authentication/Security: `jsonwebtoken`, `bcrypt` (as documented/used by backend design)
- Frontend ecosystem: React tooling and build chain
- Backend dependencies via `backend/package.json`
- Frontend dependencies via `frontend/package.json`

### Database
- PostgreSQL

### Tools
- Docker
- Docker Compose
- GitHub Actions
- npm
- Tailwind CSS
- PostCSS

### AI/ML Models
- Not applicable in current implementation.

## 🗂️ Project Structure

```text
devcollab-lite/
├── .github/
│   └── workflows/
│       └── ci-cd.yml
├── backend/
│   ├── src/
│   │   ├── db/
│   │   │   └── schema.sql
│   │   └── ... (API/server modules)
│   ├── .env.example
│   ├── Dockerfile
│   └── package.json
├── frontend/
│   ├── public/
│   ├── src/
│   │   └── ... (React app modules)
│   ├── .env.example
│   ├── Dockerfile
│   ├── tailwind.config.js
│   ├── postcss.config.js
│   └── package.json
├── docker-compose.yml
└── README.md
```

## ⚙️ Installation

### Prerequisites
- Node.js 18+
- PostgreSQL 14+
- npm
- (Optional) Docker + Docker Compose

### 1) Clone repository
```bash
git clone https://github.com/Eshwar1435/devcollab-lite.git
cd devcollab-lite
```

### 2) Setup environment variables

Create `backend/.env`:
```env
PORT=5000
DATABASE_URL=postgres://postgres:password@localhost:5432/devcollab_lite
JWT_SECRET=replace_with_a_long_random_secret
CLIENT_URL=http://localhost:3000
```

Create `frontend/.env`:
```env
REACT_APP_API_URL=http://localhost:5000
```

For production (e.g. backend deployed on Render), set `REACT_APP_API_URL` to the backend origin **without** a trailing `/api`:

```env
REACT_APP_API_URL=https://your-render-app.onrender.com
```

(Optional root `.env` for Docker Compose):
```env
POSTGRES_DB=devcollab_lite
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
BACKEND_PORT=5000
JWT_SECRET=replace_with_a_long_random_secret
CLIENT_URL=http://localhost:3000
REACT_APP_API_URL=http://localhost:5000
```

### 3) Install dependencies
```bash
cd backend
npm install
cd ../frontend
npm install
```

### 4) Initialize database
```bash
createdb devcollab_lite
psql "$DATABASE_URL" -f backend/src/db/schema.sql
```

## ▶️ Usage

### Run locally (without Docker)

Backend:
```bash
cd backend
npm run dev
```

Frontend (new terminal):
```bash
cd frontend
npm start
```

Default local URLs:
- Frontend: `http://localhost:3000`
- Backend: `http://localhost:5000`

### Run with Docker Compose

```bash
docker-compose up --build
```

Services:
- Frontend: `http://localhost:3000`
- Backend: `http://localhost:5000`
- PostgreSQL: `localhost:5432`

## 📸 Screenshots

> Screenshots are not included in the repository yet.

Suggested placeholders:
- `docs/screenshots/login.png` *(Work in Progress)*
- `docs/screenshots/projects-dashboard.png` *(Work in Progress)*
- `docs/screenshots/task-board.png` *(Work in Progress)*

## 🔮 Future Improvements

- Add role-based access control (admin/member scopes)
- Add project member invitations and collaboration permissions
- Add pagination/filtering/search for projects and tasks
- Add automated tests (unit + integration + e2e)
- Add API rate limiting and improved audit logging
- Add real-time updates (WebSocket/SSE)
- Improve production observability and error tracing

## 🤝 Contributing

Contributions are welcome.

1. Fork the repository
2. Create your branch:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. Commit your changes:
   ```bash
   git commit -m "feat: add meaningful update"
   ```
4. Push your branch:
   ```bash
   git push origin feature/your-feature-name
   ```
5. Open a Pull Request

Please keep PRs focused and include clear descriptions of changes.

## 📄 License

This project is licensed under the **MIT License**.

If a `LICENSE` file is not yet present, add a standard MIT License file at the repository root.

## 👨‍💻 Author

**Eshwar Nomula**
