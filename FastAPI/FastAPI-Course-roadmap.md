# خريطة كورس FastAPI الكامل (Roadmap)

## الكود
```
fastapi_course/
├── 01_basics_crud.py
├── 02_database_orm.py
├── 03_auth_jwt.py
├── 04_relationships_joins.py
└── 05_deployment_testing.md
```

## ملاحظات

### 01_basics_crud.py
- Setup (Python, VS Code, Virtual Env, pip)
- Starting FastAPI + Path Operations
- HTTP Requests (Postman)
- Schema Validation (Pydantic)
- CRUD Operations (Create, Retrieve, Update, Delete على array)
- Status Codes
- Automatic Documentation

### 02_database_orm.py
- Database Intro (Postgres, PgAdmin)
- SQL Queries (WHERE, Operators, LIKE, ORDER BY, LIMIT/OFFSET)
- Modifying Data (SQL)
- توصيل Python بقاعدة البيانات
- Database CRUD (بدون ORM)
- ORM Intro + SQLAlchemy Setup
- CRUD كامل بـ SQLAlchemy
- Pydantic vs ORM Models

### 03_auth_jwt.py
- Creating Users Table
- User Registration + Hashing Passwords
- FastAPI Routers (Prefix, Tags)
- JWT Token Basics
- Login Process + Creating Token
- OAuth2PasswordRequestForm
- Protecting Routes + Fetching Logged-in User

### 04_relationships_joins.py
- SQL Relationships + Foreign Keys (Postgres + SQLAlchemy)
- ربط الـ User بالبيانات بتاعته (Owner ID)
- Query Parameters
- Env Variables
- Votes/Likes Feature (مثال تطبيقي كامل)
- SQL Joins + Joins في SQLAlchemy
- Database Migrations (Alembic)

### 05_deployment_testing.md
- Git & GitHub
- Deploy على Heroku
- Deploy يدوي على Ubuntu VM (Nginx, SSL, Firewall)
- Docker & Docker Compose
- Testing (Pytest, Fixtures, FastAPI TestClient)
- CI/CD (GitHub Actions)

## مرتبط
- [[FastAPI-Basics-imports-setup]]
- [[SQL-Joins-inner-left-right]]
