# Unit 6: Contoh Output - Dokumentasi Spesifikasi

## 1. Software Requirements Specification (SRS)

### Document Information
**Document Title:** Software Requirements Specification - Sistem Manajemen Perpustakaan Digital  
**Version:** 1.0  
**Date:** 1 Maret 2024  
**Prepared by:** Business Analyst Team  
**Approved by:** Project Manager  
**Distribution:** All Stakeholders

### Table of Contents
1. Introduction
2. Overall Description
3. Specific Requirements
4. Appendices

---

## 1. Introduction

### 1.1 Purpose
Dokumen ini menjelaskan spesifikasi kebutuhan untuk Sistem Manajemen Perpustakaan Digital yang akan dikembangkan untuk Universitas XYZ.

### 1.2 Scope
Sistem ini akan menggantikan sistem perpustakaan manual dengan sistem digital yang modern, user-friendly, dan scalable.

### 1.3 Definitions, Acronyms, and Abbreviations
- **SRS:** Software Requirements Specification
- **UI:** User Interface
- **UX:** User Experience
- **API:** Application Programming Interface
- **CRUD:** Create, Read, Update, Delete
- **MVP:** Minimum Viable Product

### 1.4 References
- IEEE Std 830-1998: IEEE Recommended Practice for Software Requirements Specifications
- ISO/IEC 25010:2011: Systems and software Quality Requirements and Evaluation
- Perpustakaan Nasional Indonesia: Standar Perpustakaan Digital

### 1.5 Overview
Dokumen ini terstruktur dengan bagian Introduction, Overall Description, dan Specific Requirements.

---

## 2. Overall Description

### 2.1 Product Perspective
Sistem ini merupakan aplikasi web-based yang terintegrasi dengan:
- Database PostgreSQL
- Email service untuk notifikasi
- SMS service untuk notifikasi
- File storage untuk cover buku
- External APIs untuk ISBN lookup

### 2.2 Product Functions
- User management dan authentication
- Book catalog management
- Search dan discovery
- Borrowing dan returning system
- Reporting dan analytics
- Notification system

### 2.3 User Classes and Characteristics
- **Pustakawan:** Staff perpustakaan yang mengelola koleksi
- **Mahasiswa:** End users yang meminjam buku
- **Dosen:** Academic staff yang menggunakan perpustakaan
- **Manajer Perpustakaan:** Management yang membutuhkan laporan
- **IT Administrator:** Technical staff yang mengelola sistem

### 2.4 Operating Environment
- **Server:** Linux Ubuntu 20.04 LTS
- **Database:** PostgreSQL 13+
- **Web Server:** Nginx 1.18+
- **Application Server:** Node.js 16+
- **Browser Support:** Chrome 90+, Firefox 88+, Safari 14+, Edge 90+

### 2.5 Design and Implementation Constraints
- Budget: Rp 500.000.000
- Timeline: 6 bulan
- Team size: 5 orang
- Technology stack: React.js, Node.js, PostgreSQL

### 2.6 Assumptions and Dependencies
- Internet connectivity tersedia
- User memiliki basic computer literacy
- Database server memiliki kapasitas yang memadai
- Third-party services (email, SMS) tersedia

---

## 3. Specific Requirements

### 3.1 Functional Requirements

#### 3.1.1 User Management
**FR-001: User Registration**
- **Description:** Sistem harus dapat melakukan registrasi user baru
- **Input:** Nama, email, password, role
- **Output:** User account created
- **Precondition:** User belum terdaftar
- **Postcondition:** User dapat login ke sistem

**FR-002: User Authentication**
- **Description:** Sistem harus dapat melakukan autentikasi user
- **Input:** Email dan password
- **Output:** Access token dan user session
- **Precondition:** User terdaftar di sistem
- **Postcondition:** User dapat mengakses fitur sesuai role

**FR-003: User Profile Management**
- **Description:** User harus dapat mengedit profil mereka
- **Input:** Updated profile information
- **Output:** Profile updated
- **Precondition:** User sudah login
- **Postcondition:** Profile information tersimpan

#### 3.1.2 Book Management
**FR-004: Add New Book**
- **Description:** Pustakawan harus dapat menambah buku baru
- **Input:** Book information (title, author, ISBN, etc.)
- **Output:** Book added to catalog
- **Precondition:** User memiliki role pustakawan
- **Postcondition:** Book tersedia untuk dipinjam

**FR-005: Edit Book Information**
- **Description:** Pustakawan harus dapat mengedit informasi buku
- **Input:** Updated book information
- **Output:** Book information updated
- **Precondition:** Book exists in catalog
- **Postcondition:** Updated information tersimpan

**FR-006: Delete Book**
- **Description:** Pustakawan harus dapat menghapus buku dari katalog
- **Input:** Book ID
- **Output:** Book removed from catalog
- **Precondition:** Book exists dan tidak sedang dipinjam
- **Postcondition:** Book tidak lagi tersedia

#### 3.1.3 Search and Discovery
**FR-007: Search Books**
- **Description:** User harus dapat mencari buku berdasarkan berbagai kriteria
- **Input:** Search query (title, author, category, ISBN)
- **Output:** List of matching books
- **Precondition:** User sudah login
- **Postcondition:** Search results ditampilkan

**FR-008: Advanced Search**
- **Description:** User harus dapat melakukan pencarian lanjutan
- **Input:** Multiple search criteria
- **Output:** Filtered search results
- **Precondition:** User sudah login
- **Postcondition:** Advanced search results ditampilkan

#### 3.1.4 Borrowing System
**FR-009: Borrow Book**
- **Description:** Mahasiswa harus dapat meminjam buku
- **Input:** Book ID, User ID
- **Output:** Borrowing transaction created
- **Precondition:** Book available, user eligible
- **Postcondition:** Book status changed to borrowed

**FR-010: Return Book**
- **Description:** Mahasiswa harus dapat mengembalikan buku
- **Input:** Book ID, User ID
- **Output:** Return transaction created
- **Precondition:** Book currently borrowed by user
- **Postcondition:** Book status changed to available

**FR-011: View Borrowing History**
- **Description:** User harus dapat melihat riwayat peminjaman
- **Input:** User ID
- **Output:** List of borrowing history
- **Precondition:** User sudah login
- **Postcondition:** History ditampilkan

#### 3.1.5 Reporting System
**FR-012: Generate Statistics Report**
- **Description:** Manajer harus dapat menghasilkan laporan statistik
- **Input:** Date range, report type
- **Output:** Statistical report
- **Precondition:** User memiliki role manajer
- **Postcondition:** Report generated dan dapat di-download

### 3.2 Non-Functional Requirements

#### 3.2.1 Performance Requirements
**NFR-001: Response Time**
- **Description:** Sistem harus merespons dalam waktu maksimal 2 detik
- **Measurement:** 95% of requests
- **Priority:** High

**NFR-002: Throughput**
- **Description:** Sistem harus dapat menangani 1000 user concurrent
- **Measurement:** Peak usage hours
- **Priority:** High

**NFR-003: Database Performance**
- **Description:** Database queries harus selesai dalam waktu maksimal 1 detik
- **Measurement:** 90% of queries
- **Priority:** Medium

#### 3.2.2 Security Requirements
**NFR-004: Data Encryption**
- **Description:** Semua data sensitif harus dienkripsi
- **Implementation:** AES-256 encryption
- **Priority:** High

**NFR-005: Authentication Security**
- **Description:** Password harus di-hash dengan salt
- **Implementation:** bcrypt with salt
- **Priority:** High

**NFR-006: Session Management**
- **Description:** Session harus expire setelah 8 jam inaktivitas
- **Implementation:** JWT tokens with expiration
- **Priority:** Medium

#### 3.2.3 Usability Requirements
**NFR-007: User Interface**
- **Description:** Interface harus mudah digunakan oleh pustakawan
- **Measurement:** Usability testing score > 80%
- **Priority:** High

**NFR-008: Mobile Responsiveness**
- **Description:** Sistem harus responsive di mobile devices
- **Implementation:** Responsive design
- **Priority:** High

**NFR-009: Accessibility**
- **Description:** Sistem harus accessible untuk users dengan disabilities
- **Implementation:** WCAG 2.1 AA compliance
- **Priority:** Medium

#### 3.2.4 Reliability Requirements
**NFR-010: System Availability**
- **Description:** Sistem harus available 99.9% of the time
- **Measurement:** Monthly uptime
- **Priority:** High

**NFR-011: Data Backup**
- **Description:** Data harus di-backup setiap hari
- **Implementation:** Automated daily backup
- **Priority:** High

**NFR-012: Error Handling**
- **Description:** Sistem harus menangani error dengan graceful
- **Implementation:** Try-catch blocks, error logging
- **Priority:** Medium

### 3.3 Business Rules
**BR-001:** Mahasiswa dapat meminjam maksimal 5 buku
**BR-002:** Durasi peminjaman adalah 14 hari
**BR-003:** Denda keterlambatan adalah Rp 1.000 per hari
**BR-004:** Buku yang terlambat tidak dapat diperpanjang
**BR-005:** User yang memiliki denda tidak dapat meminjam buku baru

### 3.4 Data Requirements
**DR-001:** User data harus mencakup nama, email, role, dan status
**DR-002:** Book data harus mencakup title, author, ISBN, category, dan status
**DR-003:** Transaction data harus mencakup user ID, book ID, tanggal, dan status
**DR-004:** Semua data harus memiliki timestamp untuk audit trail

---

## 4. Appendices

### Appendix A: Glossary
- **Borrowing:** Proses meminjam buku dari perpustakaan
- **Returning:** Proses mengembalikan buku ke perpustakaan
- **Overdue:** Buku yang terlambat dikembalikan
- **Fine:** Denda yang dikenakan untuk keterlambatan
- **Reservation:** Pemesanan buku yang sedang dipinjam

### Appendix B: Use Cases
**UC-001: Borrow Book**
1. User login ke sistem
2. User mencari buku yang diinginkan
3. User memilih buku yang tersedia
4. User klik tombol "Borrow"
5. Sistem memvalidasi eligibility user
6. Sistem membuat borrowing transaction
7. Sistem mengirim konfirmasi

**UC-002: Return Book**
1. User login ke sistem
2. User melihat daftar buku yang dipinjam
3. User memilih buku yang akan dikembalikan
4. User klik tombol "Return"
5. Sistem memvalidasi return
6. Sistem membuat return transaction
7. Sistem mengirim konfirmasi

### Appendix C: User Stories
**US-001:** Sebagai mahasiswa, saya ingin dapat mencari buku berdasarkan judul agar dapat menemukan buku yang saya butuhkan
**US-002:** Sebagai pustakawan, saya ingin dapat menambah buku baru agar koleksi perpustakaan bertambah
**US-003:** Sebagai manajer perpustakaan, saya ingin dapat melihat laporan statistik agar dapat monitoring penggunaan perpustakaan

---

**Document Status:** Approved  
**Next Review Date:** 1 April 2024  
**Next Step:** Begin Unit 7 - Software Environment
