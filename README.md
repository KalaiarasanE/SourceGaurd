# SourceGuard

**Tagline:** Verify Before You Trust

SourceGuard is a community-driven news, image, video, and source verification platform designed to combat misinformation through structured verification workflows, credibility scoring, reporting, and content moderation.

SourceGuard is structured around the requested stack:

- Frontend: React, TypeScript, Vite/TanStack
- Backend: Java Spring Boot
- Database: MySQL
- Authentication: JWT
- File storage: local uploads served from the Spring Boot API

## Project Layout

```text
src/       React frontend
backend/   Spring Boot API
```

## Frontend

```powershell
npm install
npm run dev
```

The frontend reads `VITE_API_BASE_URL`, defaulting to `http://localhost:8080`.

## Backend

Install Maven, start MySQL, then run:

```powershell
cd backend
$env:MYSQL_URL="jdbc:mysql://localhost:3306/sourceguard?createDatabaseIfNotExist=true&useSSL=false&allowPublicKeyRetrieval=true&serverTimezone=UTC"
$env:MYSQL_USER="root"
$env:MYSQL_PASSWORD="password"
$env:JWT_SECRET="replace-with-a-long-random-secret-of-at-least-32-characters"
mvn spring-boot:run
```

The backend seeds default categories and trusted sources on startup. Uploaded submission files are stored under `backend/uploads/` unless `UPLOAD_DIR` is set.
