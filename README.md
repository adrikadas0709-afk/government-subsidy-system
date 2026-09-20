# Government Subsidy & Grant Disbursement Tracking System

A full-stack application for managing government subsidy and grant applications, verification workflows, staged disbursements, fund utilization, and reporting.

## Features

- Beneficiary registration and profile management
- Government scheme and eligibility-criteria management
- Multi-stage application verification
- Role-based access control with JWT authentication
- Staged subsidy disbursement and compliance milestones
- Fund-utilization tracking
- Dashboard analytics, audit logs, and CSV reports
- MySQL database integration

## Technology Stack

| Layer | Technologies |
|---|---|
| Frontend | React, Vite, React Router, Axios, Lucide React |
| Backend | Java 21, Spring Boot 3, Spring Security, Spring Data JPA |
| Database | MySQL 8 |
| Authentication | JWT |

## Project Structure

```text
government-subsidy-system/
├── frontend/                 # React + Vite application
├── backend/                  # Spring Boot API
│   └── src/main/resources/
│       ├── schema-mysql.sql
│       └── application.properties.example
├── .gitignore
└── README.md
```

## Prerequisites

Install the following before running the project:

- Java 21
- Maven 3.9 or later
- Node.js 18 or later
- MySQL 8

## Database Setup

1. Start MySQL.
2. Create the database:

```sql
CREATE DATABASE subsidy_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

3. Go to the backend resources folder:

```powershell
cd backend/src/main/resources
```

4. Copy the example configuration file:

```powershell
Copy-Item application.properties.example application.properties
```

5. Open `application.properties` and set your MySQL username, password, and a secure JWT secret.

> Do not commit `application.properties`. It is excluded through `.gitignore`.

## Backend Setup

From the project root:

```powershell
cd backend
mvn clean install
mvn spring-boot:run
```

The backend starts at:

```text
http://localhost:8084
```

## Frontend Setup

Open a new terminal from the project root:

```powershell
cd frontend
Copy-Item .env.example .env
npm install
npm run dev
```

The frontend starts at:

```text
http://localhost:3004
```

Open this URL in your browser:

```text
http://localhost:3004
```

## Frontend Environment Configuration

In `frontend/.env`, use:

```env
VITE_API_BASE_URL=http://localhost:8084
```

> Do not commit `.env`. It is excluded through `.gitignore`.

## User Roles

The application supports these roles:

- Admin
- Beneficiary
- Field Officer
- District Officer
- Finance Officer

## Application Workflow

```text
Draft
  → Submitted
  → Eligibility Evaluated
  → Field Verification
  → District Review
  → Finance Approval
  → Disbursement Planned
  → Milestone Pending
  → Disbursement In Progress
  → Fully Disbursed
  → Utilization Pending
  → Completed
```

## Build for Production

Build the frontend:

```powershell
cd frontend
npm run build
```

Build the backend:

```powershell
cd backend
mvn clean package
```

## Security Notes

The following files must never be committed because they may contain credentials or secrets:

```text
frontend/.env
backend/src/main/resources/application.properties
```

Safe template files are included instead:

```text
frontend/.env.example
backend/src/main/resources/application.properties.example
```

## License

This project is created for educational and academic purposes.