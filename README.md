# Resume Website (FastAPI)

Features:
- Resume page (index) with email and short skills blurb (Kotlin programmer).
- Project request form page that stores requests in SQLite.
- Admin login (JWT-based) and admin requests page to view stored requests.
- WebSocket endpoint broadcasting number of online visitors in real time.

Requirements:
- Python 3.10+
- Install dependencies:
  pip install -r requirements.txt

Run:
- export (or set) environment variables to secure the admin credentials and secret key:
  - SECRET_KEY (recommended)
  - ADMIN_USERNAME (default: "admin")
  - ADMIN_PASSWORD (default: "adminpass")
- Start server:
  uvicorn app.main:app --reload

Pages:
- http://localhost:8000/          -> Resume
- http://localhost:8000/request   -> Project request form
- http://localhost:8000/admin/login -> Admin login
- http://localhost:8000/admin/requests -> Admin requests (requires login)

Notes:
- For production, change SECRET_KEY and ADMIN_* variables. Consider using hashed passwords and a proper user store.
- This scaffold uses simple server-side JWT and an in-memory WebSocket connection manager. For horizontal scaling use a Redis-based pub/sub or a central WebSocket manager.

End of files.
