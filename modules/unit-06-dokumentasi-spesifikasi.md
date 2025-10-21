# Unit 6: Membuat Kebutuhan Dokumentasi Spesifikasi Perangkat Lunak
**Kode Unit:** J.62SAD00.006.1

## Tujuan Pembelajaran
Setelah menyelesaikan unit ini, peserta mampu:
- Membuat Software Requirements Specification (SRS) yang komprehensif
- Menulis user stories yang efektif
- Membuat use cases yang detail
- Mendefinisikan acceptance criteria yang jelas
- Membuat requirements traceability matrix

## Materi Teori

### 1. Software Requirements Specification (SRS)

#### A. Struktur SRS
**1. Introduction**
- Purpose
- Scope
- Definitions
- References

**2. Overall Description**
- Product Perspective
- Product Functions
- User Characteristics
- Constraints
- Assumptions

**3. Specific Requirements**
- Functional Requirements
- Non-Functional Requirements
- Interface Requirements
- Performance Requirements
- Security Requirements

**4. Appendices**
- Glossary
- References
- Index

#### B. Best Practices SRS
- **Clear and Unambiguous:** Setiap requirement harus jelas dan tidak ambigu
- **Complete:** Mencakup semua kebutuhan sistem
- **Consistent:** Tidak ada konflik antar requirements
- **Traceable:** Dapat ditelusuri ke sumbernya
- **Verifiable:** Dapat diuji dan divalidasi

### 2. User Stories

#### A. Format User Story
**Template:** As a [user type], I want [functionality], so that [benefit]

**Contoh:**
- As a librarian, I want to search books by title, so that I can quickly find books for students
- As a student, I want to reserve a book online, so that I can ensure the book is available when I need it

#### B. Acceptance Criteria
Setiap user story harus memiliki acceptance criteria yang jelas:
- **Given:** Kondisi awal
- **When:** Aksi yang dilakukan
- **Then:** Hasil yang diharapkan

**Contoh:**
```
Given: A student is logged in
When: They search for "Java Programming"
Then: They should see a list of books related to Java Programming
And: The results should be sorted by relevance
And: Each result should show title, author, and availability
```

### 3. Use Cases

#### A. Komponen Use Case
- **Use Case Name:** Nama yang deskriptif
- **Actor:** Siapa yang menggunakan
- **Precondition:** Kondisi awal
- **Postcondition:** Kondisi akhir
- **Main Flow:** Alur utama
- **Alternative Flows:** Alur alternatif
- **Exception Flows:** Alur pengecualian

#### B. Contoh Use Case
**Use Case:** Borrow Book
**Actor:** Student
**Precondition:** Student is logged in and book is available
**Postcondition:** Book is borrowed and due date is set

**Main Flow:**
1. Student searches for book
2. Student selects book
3. System checks availability
4. System creates borrowing record
5. System sets due date
6. System confirms borrowing

**Alternative Flows:**
- A1: Book is not available
- A2: Student has reached borrowing limit

**Exception Flows:**
- E1: Student account is blocked
- E2: System error occurs

### 4. Requirements Traceability

#### A. Traceability Matrix
| Requirement ID | Source | Component | Priority | Status | Test Case |
|----------------|--------|-----------|----------|--------|-----------|
| REQ-001 | User Story | UI | High | Approved | TC-001 |
| REQ-002 | Business Rule | Business Logic | Medium | Pending | TC-002 |

#### B. Traceability Benefits
- **Change Impact Analysis:** Dampak perubahan requirements
- **Coverage Analysis:** Cakupan testing
- **Compliance:** Memenuhi standar dan regulasi
- **Quality Assurance:** Memastikan semua requirements terpenuhi

## Latihan Praktis

### Exercise 1: SRS Creation
**Tugas:** Buat SRS untuk sistem perpustakaan digital

**Langkah:**
1. Buat struktur SRS lengkap
2. Tulis functional requirements (minimal 10)
3. Tulis non-functional requirements (minimal 5)
4. Definisikan interface requirements
5. Buat glossary dan references

### Exercise 2: User Stories
**Tugas:** Tulis user stories untuk fitur-fitur utama

**Langkah:**
1. Identifikasi user types
2. Tulis user stories untuk setiap user type
3. Buat acceptance criteria untuk setiap story
4. Prioritize user stories
5. Estimate story points

### Exercise 3: Use Cases
**Tugas:** Buat use cases untuk proses utama

**Langkah:**
1. Identifikasi actors
2. Buat use case diagram
3. Tulis detail use cases (minimal 5)
4. Definisikan flows (main, alternative, exception)
5. Buat use case documentation

### Exercise 4: Traceability Matrix
**Tugas:** Buat traceability matrix lengkap

**Langkah:**
1. Assign unique ID untuk setiap requirement
2. Link requirements dengan source
3. Map ke komponen sistem
4. Link dengan test cases
5. Buat traceability report

## Proyek Integrasi: Dokumentasi Spesifikasi

### SRS untuk Sistem Perpustakaan Digital

#### 1. Introduction
**Purpose:** Dokumen ini mendefinisikan requirements untuk Sistem Manajemen Perpustakaan Digital yang akan mengotomasi operasional perpustakaan universitas.

**Scope:** Sistem mencakup manajemen koleksi, peminjaman, pengembalian, reservasi, dan pelaporan.

#### 2. Functional Requirements

**REQ-001: User Authentication**
- System shall allow users to login with username/password
- System shall support role-based access control
- System shall maintain session timeout

**REQ-002: Book Search**
- System shall allow search by title, author, ISBN
- System shall support advanced search with filters
- System shall display search results with pagination

**REQ-003: Book Borrowing**
- System shall allow students to borrow books
- System shall check borrowing limits
- System shall set due dates automatically

**REQ-004: Book Return**
- System shall allow students to return books
- System shall calculate fines for overdue books
- System shall update book availability

**REQ-005: Book Reservation**
- System shall allow students to reserve books
- System shall notify when reserved books are available
- System shall maintain reservation queue

#### 3. Non-Functional Requirements

**REQ-NF-001: Performance**
- System shall respond within 2 seconds for 95% of requests
- System shall support 100 concurrent users
- System shall handle 10,000 books in database

**REQ-NF-002: Security**
- System shall encrypt sensitive data
- System shall implement role-based access control
- System shall maintain audit logs

**REQ-NF-003: Usability**
- System shall have intuitive user interface
- System shall be accessible via web browser
- System shall support mobile devices

#### 4. User Stories

**Epic 1: Book Management**
- As a librarian, I want to add new books to the system
- As a librarian, I want to update book information
- As a librarian, I want to remove books from the system

**Epic 2: User Management**
- As an administrator, I want to create user accounts
- As an administrator, I want to manage user roles
- As an administrator, I want to deactivate user accounts

**Epic 3: Borrowing Process**
- As a student, I want to search for books
- As a student, I want to borrow books
- As a student, I want to return books
- As a student, I want to reserve books

#### 5. Use Cases

**UC-001: Borrow Book**
- **Actor:** Student
- **Precondition:** Student is logged in, book is available
- **Main Flow:** Search → Select → Borrow → Confirm
- **Alternative:** Book not available → Reserve
- **Exception:** Account blocked → Show error

**UC-002: Return Book**
- **Actor:** Student
- **Precondition:** Student has borrowed books
- **Main Flow:** Select book → Return → Calculate fine → Confirm
- **Alternative:** No fine → Direct return
- **Exception:** Book damaged → Report damage

#### 6. Traceability Matrix

| ID | Requirement | Source | Component | Priority | Test Case |
|----|-------------|--------|-----------|----------|-----------|
| REQ-001 | User Authentication | User Story | Security | High | TC-001 |
| REQ-002 | Book Search | User Story | UI | High | TC-002 |
| REQ-003 | Book Borrowing | User Story | Business Logic | High | TC-003 |
| REQ-004 | Book Return | User Story | Business Logic | High | TC-004 |
| REQ-005 | Book Reservation | User Story | Business Logic | Medium | TC-005 |

## Deliverables Unit 6:
1. **Software Requirements Specification** - Dokumen SRS lengkap
2. **User Stories** - User stories dengan acceptance criteria
3. **Use Cases** - Use cases detail dengan flows
4. **Traceability Matrix** - Matrix traceability requirements
5. **Requirements Review** - Review dan validation requirements

## Assessment Criteria
- [ ] Mampu membuat SRS yang komprehensif
- [ ] Mampu menulis user stories yang efektif
- [ ] Mampu membuat use cases yang detail
- [ ] Mampu mendefinisikan acceptance criteria
- [ ] Mampu membuat traceability matrix

## Referensi
- [IEEE 830 - SRS Standard](https://www.ieee.org/)
- [User Story Mapping](https://www.jpattonassociates.com/user-story-mapping/)
- [Use Case Best Practices](https://www.omg.org/)
- [Requirements Traceability](https://www.ireb.org/)

---
**Previous Unit:** [Unit 5 - Negosiasi Kebutuhan](../modules/unit-05-negosiasi-kebutuhan.md)  
**Next Unit:** [Unit 7 - Software Environment](../modules/unit-07-software-environment.md)




