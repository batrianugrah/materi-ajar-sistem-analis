# Unit 8: Contoh Output - Spesifikasi Kebutuhan

## 1. Functional Requirements Specification

### 1.1 User Management Module

#### FR-001: User Registration
**Requirement ID:** FR-001  
**Title:** User Registration  
**Priority:** High  
**Category:** Functional  
**Stakeholder:** All Users

**Description:**
Sistem harus dapat melakukan registrasi user baru dengan informasi yang lengkap dan valid.

**Input:**
- Nama lengkap (string, 2-100 karakter)
- Email (string, format email valid)
- Password (string, minimal 8 karakter)
- Role (enum: student, librarian, manager, admin)
- Phone number (string, format Indonesia)

**Output:**
- User account created successfully
- Confirmation email sent
- User ID generated

**Business Rules:**
- Email harus unique
- Password harus mengandung minimal 1 huruf besar, 1 huruf kecil, 1 angka
- Role default adalah 'student'
- User harus verifikasi email sebelum dapat login

**Acceptance Criteria:**
- [ ] User dapat registrasi dengan data valid
- [ ] Sistem menolak email yang sudah terdaftar
- [ ] Password validation berfungsi dengan benar
- [ ] Confirmation email terkirim
- [ ] User dapat login setelah verifikasi email

**Test Cases:**
- TC-001: Registrasi dengan data valid
- TC-002: Registrasi dengan email duplikat
- TC-003: Registrasi dengan password tidak memenuhi kriteria
- TC-004: Registrasi dengan format email tidak valid

#### FR-002: User Authentication
**Requirement ID:** FR-002  
**Title:** User Authentication  
**Priority:** High  
**Category:** Functional  
**Stakeholder:** All Users

**Description:**
Sistem harus dapat melakukan autentikasi user dengan email dan password.

**Input:**
- Email (string)
- Password (string)

**Output:**
- JWT token (string)
- User session created
- User profile information

**Business Rules:**
- User harus terdaftar dan terverifikasi
- Password harus sesuai dengan yang terdaftar
- Session expire setelah 8 jam inaktivitas
- Maximum 3 login attempts, account locked setelah 3 failed attempts

**Acceptance Criteria:**
- [ ] User dapat login dengan kredensial valid
- [ ] Sistem menolak kredensial invalid
- [ ] JWT token generated dengan benar
- [ ] Session management berfungsi
- [ ] Account lockout berfungsi setelah 3 failed attempts

**Test Cases:**
- TC-005: Login dengan kredensial valid
- TC-006: Login dengan password salah
- TC-007: Login dengan email tidak terdaftar
- TC-008: Login dengan account locked
- TC-009: Session timeout setelah 8 jam

### 1.2 Book Management Module

#### FR-003: Add New Book
**Requirement ID:** FR-003  
**Title:** Add New Book  
**Priority:** High  
**Category:** Functional  
**Stakeholder:** Librarian

**Description:**
Pustakawan harus dapat menambah buku baru ke dalam katalog perpustakaan.

**Input:**
- Title (string, 1-200 karakter)
- Author (string, 1-100 karakter)
- ISBN (string, 10 atau 13 digit)
- Publisher (string, 1-100 karakter)
- Publication year (integer, 1900-2024)
- Category (enum: Fiction, Non-Fiction, Academic, Reference)
- Description (text, maksimal 1000 karakter)
- Cover image (file, maksimal 5MB)

**Output:**
- Book added to catalog
- Book ID generated
- Success message displayed

**Business Rules:**
- ISBN harus unique
- Publication year tidak boleh lebih dari tahun sekarang
- Cover image harus format JPG, PNG, atau GIF
- Hanya pustakawan yang dapat menambah buku

**Acceptance Criteria:**
- [ ] Pustakawan dapat menambah buku dengan data lengkap
- [ ] Sistem menolak ISBN duplikat
- [ ] Cover image upload berfungsi
- [ ] Book ID generated otomatis
- [ ] Buku tersedia untuk dipinjam setelah ditambah

**Test Cases:**
- TC-010: Tambah buku dengan data valid
- TC-011: Tambah buku dengan ISBN duplikat
- TC-012: Tambah buku dengan cover image terlalu besar
- TC-013: Tambah buku dengan publication year invalid

#### FR-004: Search Books
**Requirement ID:** FR-004  
**Title:** Search Books  
**Priority:** High  
**Category:** Functional  
**Stakeholder:** All Users

**Description:**
User harus dapat mencari buku berdasarkan berbagai kriteria pencarian.

**Input:**
- Search query (string, 1-100 karakter)
- Search type (enum: title, author, ISBN, category, all)
- Filters (category, publication year, availability status)
- Sort order (enum: title, author, publication year, relevance)
- Page number (integer, default 1)
- Page size (integer, default 20, maksimal 100)

**Output:**
- List of matching books
- Total count of results
- Pagination information

**Business Rules:**
- Search query minimal 2 karakter
- Results diurutkan berdasarkan relevance score
- Pagination maksimal 100 items per page
- Search case-insensitive

**Acceptance Criteria:**
- [ ] User dapat mencari buku berdasarkan title
- [ ] User dapat mencari buku berdasarkan author
- [ ] User dapat mencari buku berdasarkan ISBN
- [ ] Filter dan sort berfungsi dengan benar
- [ ] Pagination berfungsi dengan benar
- [ ] Search results relevan dan akurat

**Test Cases:**
- TC-014: Search dengan query valid
- TC-015: Search dengan query terlalu pendek
- TC-016: Search dengan filter category
- TC-017: Search dengan sort order
- TC-018: Search dengan pagination

### 1.3 Borrowing System Module

#### FR-005: Borrow Book
**Requirement ID:** FR-005  
**Title:** Borrow Book  
**Priority:** High  
**Category:** Functional  
**Stakeholder:** Student, Librarian

**Description:**
Mahasiswa harus dapat meminjam buku yang tersedia di perpustakaan.

**Input:**
- Book ID (integer)
- User ID (integer)
- Borrowing date (date, default today)
- Expected return date (date, calculated automatically)

**Output:**
- Borrowing transaction created
- Book status changed to 'borrowed'
- Confirmation message
- Email notification sent

**Business Rules:**
- User harus memiliki status 'active'
- User tidak boleh memiliki denda yang belum dibayar
- User tidak boleh meminjam lebih dari 5 buku bersamaan
- Durasi peminjaman adalah 14 hari
- Buku harus dalam status 'available'

**Acceptance Criteria:**
- [ ] Mahasiswa dapat meminjam buku yang tersedia
- [ ] Sistem menolak peminjaman jika user tidak eligible
- [ ] Book status berubah menjadi 'borrowed'
- [ ] Email notification terkirim
- [ ] Return date calculated otomatis

**Test Cases:**
- TC-019: Pinjam buku dengan user eligible
- TC-020: Pinjam buku dengan user memiliki denda
- TC-021: Pinjam buku dengan user sudah meminjam 5 buku
- TC-022: Pinjam buku yang tidak tersedia

#### FR-006: Return Book
**Requirement ID:** FR-006  
**Title:** Return Book  
**Priority:** High  
**Category:** Functional  
**Stakeholder:** Student, Librarian

**Description:**
Mahasiswa harus dapat mengembalikan buku yang dipinjam.

**Input:**
- Book ID (integer)
- User ID (integer)
- Return date (date, default today)
- Condition (enum: good, damaged, lost)

**Output:**
- Return transaction created
- Book status changed to 'available'
- Fine calculation (if applicable)
- Confirmation message

**Business Rules:**
- User harus memiliki buku yang dipinjam
- Fine dihitung jika terlambat (Rp 1.000 per hari)
- Buku yang hilang harus diganti dengan buku yang sama
- Buku yang rusak harus diperbaiki atau diganti

**Acceptance Criteria:**
- [ ] Mahasiswa dapat mengembalikan buku
- [ ] Book status berubah menjadi 'available'
- [ ] Fine calculation berfungsi dengan benar
- [ ] Confirmation message ditampilkan
- [ ] User dapat meminjam buku lain setelah return

**Test Cases:**
- TC-023: Return buku tepat waktu
- TC-024: Return buku terlambat
- TC-025: Return buku dalam kondisi rusak
- TC-026: Return buku yang hilang

## 2. Non-Functional Requirements Specification

### 2.1 Performance Requirements

#### NFR-001: Response Time
**Requirement ID:** NFR-001  
**Title:** Response Time  
**Priority:** High  
**Category:** Non-Functional  
**Stakeholder:** All Users

**Description:**
Sistem harus merespons dalam waktu maksimal 2 detik untuk 95% dari semua requests.

**Measurement:**
- Average response time: < 1.5 detik
- 95th percentile response time: < 2 detik
- 99th percentile response time: < 3 detik

**Test Scenarios:**
- Search operation dengan 1000+ books
- Login operation dengan 100+ concurrent users
- Book borrowing dengan 50+ concurrent transactions

**Acceptance Criteria:**
- [ ] Search response time < 2 detik
- [ ] Login response time < 1 detik
- [ ] Database query response time < 1 detik
- [ ] API response time < 2 detik

#### NFR-002: Throughput
**Requirement ID:** NFR-002  
**Title:** Throughput  
**Priority:** High  
**Category:** Non-Functional  
**Stakeholder:** All Users

**Description:**
Sistem harus dapat menangani 1000 user concurrent dengan performa yang stabil.

**Measurement:**
- Concurrent users: 1000
- Requests per second: 500
- Database connections: 100
- Memory usage: < 80% of available RAM

**Test Scenarios:**
- Load testing dengan 1000 concurrent users
- Stress testing dengan 1500 concurrent users
- Endurance testing selama 24 jam

**Acceptance Criteria:**
- [ ] Sistem stabil dengan 1000 concurrent users
- [ ] Response time tetap < 2 detik
- [ ] No memory leaks atau crashes
- [ ] Database performance tetap optimal

### 2.2 Security Requirements

#### NFR-003: Data Encryption
**Requirement ID:** NFR-003  
**Title:** Data Encryption  
**Priority:** High  
**Category:** Non-Functional  
**Stakeholder:** IT Manager

**Description:**
Semua data sensitif harus dienkripsi baik saat disimpan maupun saat ditransmisikan.

**Implementation:**
- Password hashing: bcrypt with salt
- Data encryption: AES-256
- Transport encryption: TLS 1.3
- Database encryption: Transparent Data Encryption (TDE)

**Acceptance Criteria:**
- [ ] Password di-hash dengan bcrypt
- [ ] Data sensitif dienkripsi di database
- [ ] HTTPS digunakan untuk semua komunikasi
- [ ] Database connection dienkripsi

#### NFR-004: Authentication Security
**Requirement ID:** NFR-004  
**Title:** Authentication Security  
**Priority:** High  
**Category:** Non-Functional  
**Stakeholder:** IT Manager

**Description:**
Sistem harus memiliki mekanisme autentikasi yang aman dan dapat diandalkan.

**Implementation:**
- JWT tokens dengan expiration
- Session management yang aman
- Rate limiting untuk login attempts
- Account lockout setelah failed attempts

**Acceptance Criteria:**
- [ ] JWT tokens expire setelah 8 jam
- [ ] Session management aman
- [ ] Rate limiting berfungsi
- [ ] Account lockout berfungsi

### 2.3 Usability Requirements

#### NFR-005: User Interface
**Requirement ID:** NFR-005  
**Title:** User Interface  
**Priority:** High  
**Category:** Non-Functional  
**Stakeholder:** All Users

**Description:**
Interface harus mudah digunakan oleh semua user dengan berbagai tingkat keahlian.

**Measurement:**
- Usability testing score: > 80%
- Task completion rate: > 90%
- User satisfaction score: > 4.0/5.0
- Learning curve: < 30 menit untuk basic operations

**Acceptance Criteria:**
- [ ] Interface intuitif dan mudah dipahami
- [ ] Navigation jelas dan konsisten
- [ ] Error messages jelas dan helpful
- [ ] Responsive design untuk mobile

#### NFR-006: Accessibility
**Requirement ID:** NFR-006  
**Title:** Accessibility  
**Priority:** Medium  
**Category:** Non-Functional  
**Stakeholder:** All Users

**Description:**
Sistem harus accessible untuk users dengan disabilities sesuai dengan WCAG 2.1 AA standards.

**Implementation:**
- Keyboard navigation support
- Screen reader compatibility
- High contrast mode
- Text size adjustment

**Acceptance Criteria:**
- [ ] Keyboard navigation berfungsi
- [ ] Screen reader compatible
- [ ] High contrast mode tersedia
- [ ] Text size dapat disesuaikan

### 2.4 Reliability Requirements

#### NFR-007: System Availability
**Requirement ID:** NFR-007  
**Title:** System Availability  
**Priority:** High  
**Category:** Non-Functional  
**Stakeholder:** All Users

**Description:**
Sistem harus available 99.9% of the time dengan planned maintenance windows.

**Measurement:**
- Uptime: 99.9%
- Downtime: < 8.76 jam per tahun
- Planned maintenance: < 4 jam per bulan
- Recovery time: < 1 jam

**Acceptance Criteria:**
- [ ] System uptime > 99.9%
- [ ] Planned maintenance < 4 jam per bulan
- [ ] Recovery time < 1 jam
- [ ] Monitoring dan alerting berfungsi

#### NFR-008: Data Backup
**Requirement ID:** NFR-008  
**Title:** Data Backup  
**Priority:** High  
**Category:** Non-Functional  
**Stakeholder:** IT Manager

**Description:**
Data harus di-backup secara otomatis setiap hari dengan retention policy yang jelas.

**Implementation:**
- Daily automated backup
- Incremental backup setiap 6 jam
- Backup encryption
- Off-site backup storage

**Acceptance Criteria:**
- [ ] Daily backup otomatis
- [ ] Backup encryption berfungsi
- [ ] Recovery testing berhasil
- [ ] Off-site backup tersedia

## 3. Business Rules Specification

### BR-001: User Eligibility
**Rule ID:** BR-001  
**Title:** User Eligibility  
**Priority:** High  
**Category:** Business Rule  
**Stakeholder:** All Users

**Description:**
User harus memenuhi kriteria tertentu untuk dapat menggunakan sistem.

**Rules:**
- User harus terdaftar dan terverifikasi
- User tidak boleh memiliki status 'suspended'
- User tidak boleh memiliki denda yang belum dibayar
- User harus memiliki role yang sesuai

**Implementation:**
- User validation sebelum setiap operasi
- Status check untuk setiap transaction
- Role-based access control

### BR-002: Borrowing Limits
**Rule ID:** BR-002  
**Title:** Borrowing Limits  
**Priority:** High  
**Category:** Business Rule  
**Stakeholder:** Students

**Description:**
Mahasiswa memiliki batasan dalam meminjam buku.

**Rules:**
- Maksimal 5 buku bersamaan
- Durasi peminjaman 14 hari
- Tidak dapat meminjam buku yang sama 2 kali berturut-turut
- Buku yang terlambat tidak dapat diperpanjang

**Implementation:**
- Borrowing limit check
- Due date calculation
- Extension restriction
- Automatic fine calculation

### BR-003: Fine Calculation
**Rule ID:** BR-003  
**Title:** Fine Calculation  
**Priority:** High  
**Category:** Business Rule  
**Stakeholder:** Students

**Description:**
Denda dihitung berdasarkan keterlambatan pengembalian buku.

**Rules:**
- Denda Rp 1.000 per hari keterlambatan
- Maksimal denda Rp 50.000 per buku
- Denda dihitung otomatis setiap hari
- User dengan denda tidak dapat meminjam buku baru

**Implementation:**
- Daily fine calculation
- Fine accumulation
- Borrowing restriction
- Payment processing

## 4. Data Requirements Specification

### 4.1 User Data
**Table:** users  
**Purpose:** Menyimpan informasi user

| Field | Type | Constraints | Description |
|-------|------|-------------|-------------|
| id | SERIAL | PRIMARY KEY | User ID |
| name | VARCHAR(100) | NOT NULL | Nama lengkap |
| email | VARCHAR(100) | UNIQUE, NOT NULL | Email address |
| password | VARCHAR(255) | NOT NULL | Hashed password |
| role | VARCHAR(20) | NOT NULL | User role |
| phone | VARCHAR(20) | NULL | Phone number |
| status | VARCHAR(20) | DEFAULT 'active' | User status |
| created_at | TIMESTAMP | DEFAULT NOW() | Creation timestamp |
| updated_at | TIMESTAMP | DEFAULT NOW() | Update timestamp |

### 4.2 Book Data
**Table:** books  
**Purpose:** Menyimpan informasi buku

| Field | Type | Constraints | Description |
|-------|------|-------------|-------------|
| id | SERIAL | PRIMARY KEY | Book ID |
| title | VARCHAR(200) | NOT NULL | Book title |
| author | VARCHAR(100) | NOT NULL | Book author |
| isbn | VARCHAR(20) | UNIQUE | ISBN number |
| publisher | VARCHAR(100) | NULL | Publisher |
| publication_year | INTEGER | NULL | Publication year |
| category | VARCHAR(50) | NULL | Book category |
| description | TEXT | NULL | Book description |
| cover_image | VARCHAR(255) | NULL | Cover image path |
| status | VARCHAR(20) | DEFAULT 'available' | Book status |
| created_at | TIMESTAMP | DEFAULT NOW() | Creation timestamp |
| updated_at | TIMESTAMP | DEFAULT NOW() | Update timestamp |

### 4.3 Transaction Data
**Table:** transactions  
**Purpose:** Menyimpan informasi transaksi peminjaman

| Field | Type | Constraints | Description |
|-------|------|-------------|-------------|
| id | SERIAL | PRIMARY KEY | Transaction ID |
| user_id | INTEGER | FOREIGN KEY | User ID |
| book_id | INTEGER | FOREIGN KEY | Book ID |
| type | VARCHAR(20) | NOT NULL | Transaction type |
| borrow_date | DATE | NULL | Borrow date |
| due_date | DATE | NULL | Due date |
| return_date | DATE | NULL | Return date |
| fine_amount | DECIMAL(10,2) | DEFAULT 0 | Fine amount |
| status | VARCHAR(20) | DEFAULT 'active' | Transaction status |
| created_at | TIMESTAMP | DEFAULT NOW() | Creation timestamp |
| updated_at | TIMESTAMP | DEFAULT NOW() | Update timestamp |

---

**Status:** Completed  
**Next Step:** Begin Unit 9 - Review Kebutuhan
