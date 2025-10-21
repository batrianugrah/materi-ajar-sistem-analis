# Unit 11: Contoh Output - Struktur Perangkat Lunak

## 1. Arsitektur Sistem Overview

### 1.1 High-Level Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                    Sistem Manajemen Perpustakaan Digital        │
├─────────────────────────────────────────────────────────────────┤
│  Frontend Layer (React.js)                                      │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│  │   User UI   │ │ Librarian UI│ │ Manager UI  │ │  Admin UI   │ │
│  └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
├─────────────────────────────────────────────────────────────────┤
│  API Gateway Layer (Nginx + Load Balancer)                      │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│  │   Auth API  │ │  Book API   │ │ Borrow API │ │ Report API  │ │
│  └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
├─────────────────────────────────────────────────────────────────┤
│  Business Logic Layer (Node.js + Express.js)                     │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│  │ User Service│ │ Book Service│ │Borrow Service│ │Report Service│ │
│  └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
├─────────────────────────────────────────────────────────────────┤
│  Data Access Layer (PostgreSQL + Redis)                        │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│  │   Users DB  │ │   Books DB  │ │Transactions│ │   Cache     │ │
│  └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
└─────────────────────────────────────────────────────────────────┘
```

### 1.2 Architecture Principles

#### Layered Architecture
- **Presentation Layer:** User interfaces dan user experience
- **API Gateway Layer:** Request routing, authentication, rate limiting
- **Business Logic Layer:** Core business logic dan rules
- **Data Access Layer:** Database operations dan caching

#### Separation of Concerns
- **User Management:** Authentication, authorization, profile management
- **Book Management:** Catalog management, search, categorization
- **Borrowing System:** Borrowing, returning, fine calculation
- **Reporting System:** Statistics, analytics, compliance reports

#### Scalability Design
- **Horizontal Scaling:** Multiple instances untuk high availability
- **Vertical Scaling:** Resource optimization untuk performance
- **Caching Strategy:** Redis untuk session dan data caching
- **Load Balancing:** Nginx untuk request distribution

## 2. Komponen Arsitektur Detail

### 2.1 Frontend Layer

#### User Interface Components
```
Frontend Architecture
├── Public Components
│   ├── Header
│   ├── Footer
│   ├── Navigation
│   └── Sidebar
├── User Components
│   ├── LoginForm
│   ├── RegisterForm
│   ├── ProfileForm
│   └── Dashboard
├── Book Components
│   ├── BookList
│   ├── BookCard
│   ├── BookDetail
│   ├── SearchForm
│   └── BookFilter
├── Borrowing Components
│   ├── BorrowForm
│   ├── ReturnForm
│   ├── BorrowingHistory
│   └── FineDisplay
└── Admin Components
    ├── UserManagement
    ├── BookManagement
    ├── ReportDashboard
    └── SystemSettings
```

#### Technology Stack
- **Framework:** React.js 18.2.0
- **State Management:** Redux Toolkit
- **Routing:** React Router v6
- **UI Library:** Material-UI v5
- **HTTP Client:** Axios
- **Form Handling:** React Hook Form
- **Validation:** Yup

### 2.2 API Gateway Layer

#### API Gateway Components
```
API Gateway Architecture
├── Authentication Service
│   ├── JWT Token Validation
│   ├── Role-based Access Control
│   ├── Session Management
│   └── Rate Limiting
├── Request Routing
│   ├── User API Routes
│   ├── Book API Routes
│   ├── Borrowing API Routes
│   └── Report API Routes
├── Middleware
│   ├── CORS Handling
│   ├── Request Logging
│   ├── Error Handling
│   └── Response Formatting
└── Load Balancing
    ├── Round Robin
    ├── Least Connections
    ├── Health Checks
    └── Failover
```

#### Technology Stack
- **Web Server:** Nginx 1.18.0
- **Load Balancer:** Nginx Load Balancer
- **SSL/TLS:** Let's Encrypt
- **Rate Limiting:** Nginx Rate Limiting
- **Caching:** Nginx Caching

### 2.3 Business Logic Layer

#### Service Architecture
```
Business Logic Layer
├── User Service
│   ├── Authentication Logic
│   ├── Authorization Logic
│   ├── Profile Management
│   └── Role Management
├── Book Service
│   ├── Book CRUD Operations
│   ├── Search Logic
│   ├── Category Management
│   └── Book Status Management
├── Borrowing Service
│   ├── Borrowing Logic
│   ├── Returning Logic
│   ├── Fine Calculation
│   └── History Management
├── Report Service
│   ├── Statistics Generation
│   ├── Analytics Processing
│   ├── Report Formatting
│   └── Data Aggregation
└── Notification Service
    ├── Email Notifications
    ├── SMS Notifications
    ├── Push Notifications
    └── Notification Scheduling
```

#### Technology Stack
- **Runtime:** Node.js 16.18.0
- **Framework:** Express.js 4.18.0
- **Authentication:** JWT, bcrypt
- **Validation:** Joi
- **Logging:** Winston
- **Process Management:** PM2

### 2.4 Data Access Layer

#### Database Architecture
```
Data Access Layer
├── Primary Database (PostgreSQL)
│   ├── Users Table
│   ├── Books Table
│   ├── Transactions Table
│   ├── Categories Table
│   └── Fines Table
├── Cache Database (Redis)
│   ├── Session Cache
│   ├── Query Cache
│   ├── User Cache
│   └── Book Cache
├── File Storage
│   ├── Book Covers
│   ├── User Avatars
│   ├── Documents
│   └── Reports
└── External Services
    ├── Email Service
    ├── SMS Service
    ├── ISBN Service
    └── Payment Gateway
```

#### Technology Stack
- **Primary Database:** PostgreSQL 14.5
- **Cache Database:** Redis 6.2.7
- **File Storage:** AWS S3
- **Email Service:** SendGrid
- **SMS Service:** Twilio

## 3. Database Design

### 3.1 Entity Relationship Diagram

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│      Users       │    │      Books       │    │   Transactions  │
├─────────────────┤    ├─────────────────┤    ├─────────────────┤
│ id (PK)         │    │ id (PK)         │    │ id (PK)         │
│ name            │    │ title           │    │ user_id (FK)    │
│ email           │    │ author          │    │ book_id (FK)    │
│ password        │    │ isbn            │    │ type            │
│ role            │    │ publisher       │    │ borrow_date     │
│ phone           │    │ publication_year│    │ due_date        │
│ status          │    │ category        │    │ return_date     │
│ created_at      │    │ description     │    │ fine_amount     │
│ updated_at      │    │ cover_image     │    │ status          │
└─────────────────┘    │ status          │    │ created_at      │
                       │ created_at      │    │ updated_at      │
                       │ updated_at      │    └─────────────────┘
                       └─────────────────┘
```

### 3.2 Database Schema

#### Users Table
```sql
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL,
    role VARCHAR(20) NOT NULL CHECK (role IN ('student', 'librarian', 'manager', 'admin')),
    phone VARCHAR(20),
    status VARCHAR(20) DEFAULT 'active' CHECK (status IN ('active', 'inactive', 'suspended')),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Indexes
CREATE INDEX idx_users_email ON users(email);
CREATE INDEX idx_users_role ON users(role);
CREATE INDEX idx_users_status ON users(status);
```

#### Books Table
```sql
CREATE TABLE books (
    id SERIAL PRIMARY KEY,
    title VARCHAR(200) NOT NULL,
    author VARCHAR(100) NOT NULL,
    isbn VARCHAR(20) UNIQUE,
    publisher VARCHAR(100),
    publication_year INTEGER CHECK (publication_year >= 1900 AND publication_year <= 2024),
    category VARCHAR(50),
    description TEXT,
    cover_image VARCHAR(255),
    status VARCHAR(20) DEFAULT 'available' CHECK (status IN ('available', 'borrowed', 'reserved', 'maintenance')),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Indexes
CREATE INDEX idx_books_title ON books(title);
CREATE INDEX idx_books_author ON books(author);
CREATE INDEX idx_books_isbn ON books(isbn);
CREATE INDEX idx_books_category ON books(category);
CREATE INDEX idx_books_status ON books(status);
```

#### Transactions Table
```sql
CREATE TABLE transactions (
    id SERIAL PRIMARY KEY,
    user_id INTEGER NOT NULL REFERENCES users(id) ON DELETE CASCADE,
    book_id INTEGER NOT NULL REFERENCES books(id) ON DELETE CASCADE,
    type VARCHAR(20) NOT NULL CHECK (type IN ('borrow', 'return', 'renew', 'reserve')),
    borrow_date DATE,
    due_date DATE,
    return_date DATE,
    fine_amount DECIMAL(10,2) DEFAULT 0,
    status VARCHAR(20) DEFAULT 'active' CHECK (status IN ('active', 'completed', 'overdue', 'cancelled')),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Indexes
CREATE INDEX idx_transactions_user_id ON transactions(user_id);
CREATE INDEX idx_transactions_book_id ON transactions(book_id);
CREATE INDEX idx_transactions_type ON transactions(type);
CREATE INDEX idx_transactions_status ON transactions(status);
CREATE INDEX idx_transactions_due_date ON transactions(due_date);
```

### 3.3 Database Relationships

#### Primary Relationships
- **Users → Transactions:** One-to-Many (1 user can have many transactions)
- **Books → Transactions:** One-to-Many (1 book can have many transactions)
- **Users → Users:** Self-referencing (manager can manage librarians)

#### Foreign Key Constraints
```sql
-- Users to Transactions
ALTER TABLE transactions 
ADD CONSTRAINT fk_transactions_user_id 
FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE;

-- Books to Transactions
ALTER TABLE transactions 
ADD CONSTRAINT fk_transactions_book_id 
FOREIGN KEY (book_id) REFERENCES books(id) ON DELETE CASCADE;
```

## 4. API Design

### 4.1 RESTful API Endpoints

#### User Management API
```
GET    /api/users                    # Get all users
GET    /api/users/:id                # Get user by ID
POST   /api/users                    # Create new user
PUT    /api/users/:id                # Update user
DELETE /api/users/:id                # Delete user
POST   /api/users/login              # User login
POST   /api/users/logout             # User logout
POST   /api/users/register           # User registration
GET    /api/users/profile            # Get user profile
PUT    /api/users/profile            # Update user profile
```

#### Book Management API
```
GET    /api/books                    # Get all books
GET    /api/books/:id                # Get book by ID
POST   /api/books                    # Create new book
PUT    /api/books/:id                # Update book
DELETE /api/books/:id                # Delete book
GET    /api/books/search             # Search books
GET    /api/books/categories         # Get book categories
GET    /api/books/:id/availability   # Check book availability
```

#### Borrowing System API
```
GET    /api/transactions              # Get all transactions
GET    /api/transactions/:id         # Get transaction by ID
POST   /api/transactions/borrow      # Borrow a book
POST   /api/transactions/return      # Return a book
POST   /api/transactions/renew       # Renew a book
GET    /api/transactions/user/:id    # Get user transactions
GET    /api/transactions/book/:id    # Get book transactions
GET    /api/transactions/overdue     # Get overdue transactions
```

#### Reporting API
```
GET    /api/reports/statistics       # Get system statistics
GET    /api/reports/users            # Get user reports
GET    /api/reports/books            # Get book reports
GET    /api/reports/transactions     # Get transaction reports
GET    /api/reports/fines            # Get fine reports
POST   /api/reports/generate         # Generate custom report
```

### 4.2 API Response Format

#### Success Response
```json
{
  "success": true,
  "data": {
    "id": 1,
    "name": "John Doe",
    "email": "john@example.com",
    "role": "student"
  },
  "message": "User retrieved successfully",
  "timestamp": "2024-03-15T10:30:00Z"
}
```

#### Error Response
```json
{
  "success": false,
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Invalid input data",
    "details": [
      {
        "field": "email",
        "message": "Email format is invalid"
      }
    ]
  },
  "timestamp": "2024-03-15T10:30:00Z"
}
```

## 5. Security Architecture

### 5.1 Authentication & Authorization

#### Authentication Flow
```
1. User submits credentials
2. Server validates credentials
3. Server generates JWT token
4. Server returns token to client
5. Client stores token
6. Client includes token in subsequent requests
7. Server validates token for each request
```

#### Authorization Levels
- **Public:** No authentication required
- **User:** Basic user authentication
- **Librarian:** Librarian role required
- **Manager:** Manager role required
- **Admin:** Admin role required

#### Security Measures
- **Password Hashing:** bcrypt with salt
- **JWT Tokens:** Secure token generation
- **Rate Limiting:** API rate limiting
- **CORS:** Cross-origin resource sharing
- **HTTPS:** SSL/TLS encryption
- **Input Validation:** Request validation
- **SQL Injection Prevention:** Parameterized queries

### 5.2 Data Security

#### Data Encryption
- **At Rest:** Database encryption
- **In Transit:** HTTPS/TLS encryption
- **Sensitive Data:** Field-level encryption
- **Backup:** Encrypted backups

#### Access Control
- **Database Access:** Role-based access
- **API Access:** Token-based authentication
- **File Access:** Permission-based access
- **Admin Access:** Multi-factor authentication

## 6. Deployment Architecture

### 6.1 Production Environment

#### Server Configuration
```
Production Environment
├── Web Servers (2x)
│   ├── Nginx Load Balancer
│   ├── SSL Termination
│   └── Static File Serving
├── Application Servers (3x)
│   ├── Node.js Applications
│   ├── PM2 Process Manager
│   └── Health Monitoring
├── Database Servers (2x)
│   ├── PostgreSQL Primary
│   ├── PostgreSQL Replica
│   └── Redis Cache
└── File Storage
    ├── AWS S3
    ├── CDN Distribution
    └── Backup Storage
```

#### Load Balancing Strategy
- **Round Robin:** Request distribution
- **Health Checks:** Server monitoring
- **Failover:** Automatic failover
- **SSL Termination:** SSL handling

### 6.2 Monitoring & Logging

#### Application Monitoring
- **Performance Metrics:** Response time, throughput
- **Error Tracking:** Error logging and alerting
- **User Analytics:** User behavior tracking
- **System Health:** Server and database monitoring

#### Logging Strategy
- **Application Logs:** Winston logging
- **Access Logs:** Nginx access logs
- **Error Logs:** Error tracking and alerting
- **Audit Logs:** Security and compliance logging

---

**Status:** Completed  
**Next Step:** Begin Unit 12 - Komponen Perangkat Lunak
