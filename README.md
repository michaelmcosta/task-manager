# Task Manager

A simple task manager application with a Django REST API backend and a React (Vite + TypeScript) frontend.

## Project structure

- `backend/core/` – Django project (Django REST Framework, JWT auth, tasks API, SQLite)
- `frontend/` – React + TypeScript frontend (Vite)

## Prerequisites

- Python 3.12+ (recommended for Django 6)
- Node.js and npm

## Backend setup (Django)

1. Open a terminal in `backend/core`:
   ```bash
   cd backend/core
   ```

2. Create and activate a virtual environment:
   ```powershell
   # Windows (PowerShell)
   python -m venv .venv
   .venv\Scripts\Activate.ps1
   ```
   ```bash
   # macOS/Linux
   python -m venv .venv
   source .venv/bin/activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Apply database migrations:
   ```bash
   python manage.py migrate
   ```

5. (Optional) Create a user for login/admin:
   ```bash
   python manage.py createsuperuser
   ```

6. Start the backend server:
   ```bash
   python manage.py runserver
   ```

The backend runs at `http://localhost:8000`.

## Frontend setup (React + Vite)

1. Open a new terminal in `frontend`:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

The frontend runs at `http://localhost:5173` by default.

## Running the app

1. Start the backend server in `backend/core`.
2. Start the frontend dev server in `frontend`.
3. Open `http://localhost:5173` in your browser.
4. Log in with a Django user account.

## API notes

- The frontend is configured to call the API at `http://localhost:8000/api`.
- CORS allows requests from `http://localhost:5173`.
- Main endpoints:
  - `POST /api/auth/login/` – obtain JWT access/refresh tokens
  - `POST /api/auth/refresh/` – refresh access token
  - `/api/tasks/` – task CRUD (authentication required)
  - `/admin/` – Django admin
