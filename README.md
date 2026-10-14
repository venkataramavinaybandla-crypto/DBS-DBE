# DBS-DBE — Database Systems & Database Engineering

<p align="center">
  <strong>A hands-on collection of database practicals, backend APIs, and full-stack projects.</strong>
  <br />
  Exploring relational databases, NoSQL data modelling, REST APIs, persistence layers, and secure application design.
</p>

<p align="center">
  <a href="https://github.com/venkataramavinaybandla-crypto/DBS-DBE">
    <img src="https://img.shields.io/badge/Repository-DBS--DBE-14395C?style=for-the-badge&logo=github&logoColor=white" alt="DBS-DBE Repository" />
  </a>
  <img src="https://img.shields.io/badge/Domain-Database%20Engineering-00758F?style=for-the-badge" alt="Database Engineering" />
  <img src="https://img.shields.io/badge/Focus-Practical%20Implementations-2E7D32?style=for-the-badge" alt="Practical Implementations" />
</p>

---

## Overview

**DBS-DBE** is a practical repository documenting database concepts and their application in software systems. It brings together coursework, implementation files, project documentation, and supporting learning resources in one place.

The repository covers multiple approaches to data management — from structured relational tables and document-oriented databases to database-backed REST services and application-level search.

Rather than treating database concepts as isolated theory, these practicals connect them to working application patterns:

- Designing and querying structured and semi-structured data.
- Modelling application entities and relationships.
- Building CRUD operations through REST APIs.
- Connecting Java and JavaScript applications to databases.
- Applying authentication, request validation, and error handling.
- Exploring text embeddings and similarity-based book search.
- Documenting implementation details, setup procedures, and limitations.

> **Repository principle:** Understand the data model, build the interface to the data, and document what the implementation actually does.

## Table of Contents

- [Repository at a Glance](#repository-at-a-glance)
- [Technology Stack](#technology-stack)
- [Projects and Practicals](#projects-and-practicals)
  - [Week 1 Practicals](#week-1-practicals)
  - [Week 2 Practical](#week-2-practical)
  - [Week 3 — MongoDB](#week-3--mongodb)
  - [CO-3 — Student Records API](#co-3--student-records-api)
  - [CO-4-1 — Student Management System](#co-4-1--student-management-system)
  - [CO-5 — Library Management System](#co-5--library-management-system)
- [Architecture Patterns](#architecture-patterns)
- [Repository Structure](#repository-structure)
- [Getting Started](#getting-started)
- [API Reference](#api-reference)
- [Database Concepts Demonstrated](#database-concepts-demonstrated)
- [Security and Configuration](#security-and-configuration)
- [Documentation and Certificates](#documentation-and-certificates)
- [Testing and Verification](#testing-and-verification)
- [Current Scope and Limitations](#current-scope-and-limitations)
- [Future Improvements](#future-improvements)
- [Author](#author)

---

## Repository at a Glance

| Area | Technologies | Focus |
|---|---|---|
| Relational databases | MySQL, SQL | Schema design, structured storage, queries |
| Document databases | MongoDB, Mongoose | Flexible schemas, filtering, aggregation |
| Java backend | Java, Spring Boot, Spring Data JPA | Database-backed REST services |
| JavaScript backend | Node.js, Express.js | HTTP endpoints and request handling |
| Full-stack development | React, Vite, Spring Boot | Frontend-to-backend integration |
| Authentication | Spring Security, JWT, BCrypt | Authenticated application access |
| API development | REST, JSON, Postman workflow | CRUD operations and request testing |
| Search | Text embeddings, cosine similarity | Application-level semantic search |
| Documentation | DOCX, PDF, Markdown | Practical reports and supporting resources |

*The technology list describes the repository's documented projects collectively; individual practicals use different subsets of the stack.*

---

## Projects and Practicals

### Week 1 Practicals

**Documentation:** `Bandla_Vinay_2520030437_Week-1.1.docx`, `Bandla_Vinay_2520030437_Week-1.2.docx`, and `Bandla_Vinay_2520030437_Week-1.3.docx`

These files preserve the Week 1 practical submissions and their associated documentation.

Refer to the individual reports for the exact objectives, procedures, implementation details, and outputs of each practical.

### Week 2 Practical

**Documentation:** `Bandla_Vinay_2520030437_Week2.docx`

The Week 2 submission is maintained as a separate practical report. Its specific implementation should be read from the report rather than inferred from the repository's other projects.

### Week 3 — MongoDB

**Documentation:** `Bandla_Vinay_25200030437_Week-3.docx`

This practical explores document-oriented data management through a book-oriented dataset.

Key topics documented for this work include:

- Creating and querying a MongoDB database and collection.
- Storing flexible book metadata and related information.
- Filtering records using comparison and membership operators.
- Performing regular-expression queries.
- Building aggregation pipelines.
- Creating text indexes and performing text search.
- Examining query execution with `explain("executionStats")`.

The associated practical explores a `bookflow` database and a `book_metadata` collection.

These exercises demonstrate how document databases support flexible data structures and query patterns that differ from traditional relational tables.

### CO-3 — Student Records API

**Project directory:** [`Bandla_Vinay_2520030437_Co-3`](Bandla_Vinay_2520030437_Co-3/)

**Report:** [`Bandla_Vinay_2520030437_Co-3.docx`](Bandla_Vinay_2520030437_Co-3.docx)

This practical contains a student-record data model and controller operations implemented with JavaScript, Express-style controller patterns, and Mongoose.

#### Data model

The `Student` schema defines:

- `name` — required string, trimmed.
- `age` — required number between 16 and 100.
- `course` — required string, trimmed.
- `email` — required, unique, trimmed, and converted to lowercase.
- `timestamps` — automatically managed creation and update timestamps.

#### Implemented controller operations

| Operation | Purpose |
|---|---|
| Create student | Stores a new student record |
| Get all students | Retrieves student records |
| Get student by ID | Finds a student by MongoDB document ID |
| Update student | Modifies an existing student record |
| Delete student | Removes a student record |

#### Core source files

```text
Bandla_Vinay_2520030437_Co-3/
├── controllers/
│   └── studentController.js
└── models/
    └── Student.js
```

**Implementation note:** The tracked project currently contains the model and controller files, but does not include a complete application entry point, route registration, or `package.json`. A full standalone setup therefore requires those missing project components.

### CO-4-1 — Student Management System

**Project directory:** [`Bandla_Vinay_2520030437_Co-4-1`](Bandla_Vinay_2520030437_Co-4-1/)

**Report:** [`Bandla_Vinay_2520030437_Co-4-1.docx`](Bandla_Vinay_2520030437_Co-4-1.docx)

A Java-based REST API that demonstrates layered application design and relational persistence using Spring Boot, Spring Data JPA, and MySQL.

#### Core capabilities

- Create student records.
- Retrieve all student records.
- Retrieve an individual student by ID.
- Update student details.
- Delete student records.

#### Student entity

| Field | Type | Purpose |
|---|---|---|
| `id` | `Long` | Auto-generated primary key |
| `name` | `String` | Student name |
| `department` | `String` | Department or programme |
| `email` | `String` | Student email address |

#### Architecture

```text
HTTP Client
    |
    v
StudentController
    |
    v
StudentService
    |
    v
StudentRepository
    |
    v
MySQL Database
```

#### Core source structure

```text
Bandla_Vinay_2520030437_Co-4-1/
├── pom.xml
├── mvnw
├── mvnw.cmd
└── src/
    ├── main/
    │   ├── java/com/example/studentmanagement/
    │   │   ├── StudentManagementApplication.java
    │   │   ├── controller/
    │   │   │   └── StudentController.java
    │   │   ├── entity/
    │   │   │   └── Student.java
    │   │   ├── repository/
    │   │   │   └── StudentRepository.java
    │   │   └── service/
    │   │       └── StudentService.java
    │   └── resources/
    │       └── application.properties
    └── test/
        └── java/com/example/studentmanagement/
            └── StudentManagementApplicationTests.java
```

The repository uses the conventional controller-service-repository structure, keeping HTTP request handling, application operations, and persistence access in separate layers.

### CO-5 — Library Management System

**Project directory:** [`Bandla_Vinay_CO-5`](Bandla_Vinay_CO-5/)

**Report:** [`Bandla_Vinay_2520030437_CO-5.docx`](Bandla_Vinay_2520030437_CO-5.docx)

This project brings together a library-oriented domain model, a Spring Boot backend, a MySQL database, and a documented React/Vite frontend workflow.

#### Technology stack

- **Frontend:** React, Vite, JavaScript.
- **Backend:** Spring Boot, Spring Security, Spring Data JPA.
- **Database:** MySQL 8.
- **Authentication:** JWT and BCrypt password hashing.
- **Validation:** Bean Validation.
- **Background processing:** Asynchronous audit logging.
- **Search:** Application-level semantic similarity using embeddings.
- **API workflow:** HTTP/JSON requests, with Postman described in the project documentation.

#### Documented features

- Member registration and login.
- Token-based authentication.
- Book creation and retrieval.
- Input validation and centralized exception handling.
- Member-protected book operations.
- Book-text embeddings stored as JSON data in MySQL.
- Similarity-based search using cosine similarity.
- Asynchronous logging of book creation events.

#### Architecture

```text
React / API Client
        |
        | HTTP + JSON
        | JWT for protected requests
        v
Spring Boot REST API
        |
        +-- Authentication and Security
        +-- Request Validation
        +-- Book and Member Services
        +-- Semantic Search
        +-- Asynchronous Audit Logging
        |
        v
Spring Data JPA / Hibernate
        |
        v
      MySQL 8
```

#### Relevant project files

```text
Bandla_Vinay_CO-5/
├── README.md
├── backend/
│   ├── pom.xml
│   ├── docker-compose.yml
│   ├── logs/
│   │   └── book_events.txt
│   └── src/main/
│       ├── java/com/library/api/
│       │   ├── controller/
│       │   ├── dto/
│       │   ├── model/
│       │   ├── repository/
│       │   ├── security/
│       │   └── service/
│       └── resources/
│           └── application.properties
├── database/
│   └── library_database.sql
└── frontend/
    └── index.html
```

The backend source separates controllers, data-transfer objects, entities, repositories, security components, and services.

**Repository note:** The checked-in frontend currently lacks the normal Vite application files such as `package.json` and application source modules. The project README describes the intended React workflow, but a complete frontend installation cannot be reproduced from the currently tracked frontend files alone. A Postman collection is also referenced in the project documentation but is not present in the inspected repository tree.

---

## Architecture Patterns

Across the repository, the projects illustrate several common database engineering patterns.

### 1. Relational persistence

The Spring Boot projects use entity models and repository abstractions to map application objects to relational database records.

### 2. Document-oriented persistence

The MongoDB practical demonstrates flexible documents, query operators, indexes, and aggregation pipelines.

### 3. Layered backend architecture

The CO-4-1 and CO-5 projects separate request handling from service logic and database access.

### 4. API-driven communication

REST endpoints exchange JSON data between clients and backend services.

### 5. Authentication and access control

The library project documents JWT-based authentication, password hashing with BCrypt, and protected API operations.

### 6. Application-level semantic search

The library project describes generating text embeddings, storing them in MySQL, and ranking search results by cosine similarity rather than relying on a database-native vector operator.

---

## Repository Structure

The following is a simplified view of the top-level repository:

```text
DBS-DBE/
│
├── README.md
│
├── Bandla_Vinay_2520030437_Week-1.1.docx
├── Bandla_Vinay_2520030437_Week-1.2.docx
├── Bandla_Vinay_2520030437_Week-1.3.docx
├── Bandla_Vinay_2520030437_Week2.docx
├── Bandla_Vinay_25200030437_Week-3.docx
│
├── Bandla_Vinay_2520030437_Co-3.docx
├── Bandla_Vinay_2520030437_Co-3/
│
├── Bandla_Vinay_2520030437_Co-4-1.docx
├── Bandla_Vinay_2520030437_Co-4-1/
│
├── Bandla_Vinay_2520030437_CO-5.docx
├── Bandla_Vinay_CO-5/
│
├── Co-4-Project-2.docx
├── MongoDB_Certificate.pdf
└── SQL_Certificate.pdf
```

The project directories contain implementation files, while the root-level DOCX and PDF files preserve reports, practical submissions, and supporting credentials.

Some directories also contain generated build output or installed dependencies. Those files are not required to understand the main source architecture.

---

## Getting Started

Each project has its own dependencies and configuration. There is no single root-level command that starts every practical.

### Prerequisites

Install the tools needed for the particular project you intend to run:

| Tool | Used for |
|---|---|
| Git | Cloning and version control |
| Java JDK | Spring Boot projects |
| Maven or Maven Wrapper | Java dependency management and execution |
| MySQL Server | Relational database projects |
| MySQL Workbench | Optional visual database management |
| Node.js and npm | JavaScript projects |
| MongoDB Server | MongoDB practicals |
| MongoDB Shell or Compass | Optional database interaction and inspection |
| Postman or another HTTP client | REST API testing |

### Clone the repository

```bash
git clone https://github.com/venkataramavinaybandla-crypto/DBS-DBE.git
cd DBS-DBE
```

### Run CO-4-1 — Student Management System

First, ensure a local MySQL server is running and create the database:

```sql
CREATE DATABASE studentdb;
```

Configure the database connection privately before launching the application.

On Windows:

```powershell
cd Bandla_Vinay_2520030437_Co-4-1
.\mvnw.cmd spring-boot:run
```

On macOS/Linux:

```bash
cd Bandla_Vinay_2520030437_Co-4-1
chmod +x mvnw
./mvnw spring-boot:run
```

The application is configured to use port `8080`.

Base API URL:

```text
http://localhost:8080/api/students
```

The project currently targets Java 25 in its Maven configuration. Install a compatible JDK before running it.

### Run CO-5 — Library Management System

Create the library database using the SQL script:

```text
Bandla_Vinay_CO-5/database/library_database.sql
```

Then, after verifying the local database configuration, start the backend:

```bash
cd Bandla_Vinay_CO-5/backend
mvn spring-boot:run
```

The backend README documents the API at:

```text
http://localhost:8080
```

The documented frontend workflow is:

```bash
cd Bandla_Vinay_CO-5/frontend
npm install
npm run dev
```

However, the currently tracked frontend directory is incomplete and does not contain `package.json`; restore or add the missing Vite project files before using those commands.

### Run CO-3 — Student Records API

The currently tracked CO-3 folder contains the Mongoose model and student controller, rather than a complete runnable Node.js application.

To make it independently executable, the project needs a `package.json`, application entry point, Express app configuration, route registration, and MongoDB connection configuration. Those missing files must be supplied before a reliable startup command can be documented.

### Run the MongoDB practical

Open the Week 3 report and follow its database setup and query instructions. The practical documents the `bookflow` database, `book_metadata` collection, filtering, aggregation, text search, and query execution analysis.

---

## API Reference

This section summarizes the endpoints implemented or documented by the project source.

### CO-3 — Student Records API

The controller defines the following operations:

| Method | Route pattern | Purpose |
|---|---|---|
| `POST` | Route not included in the tracked files | Create a student |
| `GET` | Route not included in the tracked files | Retrieve all students |
| `GET` | Route not included in the tracked files | Retrieve a student by ID |
| `PUT` | Route not included in the tracked files | Update a student |
| `DELETE` | Route not included in the tracked files | Delete a student |

The controller logic is present, but the route-registration code is not included in the tracked CO-3 folder. Exact request URLs cannot therefore be confirmed from the current source.

### CO-4-1 — Student Management System

Base path:

```text
/api/students
```

| Method | Endpoint | Purpose |
|---|---|---|
| `POST` | `/api/students` | Create a student |
| `GET` | `/api/students` | Retrieve all students |
| `GET` | `/api/students/{id}` | Retrieve a student by ID |
| `PUT` | `/api/students/{id}` | Update a student |
| `DELETE` | `/api/students/{id}` | Delete a student |

Example request body:

```json
{
  "name": "Vinay",
  "department": "Computer Science",
  "email": "vinay@example.com"
}
```

Example request:

```bash
curl -X GET http://localhost:8080/api/students
```

These examples describe the expected request format. They do not imply that the application has been started or that the requests have been executed in this environment.

### CO-5 — Library Management System

The project documentation describes the following API routes:

| Method | Endpoint | Purpose |
|---|---|---|
| `GET` | `/api/health` | Check service health |
| `POST` | `/api/auth/register` | Register a member |
| `POST` | `/api/auth/login` | Authenticate a member |
| `POST` | `/api/books` | Create a book |
| `GET` | `/api/books/search` | Search books by query text |

Protected endpoints use bearer-token authentication as documented by the project.

Example search request:

```bash
curl "http://localhost:8080/api/books/search?q=secure%20web%20development&limit=10" \
  -H "Authorization: Bearer YOUR_ACCESS_TOKEN"
```

Replace the placeholder with a valid token from the login endpoint. Confirm the running backend's route configuration before relying on any example.

---

## Database Concepts Demonstrated

### SQL and relational modelling

- Database and table creation.
- Entity-to-table mapping.
- Primary keys and generated identifiers.
- Structured record persistence.
- Repository-based data access.

### MongoDB and document queries

- Collections and flexible document structures.
- Field-based filtering.
- Comparison and membership operators.
- Regular-expression matching.
- Aggregation pipelines.
- Text indexes and query execution analysis.

### API and persistence integration

- Mapping JSON requests to application models.
- Creating, retrieving, updating, and deleting records.
- Separating HTTP logic from persistence logic.
- Connecting backend services to relational and document databases.

### Search and retrieval

- Representing text as numerical embeddings.
- Persisting embedding data.
- Calculating cosine similarity in application code.
- Ranking records by semantic relevance.

---

## Security and Configuration

Database applications should never depend on publicly committed credentials.

Before running any project:

1. Inspect its database configuration.
2. Replace example credentials with local configuration.
3. Use environment variables or an appropriate secret-management mechanism.
4. Avoid committing passwords, access tokens, or private connection strings.
5. Rotate any real credential that has already been exposed in a public repository.
6. Use authentication and authorization where an API exposes protected data.
7. Keep production deployments behind appropriate network and transport security controls.

For local development, use environment-specific configuration rather than storing sensitive values directly in tracked source files.

---

## Documentation and Certificates

The repository also preserves practical reports and supporting resources.

| File | Description |
|---|---|
| `Bandla_Vinay_2520030437_Week-1.1.docx` | Week 1 practical report |
| `Bandla_Vinay_2520030437_Week-1.2.docx` | Week 1 practical report |
| `Bandla_Vinay_2520030437_Week-1.3.docx` | Week 1 practical report |
| `Bandla_Vinay_2520030437_Week2.docx` | Week 2 practical report |
| `Bandla_Vinay_25200030437_Week-3.docx` | Week 3 practical report |
| `Bandla_Vinay_2520030437_Co-3.docx` | CO-3 student records project report |
| `Bandla_Vinay_2520030437_Co-4-1.docx` | CO-4-1 student management report |
| `Bandla_Vinay_2520030437_CO-5.docx` | CO-5 library management report |
| `Co-4-Project-2.docx` | Additional CO-4 project documentation |
| `MongoDB_Certificate.pdf` | MongoDB-related certificate |
| `SQL_Certificate.pdf` | SQL-related certificate |

Use the individual reports for practical-specific objectives, implementation details, screenshots where available, and observations.

---

## Testing and Verification

Testing should be performed against each project independently.

Recommended verification steps include:

- Confirming the required database server is running.
- Checking that the configured database and credentials are valid.
- Starting the backend and inspecting application logs.
- Testing valid and invalid request bodies.
- Verifying expected HTTP status codes.
- Confirming that create, read, update, and delete operations persist correctly.
- Testing authentication and protected endpoints where implemented.
- Running the project's automated tests when available.

The CO-4-1 project contains a Spring Boot context-load test scaffold. The presence of a test file is not proof that the test passes.

Likewise, documented API examples and expected outputs should not be interpreted as executed test results unless accompanied by actual verification evidence.

---

## Current Scope and Limitations

This repository is a collection of practicals and project implementations rather than a single integrated application.

Some folders are more complete than others. In particular:

- **CO-3:** The tracked source contains the student model and controller, but lacks a complete runnable application setup.
- **CO-4-1:** The main Java source structure, Maven configuration, and application properties are present.
- **CO-5:** The backend source and SQL setup are present, but the checked-in frontend is incomplete.
- **Week-level practicals:** Some work is represented primarily by its report document.
- **Testing:** The repository contents do not establish that every application or endpoint has been executed and verified.

These distinctions are intentional: documentation should reflect the checked-in implementation instead of implying that every project is production-ready.

---

## Future Improvements

Potential improvements across the repository include:

- Add a root-level project index with links to each practical.
- Complete the missing CO-3 application bootstrap and route setup.
- Restore the CO-5 frontend source and dependency manifest.
- Add reproducible database initialization scripts for each application.
- Use environment-based configuration for all database credentials.
- Add automated unit and integration tests.
- Standardize API error responses and request validation.
- Add API specifications and reproducible Postman collections.
- Exclude generated build artifacts and installed dependency directories from version control.
- Add screenshots and verified execution evidence where appropriate.
- Introduce database migrations for schema changes.
- Improve setup instructions so each project can be run independently.

---

## Author

**Vinay**

Database Systems & Database Engineering practicals, implementation work, and project documentation.

- **GitHub:** [@venkataramavinaybandla-crypto](https://github.com/venkataramavinaybandla-crypto)
- **Repository:** [DBS-DBE](https://github.com/venkataramavinaybandla-crypto/DBS-DBE)

---

<p align="center">
  <strong>From data models to working APIs — learning database engineering through implementation.</strong>
</p>
