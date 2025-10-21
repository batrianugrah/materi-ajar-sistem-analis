# Unit 8: Menyusun Spesifikasi Kebutuhan Perangkat Lunak
**Kode Unit:** J.62SAD00.008.1

## Tujuan Pembelajaran
Setelah menyelesaikan unit ini, peserta mampu:
- Membuat functional requirements yang detail
- Membuat non-functional requirements yang komprehensif
- Mendefinisikan business rules yang jelas
- Mengidentifikasi constraints dan assumptions
- Membuat requirements validation yang efektif

## Materi Teori

### 1. Functional Requirements

#### A. Karakteristik Functional Requirements
- **Behavioral:** Mendeskripsikan apa yang sistem lakukan
- **Specific:** Spesifik dan tidak ambigu
- **Testable:** Dapat diuji dan divalidasi
- **Complete:** Lengkap dan konsisten

#### B. Format Functional Requirements
**Template:** The system shall [action] [condition] [result]

**Contoh:**
- The system shall allow users to search books by title, author, or ISBN
- The system shall calculate fines automatically when books are overdue
- The system shall send email notifications when reserved books are available

#### C. Kategori Functional Requirements
**User Interface Requirements:**
- Layout dan navigation
- Input validation
- Error handling
- User feedback

**Business Logic Requirements:**
- Business rules
- Calculations
- Workflows
- Validations

**Data Requirements:**
- Data input
- Data processing
- Data output
- Data storage

**Integration Requirements:**
- External systems
- APIs
- Data exchange
- Protocols

### 2. Non-Functional Requirements

#### A. Performance Requirements
**Response Time:**
- Page load time < 2 seconds
- Search results < 1 second
- Report generation < 5 seconds

**Throughput:**
- Support 100 concurrent users
- Handle 1000 transactions per hour
- Process 10,000 records per batch

**Scalability:**
- Horizontal scaling capability
- Load balancing support
- Database partitioning

#### B. Security Requirements
**Authentication:**
- User login/logout
- Password policies
- Session management
- Multi-factor authentication

**Authorization:**
- Role-based access control
- Permission management
- Resource access control
- Audit logging

**Data Security:**
- Data encryption
- Secure transmission
- Data backup
- Data retention

#### C. Usability Requirements
**User Interface:**
- Intuitive navigation
- Consistent design
- Responsive layout
- Accessibility compliance

**User Experience:**
- Easy to learn
- Efficient to use
- Error prevention
- Help system

#### D. Reliability Requirements
**Availability:**
- 99.9% uptime
- 24/7 operation
- Maintenance windows
- Disaster recovery

**Fault Tolerance:**
- Error handling
- Graceful degradation
- Recovery procedures
- Backup systems

### 3. Business Rules

#### A. Definisi Business Rules
Business rules adalah aturan bisnis yang mengatur bagaimana sistem beroperasi dalam konteks bisnis.

#### B. Kategori Business Rules
**Data Rules:**
- Data validation rules
- Data integrity rules
- Data format rules
- Data relationship rules

**Process Rules:**
- Workflow rules
- Approval rules
- Notification rules
- Escalation rules

**Policy Rules:**
- Security policies
- Access policies
- Compliance policies
- Operational policies

#### C. Format Business Rules
**Template:** If [condition], then [action]

**Contoh:**
- If a student has overdue books, then they cannot borrow new books
- If a book is reserved, then it cannot be borrowed by other students
- If a student returns a book late, then a fine is calculated

### 4. Constraints dan Assumptions

#### A. Constraints
**Technical Constraints:**
- Technology limitations
- Performance constraints
- Security constraints
- Integration constraints

**Business Constraints:**
- Budget limitations
- Timeline constraints
- Resource constraints
- Regulatory constraints

**Environmental Constraints:**
- Infrastructure limitations
- Network constraints
- Hardware constraints
- Software constraints

#### B. Assumptions
**Technical Assumptions:**
- Technology availability
- Performance assumptions
- Security assumptions
- Integration assumptions

**Business Assumptions:**
- User behavior
- Business processes
- Market conditions
- Regulatory environment

### 5. Requirements Validation

#### A. Validation Techniques
**Review:**
- Peer review
- Stakeholder review
- Expert review
- Cross-reference check

**Testing:**
- Unit testing
- Integration testing
- System testing
- User acceptance testing

**Prototyping:**
- UI prototyping
- Workflow prototyping
- Data flow prototyping
- Integration prototyping

#### B. Validation Criteria
**Completeness:**
- All requirements covered
- No missing requirements
- Complete coverage
- No gaps

**Consistency:**
- No conflicting requirements
- Consistent terminology
- Consistent format
- Consistent level of detail

**Correctness:**
- Accurate requirements
- Correct understanding
- Proper implementation
- Valid assumptions

## Latihan Praktis

### Exercise 1: Functional Requirements
**Tugas:** Buat functional requirements untuk sistem perpustakaan

**Langkah:**
1. Identifikasi fitur-fitur utama
2. Tulis functional requirements untuk setiap fitur
3. Kategorikan berdasarkan jenis
4. Validasi completeness dan consistency
5. Buat requirements document

### Exercise 2: Non-Functional Requirements
**Tugas:** Buat non-functional requirements yang komprehensif

**Langkah:**
1. Identifikasi performance requirements
2. Identifikasi security requirements
3. Identifikasi usability requirements
4. Identifikasi reliability requirements
5. Buat non-functional requirements document

### Exercise 3: Business Rules
**Tugas:** Definisikan business rules untuk sistem perpustakaan

**Langkah:**
1. Identifikasi business processes
2. Definisikan business rules
3. Kategorikan berdasarkan jenis
4. Validasi dengan stakeholders
5. Buat business rules document

### Exercise 4: Requirements Validation
**Tugas:** Lakukan validation requirements

**Langkah:**
1. Review requirements completeness
2. Check requirements consistency
3. Validate requirements correctness
4. Test requirements dengan stakeholders
5. Buat validation report

## Proyek Integrasi: Spesifikasi Kebutuhan

### Functional Requirements untuk Sistem Perpustakaan

#### 1. User Management
**REQ-F-001: User Registration**
- The system shall allow new users to register with email and password
- The system shall validate email format and password strength
- The system shall send confirmation email after registration

**REQ-F-002: User Authentication**
- The system shall authenticate users with username and password
- The system shall support role-based access control
- The system shall maintain user sessions with timeout

**REQ-F-003: User Profile Management**
- The system shall allow users to update their profile information
- The system shall validate profile data before saving
- The system shall maintain profile history

#### 2. Book Management
**REQ-F-004: Book Search**
- The system shall allow users to search books by title, author, ISBN
- The system shall support advanced search with multiple criteria
- The system shall display search results with pagination

**REQ-F-005: Book Catalog**
- The system shall maintain a catalog of all books
- The system shall support book categorization
- The system shall display book details including availability

**REQ-F-006: Book Borrowing**
- The system shall allow students to borrow books
- The system shall check borrowing limits and book availability
- The system shall set due dates automatically

#### 3. Reservation System
**REQ-F-007: Book Reservation**
- The system shall allow students to reserve books
- The system shall maintain reservation queue
- The system shall notify students when reserved books are available

**REQ-F-008: Reservation Management**
- The system shall allow students to cancel reservations
- The system shall automatically cancel expired reservations
- The system shall maintain reservation history

#### 4. Fine Management
**REQ-F-009: Fine Calculation**
- The system shall calculate fines for overdue books
- The system shall apply different fine rates for different book types
- The system shall track fine payment history

**REQ-F-010: Fine Payment**
- The system shall allow students to pay fines online
- The system shall process fine payments securely
- The system shall update fine status after payment

### Non-Functional Requirements

#### 1. Performance Requirements
**REQ-NF-001: Response Time**
- The system shall respond to user requests within 2 seconds
- The system shall display search results within 1 second
- The system shall generate reports within 5 seconds

**REQ-NF-002: Throughput**
- The system shall support 100 concurrent users
- The system shall handle 1000 transactions per hour
- The system shall process 10,000 books in database

**REQ-NF-003: Scalability**
- The system shall support horizontal scaling
- The system shall handle increased load gracefully
- The system shall maintain performance under load

#### 2. Security Requirements
**REQ-NF-004: Authentication**
- The system shall implement secure authentication
- The system shall enforce password policies
- The system shall support session management

**REQ-NF-005: Authorization**
- The system shall implement role-based access control
- The system shall enforce permission-based access
- The system shall maintain audit logs

**REQ-NF-006: Data Security**
- The system shall encrypt sensitive data
- The system shall secure data transmission
- The system shall implement data backup

#### 3. Usability Requirements
**REQ-NF-007: User Interface**
- The system shall have intuitive user interface
- The system shall be accessible via web browser
- The system shall support mobile devices

**REQ-NF-008: User Experience**
- The system shall be easy to learn and use
- The system shall provide helpful error messages
- The system shall include help documentation

#### 4. Reliability Requirements
**REQ-NF-009: Availability**
- The system shall maintain 99.9% uptime
- The system shall operate 24/7
- The system shall have maintenance windows

**REQ-NF-010: Fault Tolerance**
- The system shall handle errors gracefully
- The system shall provide fallback mechanisms
- The system shall implement recovery procedures

### Business Rules

#### 1. Borrowing Rules
**BR-001:** If a student has overdue books, then they cannot borrow new books
**BR-002:** If a student has reached borrowing limit, then they cannot borrow more books
**BR-003:** If a book is reserved, then it cannot be borrowed by other students

#### 2. Fine Rules
**BR-004:** If a book is returned late, then a fine is calculated based on days overdue
**BR-005:** If a student has unpaid fines, then they cannot borrow new books
**BR-006:** If a fine is not paid within 30 days, then the student account is blocked

#### 3. Reservation Rules
**BR-007:** If a book is available, then it cannot be reserved
**BR-008:** If a reservation is not claimed within 3 days, then it is automatically cancelled
**BR-009:** If a student has active reservations, then they cannot reserve more books

### Constraints dan Assumptions

#### 1. Technical Constraints
**TC-001:** System must be web-based and accessible via standard browsers
**TC-002:** System must support PostgreSQL database
**TC-003:** System must be deployable on Linux servers
**TC-004:** System must support HTTPS encryption

#### 2. Business Constraints
**BC-001:** Development budget is limited to $50,000
**BC-002:** System must be delivered within 6 months
**BC-003:** System must support maximum 1000 users
**BC-004:** System must comply with university IT policies

#### 3. Assumptions
**A-001:** Users have basic computer literacy
**A-002:** Internet connection is available
**A-003:** Users have valid email addresses
**A-004:** University network is secure

## Deliverables Unit 8:
1. **Functional Requirements Document** - Requirements fungsional lengkap
2. **Non-Functional Requirements Document** - Requirements non-fungsional
3. **Business Rules Document** - Aturan bisnis yang jelas
4. **Constraints and Assumptions Document** - Constraints dan assumptions
5. **Requirements Validation Report** - Laporan validasi requirements

## Assessment Criteria
- [ ] Mampu membuat functional requirements yang detail
- [ ] Mampu membuat non-functional requirements yang komprehensif
- [ ] Mampu mendefinisikan business rules yang jelas
- [ ] Mampu mengidentifikasi constraints dan assumptions
- [ ] Mampu melakukan requirements validation

## Referensi
- [IEEE 830 - Software Requirements Specification](https://www.ieee.org/)
- [Requirements Engineering Best Practices](https://www.ireb.org/)
- [Business Rules Management](https://www.businessrulesgroup.org/)
- [Non-Functional Requirements](https://www.omg.org/)

---
**Previous Unit:** [Unit 7 - Software Environment](../modules/unit-07-software-environment.md)  
**Next Unit:** [Unit 9 - Review Kebutuhan](../modules/unit-09-review-kebutuhan.md)




