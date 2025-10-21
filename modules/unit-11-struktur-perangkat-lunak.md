# Unit 11: Merancang Struktur Perangkat Lunak
**Kode Unit:** J.62SAD00.011.1

## Tujuan Pembelajaran
Setelah menyelesaikan unit ini, peserta mampu:
- Merancang system architecture yang scalable
- Membuat architectural diagrams yang jelas
- Mengidentifikasi komponen-komponen sistem
- Merancang database schema yang optimal
- Membuat integration design yang efektif

## Materi Teori

### 1. System Architecture Overview

#### A. Architecture Patterns
**Layered Architecture:**
- Presentation Layer
- Business Logic Layer
- Data Access Layer
- Database Layer

**Microservices Architecture:**
- Service-oriented design
- Independent services
- API communication
- Scalable deployment

**Event-Driven Architecture:**
- Event-based communication
- Asynchronous processing
- Loose coupling
- High scalability

#### B. Architecture Principles
**Separation of Concerns:**
- Each layer has specific responsibilities
- Clear boundaries between layers
- Independent development
- Easier maintenance

**Scalability:**
- Horizontal scaling
- Load balancing
- Caching strategies
- Performance optimization

**Security:**
- Defense in depth
- Authentication and authorization
- Data encryption
- Security monitoring

### 2. Architectural Diagrams

#### A. System Architecture Diagram
**Components:**
- External systems
- Web servers
- Application servers
- Database servers
- Load balancers

**Connections:**
- Network connections
- Data flow
- Communication protocols
- Security boundaries

#### B. Component Diagram
**Components:**
- User interface components
- Business logic components
- Data access components
- Integration components

**Relationships:**
- Dependencies
- Interfaces
- Data flow
- Control flow

#### C. Deployment Diagram
**Nodes:**
- Physical servers
- Virtual machines
- Cloud instances
- Network devices

**Artifacts:**
- Applications
- Databases
- Configuration files
- Log files

### 3. Database Design

#### A. Database Schema Design
**Entity Design:**
- Identify entities
- Define attributes
- Establish relationships
- Normalize data

**Table Design:**
- Primary keys
- Foreign keys
- Indexes
- Constraints

**Relationship Design:**
- One-to-one
- One-to-many
- Many-to-many
- Self-referencing

#### B. Database Optimization
**Performance Optimization:**
- Indexing strategies
- Query optimization
- Partitioning
- Caching

**Security Optimization:**
- Access control
- Data encryption
- Audit logging
- Backup strategies

### 4. Integration Design

#### A. Integration Patterns
**API Integration:**
- RESTful APIs
- SOAP services
- GraphQL
- Webhooks

**Message Integration:**
- Message queues
- Event streaming
- Pub/Sub patterns
- Asynchronous processing

**Data Integration:**
- ETL processes
- Data synchronization
- Real-time streaming
- Batch processing

#### B. Integration Security
**Authentication:**
- API keys
- OAuth 2.0
- JWT tokens
- Certificate-based

**Authorization:**
- Role-based access
- Permission management
- Resource protection
- Audit logging

## Latihan Praktis

### Exercise 1: System Architecture Design
**Tugas:** Rancang system architecture untuk sistem perpustakaan

**Langkah:**
1. Identifikasi requirements
2. Pilih architecture pattern
3. Rancang system components
4. Buat architectural diagrams
5. Validasi architecture

### Exercise 2: Database Schema Design
**Tugas:** Rancang database schema untuk sistem perpustakaan

**Langkah:**
1. Identifikasi entities
2. Definisikan attributes
3. Buat relationships
4. Normalize schema
5. Optimasi performance

### Exercise 3: Integration Design
**Tugas:** Rancang integration untuk sistem perpustakaan

**Langkah:**
1. Identifikasi integration points
2. Pilih integration patterns
3. Rancang API design
4. Buat security design
5. Validasi integration

### Exercise 4: Architecture Validation
**Tugas:** Validasi system architecture

**Langkah:**
1. Review architecture
2. Test scalability
3. Test security
4. Test performance
5. Buat validation report

## Proyek Integrasi: System Architecture

### Architecture Design untuk Sistem Perpustakaan

#### 1. System Architecture Overview

##### Architecture Pattern: Layered Architecture
**Presentation Layer:**
- React.js frontend
- Material-UI components
- Responsive design
- Mobile support

**Business Logic Layer:**
- Node.js backend
- Express.js framework
- Business rules
- Workflow management

**Data Access Layer:**
- ORM (Sequelize)
- Database abstraction
- Query optimization
- Caching layer

**Database Layer:**
- PostgreSQL database
- Data storage
- Backup and recovery
- Performance optimization

#### 2. System Architecture Diagram

```
[Users] --> [Load Balancer] --> [Web Server] --> [Application Server] --> [Database Server]
    |              |                |                    |                    |
    |              |                |                    |                    |
[Students]    [Nginx]         [React.js]           [Node.js]            [PostgreSQL]
[Librarians]  [SSL/TLS]       [Material-UI]       [Express.js]         [Redis Cache]
[Managers]    [Firewall]       [PWA]               [JWT Auth]          [Backup]
```

#### 3. Component Design

##### Frontend Components
**User Interface Components:**
- LoginForm
- BookSearch
- BookList
- BookDetail
- BorrowingForm
- UserProfile

**Business Logic Components:**
- AuthenticationService
- BookService
- BorrowingService
- UserService
- NotificationService

**Data Access Components:**
- BookRepository
- UserRepository
- BorrowingRepository
- NotificationRepository

##### Backend Components
**API Controllers:**
- AuthController
- BookController
- BorrowingController
- UserController
- ReportController

**Business Services:**
- AuthenticationService
- BookManagementService
- BorrowingService
- FineCalculationService
- NotificationService

**Data Access Layer:**
- BookRepository
- UserRepository
- BorrowingRepository
- FineRepository
- NotificationRepository

#### 4. Database Schema Design

##### Entity Relationship Diagram
```
[Users] ----< [Borrowings] >---- [Books]
    |              |                |
    |              |                |
[Profiles]    [Fines]         [Categories]
    |              |                |
    |              |                |
[Roles]       [Payments]      [Authors]
```

##### Database Tables
**Users Table:**
- user_id (Primary Key)
- username
- email
- password_hash
- role_id
- created_at
- updated_at

**Books Table:**
- book_id (Primary Key)
- title
- author
- isbn
- category_id
- availability_status
- created_at
- updated_at

**Borrowings Table:**
- borrowing_id (Primary Key)
- user_id (Foreign Key)
- book_id (Foreign Key)
- borrow_date
- due_date
- return_date
- status
- created_at
- updated_at

**Categories Table:**
- category_id (Primary Key)
- name
- description
- created_at
- updated_at

**Fines Table:**
- fine_id (Primary Key)
- borrowing_id (Foreign Key)
- amount
- due_date
- payment_date
- status
- created_at
- updated_at

#### 5. Integration Design

##### API Design
**Authentication API:**
- POST /api/auth/login
- POST /api/auth/logout
- POST /api/auth/refresh
- GET /api/auth/profile

**Book Management API:**
- GET /api/books
- GET /api/books/:id
- POST /api/books
- PUT /api/books/:id
- DELETE /api/books/:id

**Borrowing API:**
- POST /api/borrowings
- GET /api/borrowings
- PUT /api/borrowings/:id/return
- GET /api/borrowings/:id

**User Management API:**
- GET /api/users
- GET /api/users/:id
- POST /api/users
- PUT /api/users/:id
- DELETE /api/users/:id

##### External Integrations
**Email Service Integration:**
- SMTP server configuration
- Email templates
- Notification sending
- Delivery tracking

**SMS Service Integration:**
- SMS gateway configuration
- Message templates
- Notification sending
- Delivery tracking

**Payment Gateway Integration:**
- Payment processing
- Transaction management
- Refund handling
- Security compliance

#### 6. Security Architecture

##### Authentication and Authorization
**Authentication:**
- JWT token-based authentication
- Password hashing with bcrypt
- Session management
- Multi-factor authentication (future)

**Authorization:**
- Role-based access control
- Permission-based access
- Resource protection
- Audit logging

##### Data Security
**Data Encryption:**
- Encryption at rest
- Encryption in transit
- Key management
- Certificate management

**Network Security:**
- HTTPS/TLS encryption
- Firewall configuration
- VPN access
- Intrusion detection

#### 7. Performance Architecture

##### Caching Strategy
**Application Caching:**
- Redis for session storage
- Memory caching for frequently accessed data
- Query result caching
- API response caching

**Database Optimization:**
- Indexing strategies
- Query optimization
- Connection pooling
- Read replicas

##### Scalability Design
**Horizontal Scaling:**
- Load balancer configuration
- Multiple application servers
- Database clustering
- CDN integration

**Vertical Scaling:**
- Server resource optimization
- Memory optimization
- CPU optimization
- Storage optimization

#### 8. Deployment Architecture

##### Development Environment
**Local Development:**
- Docker containers
- Local database
- Development tools
- Testing frameworks

**Development Server:**
- Shared development environment
- Version control integration
- Automated testing
- Code review process

##### Production Environment
**Production Server:**
- High availability setup
- Load balancing
- Monitoring and alerting
- Backup and recovery

**Cloud Deployment:**
- AWS EC2 instances
- RDS database
- S3 storage
- CloudFront CDN

## Deliverables Unit 11:
1. **System Architecture Document** - Dokumen arsitektur lengkap
2. **Architectural Diagrams** - Diagram arsitektur detail
3. **Component Specifications** - Spesifikasi komponen
4. **Database Schema** - Schema database lengkap
5. **Integration Design** - Rancangan integrasi
6. **Security Architecture** - Arsitektur keamanan
7. **Performance Architecture** - Arsitektur performa
8. **Deployment Architecture** - Arsitektur deployment

## Assessment Criteria
- [ ] Mampu merancang system architecture yang scalable
- [ ] Mampu membuat architectural diagrams yang jelas
- [ ] Mampu mengidentifikasi komponen-komponen sistem
- [ ] Mampu merancang database schema yang optimal
- [ ] Mampu membuat integration design yang efektif

## Referensi
- [Software Architecture Patterns](https://www.oreilly.com/)
- [Database Design Best Practices](https://www.postgresql.org/)
- [API Design Guidelines](https://restfulapi.net/)
- [Security Architecture](https://www.owasp.org/)

---
**Previous Unit:** [Unit 10 - Validasi Spesifikasi](../modules/unit-10-validasi-spesifikasi.md)  
**Next Unit:** [Unit 12 - Komponen Perangkat Lunak](../modules/unit-12-komponen-perangkat-lunak.md)




