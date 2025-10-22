# SOFTWARE REQUIREMENTS SPECIFICATION (SRS)
## SISTEM MANAJEMEN PERPUSTAKAAN DIGITAL

**Versi:** 1.0  
**Tanggal:** 15 Desember 2024  
**Disusun oleh:** Sistem Analis  
**Diapprove oleh:** Kepala Perpustakaan  

---

## DAFTAR ISI

1. [Introduction](#1-introduction)
2. [Overall Description](#2-overall-description)
3. [Specific Requirements](#3-specific-requirements)
4. [External Interface Requirements](#4-external-interface-requirements)
5. [Other Nonfunctional Requirements](#5-other-nonfunctional-requirements)
6. [Other Requirements](#6-other-requirements)
7. [Appendices](#7-appendices)

---

## 1. INTRODUCTION

### 1.1 Purpose
Dokumen Software Requirements Specification (SRS) ini mendefinisikan spesifikasi kebutuhan perangkat lunak untuk Sistem Manajemen Perpustakaan Digital. Dokumen ini ditujukan untuk pengembang, tester, dan stakeholder yang terlibat dalam pengembangan sistem.

### 1.2 Scope
Sistem Manajemen Perpustakaan Digital adalah aplikasi web yang dirancang untuk mengelola operasional perpustakaan modern, termasuk:
- Manajemen koleksi buku dan media digital
- Sistem peminjaman dan pengembalian
- Manajemen anggota perpustakaan
- Sistem reservasi dan antrian
- Laporan dan statistik perpustakaan
- Integrasi dengan sistem pembayaran denda

### 1.3 Definitions, Acronyms, and Abbreviations
- **SRS**: Software Requirements Specification
- **UI**: User Interface
- **API**: Application Programming Interface
- **DB**: Database
- **ISBN**: International Standard Book Number
- **RFID**: Radio Frequency Identification
- **SMS**: Short Message Service
- **Email**: Electronic Mail

### 1.4 References
- IEEE Std 830-1998, IEEE Recommended Practice for Software Requirements Specifications
- ISO/IEC 25010:2011, Systems and software Quality Requirements and Evaluation
- Peraturan Perpustakaan Nasional Republik Indonesia

### 1.5 Overview
Dokumen ini terstruktur dalam 7 bagian utama yang mencakup pengenalan sistem, deskripsi umum, kebutuhan spesifik, antarmuka eksternal, dan persyaratan non-fungsional lainnya.

---

## 2. OVERALL DESCRIPTION

### 2.1 Product Perspective
Sistem Manajemen Perpustakaan Digital adalah sistem mandiri yang beroperasi dalam lingkungan web-based dengan komponen utama:

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Web Browser   │    │   Mobile App    │    │  Admin Panel    │
│   (Anggota)     │    │   (Anggota)     │    │   (Petugas)     │
└─────────┬───────┘    └─────────┬───────┘    └─────────┬───────┘
          │                      │                      │
          └──────────────────────┼──────────────────────┘
                                 │
                    ┌─────────────┴─────────────┐
                    │     Web Application      │
                    │   (Backend Services)     │
                    └─────────────┬─────────────┘
                                  │
                    ┌─────────────┴─────────────┐
                    │       Database           │
                    │    (MySQL/PostgreSQL)    │
                    └───────────────────────────┘
```

### 2.2 Product Functions
Sistem menyediakan fungsi-fungsi utama:

**A. Manajemen Koleksi**
- Katalogisasi buku dan media
- Klasifikasi berdasarkan Dewey Decimal System
- Manajemen metadata (ISBN, pengarang, penerbit, dll)
- Upload dan manajemen file digital

**B. Manajemen Anggota**
- Registrasi anggota baru
- Verifikasi identitas
- Manajemen profil anggota
- Status keanggotaan dan hak akses

**C. Sistem Peminjaman**
- Pencarian dan reservasi buku
- Proses peminjaman dan pengembalian
- Tracking status peminjaman
- Sistem notifikasi otomatis

**D. Manajemen Denda**
- Perhitungan denda otomatis
- Sistem pembayaran online
- Laporan denda dan pembayaran

**E. Laporan dan Analitik**
- Statistik peminjaman
- Laporan koleksi
- Analisis penggunaan perpustakaan

### 2.3 User Classes and Characteristics

**A. Anggota Perpustakaan**
- Umur: 12-65 tahun
- Tingkat keahlian: Basic to Intermediate
- Akses: Web browser, mobile app
- Kebutuhan: Pencarian buku, peminjaman, tracking status

**B. Petugas Perpustakaan**
- Umur: 22-55 tahun
- Tingkat keahlian: Intermediate to Advanced
- Akses: Admin panel, web interface
- Kebutuhan: Manajemen koleksi, verifikasi peminjaman, laporan

**C. Administrator Sistem**
- Umur: 25-50 tahun
- Tingkat keahlian: Advanced
- Akses: Full system access
- Kebutuhan: Konfigurasi sistem, manajemen user, backup data

### 2.4 Operating Environment

**Server Environment:**
- Operating System: Linux Ubuntu 20.04 LTS
- Web Server: Apache 2.4 atau Nginx 1.18
- Application Server: PHP 8.1+ atau Node.js 16+
- Database: MySQL 8.0 atau PostgreSQL 13+
- Memory: Minimum 4GB RAM
- Storage: Minimum 100GB SSD

**Client Environment:**
- Web Browser: Chrome 90+, Firefox 88+, Safari 14+, Edge 90+
- Mobile: Android 8.0+, iOS 12.0+
- Screen Resolution: Minimum 1024x768
- Internet Connection: Minimum 1 Mbps

### 2.5 Design and Implementation Constraints

**A. Technical Constraints:**
- Menggunakan framework web modern (Laravel/Express.js)
- Database harus mendukung ACID transactions
- Implementasi responsive design untuk mobile
- API harus mengikuti RESTful principles

**B. Regulatory Constraints:**
- Mematuhi UU No. 43 Tahun 2007 tentang Perpustakaan
- Kepatuhan terhadap standar ISO 27001 untuk keamanan data
- Implementasi GDPR untuk perlindungan data pribadi

**C. Hardware Constraints:**
- Sistem harus dapat berjalan pada server dengan spesifikasi minimum
- Dukungan untuk scanner barcode/QR code
- Integrasi dengan printer untuk kartu anggota

### 2.6 Assumptions and Dependencies

**Assumptions:**
- Pengguna memiliki akses internet yang stabil
- Perpustakaan memiliki infrastruktur IT yang memadai
- Petugas perpustakaan terlatih dalam penggunaan sistem
- Data buku tersedia dalam format digital

**Dependencies:**
- Ketersediaan layanan email untuk notifikasi
- Integrasi dengan sistem pembayaran online
- Koneksi ke database eksternal untuk verifikasi ISBN
- Backup sistem yang teratur

---

## 3. SPECIFIC REQUIREMENTS

### 3.1 Functional Requirements

#### 3.1.1 Manajemen Koleksi

**FR-001: Katalogisasi Buku**
- **Description:** Sistem harus memungkinkan petugas untuk menambahkan buku baru ke dalam katalog
- **Input:** Data buku (judul, pengarang, ISBN, penerbit, tahun terbit, kategori)
- **Process:** Validasi data, generate ID unik, simpan ke database
- **Output:** Konfirmasi buku berhasil ditambahkan
- **Priority:** High

**FR-002: Pencarian Buku**
- **Description:** Anggota dapat mencari buku berdasarkan berbagai kriteria
- **Input:** Kata kunci pencarian (judul, pengarang, ISBN, kategori)
- **Process:** Query database, filter hasil, ranking relevansi
- **Output:** Daftar buku yang sesuai dengan kriteria
- **Priority:** High

**FR-003: Manajemen Metadata**
- **Description:** Sistem harus memungkinkan update metadata buku
- **Input:** Data metadata yang diperbarui
- **Process:** Validasi perubahan, update database, log perubahan
- **Output:** Konfirmasi metadata berhasil diperbarui
- **Priority:** Medium

#### 3.1.2 Manajemen Anggota

**FR-004: Registrasi Anggota**
- **Description:** Sistem harus memungkinkan pendaftaran anggota baru
- **Input:** Data pribadi (nama, alamat, email, telepon, foto)
- **Process:** Validasi data, generate ID anggota, simpan ke database
- **Output:** Kartu anggota digital dan konfirmasi registrasi
- **Priority:** High

**FR-005: Verifikasi Identitas**
- **Description:** Sistem harus memverifikasi identitas anggota
- **Input:** Nomor ID anggota atau email
- **Process:** Query database, validasi status keanggotaan
- **Output:** Status verifikasi dan informasi anggota
- **Priority:** High

**FR-006: Manajemen Profil**
- **Description:** Anggota dapat mengupdate profil pribadi
- **Input:** Data profil yang diperbarui
- **Process:** Validasi data, update database, notifikasi perubahan
- **Output:** Konfirmasi profil berhasil diperbarui
- **Priority:** Medium

#### 3.1.3 Sistem Peminjaman

**FR-007: Peminjaman Buku**
- **Description:** Sistem harus memproses peminjaman buku
- **Input:** ID anggota, ID buku, tanggal peminjaman
- **Process:** Validasi ketersediaan, cek limit peminjaman, update status
- **Output:** Konfirmasi peminjaman dan tanggal pengembalian
- **Priority:** High

**FR-008: Pengembalian Buku**
- **Description:** Sistem harus memproses pengembalian buku
- **Input:** ID peminjaman atau ID buku
- **Process:** Validasi peminjaman, update status, hitung denda jika ada
- **Output:** Konfirmasi pengembalian dan informasi denda
- **Priority:** High

**FR-009: Reservasi Buku**
- **Description:** Anggota dapat mereservasi buku yang sedang dipinjam
- **Input:** ID anggota, ID buku
- **Process:** Cek status buku, tambah ke antrian reservasi
- **Output:** Konfirmasi reservasi dan posisi dalam antrian
- **Priority:** Medium

**FR-010: Perpanjangan Peminjaman**
- **Description:** Anggota dapat memperpanjang masa peminjaman
- **Input:** ID peminjaman, permintaan perpanjangan
- **Process:** Validasi syarat perpanjangan, update tanggal jatuh tempo
- **Output:** Konfirmasi perpanjangan atau penolakan dengan alasan
- **Priority:** Medium

#### 3.1.4 Sistem Denda

**FR-011: Perhitungan Denda**
- **Description:** Sistem harus menghitung denda otomatis
- **Input:** Data peminjaman dan tanggal pengembalian
- **Process:** Hitung selisih hari, terapkan tarif denda
- **Output:** Jumlah denda yang harus dibayar
- **Priority:** High

**FR-012: Pembayaran Denda**
- **Description:** Sistem harus memproses pembayaran denda
- **Input:** ID anggota, jumlah pembayaran, metode pembayaran
- **Process:** Validasi pembayaran, update status denda, generate receipt
- **Output:** Konfirmasi pembayaran dan receipt digital
- **Priority:** High

#### 3.1.5 Notifikasi

**FR-013: Notifikasi Email**
- **Description:** Sistem harus mengirim notifikasi email
- **Input:** Template email, data penerima, konten pesan
- **Process:** Generate email, kirim ke SMTP server
- **Output:** Status pengiriman email
- **Priority:** Medium

**FR-014: Notifikasi SMS**
- **Description:** Sistem harus mengirim notifikasi SMS
- **Input:** Nomor telepon, pesan SMS
- **Process:** Kirim via SMS gateway
- **Output:** Status pengiriman SMS
- **Priority:** Low

#### 3.1.6 Laporan

**FR-015: Laporan Peminjaman**
- **Description:** Sistem harus menghasilkan laporan peminjaman
- **Input:** Periode laporan, filter kriteria
- **Process:** Query data, generate laporan dalam format PDF/Excel
- **Output:** File laporan yang dapat diunduh
- **Priority:** Medium

**FR-016: Laporan Statistik**
- **Description:** Sistem harus menyediakan dashboard statistik
- **Input:** Parameter statistik, periode data
- **Process:** Agregasi data, generate chart dan grafik
- **Output:** Dashboard interaktif dengan visualisasi data
- **Priority:** Medium

### 3.2 Non-Functional Requirements

#### 3.2.1 Performance Requirements

**NFR-001: Response Time**
- **Description:** Sistem harus merespons dalam waktu maksimal 3 detik
- **Measurement:** 95% dari request harus selesai dalam 3 detik
- **Priority:** High

**NFR-002: Throughput**
- **Description:** Sistem harus mendukung 100 concurrent users
- **Measurement:** Sistem tetap stabil dengan 100 user aktif bersamaan
- **Priority:** High

**NFR-003: Database Performance**
- **Description:** Query database harus selesai dalam 1 detik
- **Measurement:** 90% query database selesai dalam 1 detik
- **Priority:** Medium

#### 3.2.2 Security Requirements

**NFR-004: Authentication**
- **Description:** Semua akses harus melalui autentikasi
- **Implementation:** Login dengan username/password atau SSO
- **Priority:** High

**NFR-005: Authorization**
- **Description:** Akses berdasarkan role dan permission
- **Implementation:** Role-based access control (RBAC)
- **Priority:** High

**NFR-006: Data Encryption**
- **Description:** Data sensitif harus dienkripsi
- **Implementation:** AES-256 encryption untuk data pribadi
- **Priority:** High

**NFR-007: Session Management**
- **Description:** Session harus aman dan timeout otomatis
- **Implementation:** Session timeout 30 menit, secure cookies
- **Priority:** Medium

#### 3.2.3 Usability Requirements

**NFR-008: User Interface**
- **Description:** Interface harus user-friendly dan intuitif
- **Implementation:** Responsive design, clear navigation, help system
- **Priority:** High

**NFR-009: Accessibility**
- **Description:** Sistem harus accessible untuk penyandang disabilitas
- **Implementation:** WCAG 2.1 AA compliance, screen reader support
- **Priority:** Medium

**NFR-010: Multi-language Support**
- **Description:** Sistem harus mendukung bahasa Indonesia dan Inggris
- **Implementation:** Internationalization (i18n) framework
- **Priority:** Low

#### 3.2.4 Reliability Requirements

**NFR-011: System Availability**
- **Description:** Sistem harus available 99.5% dari waktu
- **Measurement:** Downtime maksimal 3.6 jam per bulan
- **Priority:** High

**NFR-012: Data Backup**
- **Description:** Backup data otomatis setiap hari
- **Implementation:** Daily automated backup dengan retention 30 hari
- **Priority:** High

**NFR-013: Error Handling**
- **Description:** Sistem harus menangani error dengan graceful
- **Implementation:** Comprehensive error logging dan user-friendly error messages
- **Priority:** Medium

#### 3.2.5 Scalability Requirements

**NFR-014: Horizontal Scaling**
- **Description:** Sistem harus dapat di-scale horizontal
- **Implementation:** Load balancer, stateless application design
- **Priority:** Medium

**NFR-015: Database Scaling**
- **Description:** Database harus dapat di-scale sesuai kebutuhan
- **Implementation:** Database clustering, read replicas
- **Priority:** Low

---

## 4. EXTERNAL INTERFACE REQUIREMENTS

### 4.1 User Interfaces

#### 4.1.1 Web Interface untuk Anggota
- **Layout:** Responsive design dengan sidebar navigation
- **Components:** Header dengan logo, search bar, user menu
- **Pages:** Dashboard, Katalog, Peminjaman, Profil, Riwayat
- **Features:** Advanced search, filter, sorting, pagination

#### 4.1.2 Mobile Interface
- **Platform:** Progressive Web App (PWA)
- **Features:** Offline capability, push notifications, camera integration
- **Navigation:** Bottom tab navigation dengan 5 tab utama
- **Responsive:** Optimized untuk layar 4-7 inci

#### 4.1.3 Admin Interface
- **Layout:** Dashboard dengan sidebar dan top navigation
- **Components:** Data tables, charts, forms, modal dialogs
- **Features:** Bulk operations, advanced filtering, export functionality

### 4.2 Hardware Interfaces

#### 4.2.1 Barcode Scanner
- **Type:** USB barcode scanner
- **Protocol:** HID (Human Interface Device)
- **Integration:** Direct input ke form pencarian dan peminjaman

#### 4.2.2 RFID Reader
- **Type:** USB RFID reader
- **Protocol:** Serial communication
- **Integration:** Automatic book identification untuk peminjaman

#### 4.2.3 Printer
- **Type:** Thermal printer untuk receipt dan kartu anggota
- **Protocol:** USB atau network printing
- **Integration:** Print receipt untuk peminjaman dan pembayaran

### 4.3 Software Interfaces

#### 4.3.1 Email Service
- **Provider:** SMTP server (Gmail, SendGrid, dll)
- **Protocol:** SMTP dengan authentication
- **Purpose:** Notifikasi email untuk peminjaman, pengembalian, denda

#### 4.3.2 SMS Gateway
- **Provider:** Twilio, SMS Gateway lokal
- **Protocol:** REST API
- **Purpose:** Notifikasi SMS untuk reminder dan alert

#### 4.3.3 Payment Gateway
- **Provider:** Midtrans, Doku, atau payment gateway lokal
- **Protocol:** REST API dengan webhook
- **Purpose:** Pembayaran denda online

#### 4.3.4 ISBN Database
- **Provider:** Open Library API, Google Books API
- **Protocol:** REST API
- **Purpose:** Auto-fill data buku berdasarkan ISBN

### 4.4 Communication Interfaces

#### 4.4.1 HTTP/HTTPS
- **Protocol:** HTTP/1.1 dan HTTP/2
- **Security:** TLS 1.3 untuk enkripsi
- **Purpose:** Web communication antara client dan server

#### 4.4.2 WebSocket
- **Protocol:** WebSocket dengan secure connection (WSS)
- **Purpose:** Real-time notifications dan updates

#### 4.4.3 REST API
- **Protocol:** RESTful API dengan JSON
- **Authentication:** JWT (JSON Web Token)
- **Purpose:** Mobile app integration dan third-party access

---

## 5. OTHER NONFUNCTIONAL REQUIREMENTS

### 5.1 Legal and Regulatory Requirements

**LNR-001: Data Protection**
- **Description:** Sistem harus mematuhi UU Perlindungan Data Pribadi
- **Implementation:** Privacy policy, data consent, right to be forgotten
- **Compliance:** UU No. 27 Tahun 2022 tentang Perlindungan Data Pribadi

**LNR-002: Library Standards**
- **Description:** Sistem harus mengikuti standar perpustakaan nasional
- **Implementation:** Dewey Decimal Classification, MARC format
- **Compliance:** Standar Nasional Indonesia (SNI) untuk perpustakaan

### 5.2 Internationalization Requirements

**INR-001: Multi-language Support**
- **Description:** Interface harus mendukung bahasa Indonesia dan Inggris
- **Implementation:** i18n framework dengan translation files
- **Priority:** Medium

**INR-002: Date and Time Format**
- **Description:** Format tanggal dan waktu sesuai lokal Indonesia
- **Implementation:** Timezone Asia/Jakarta, format DD/MM/YYYY
- **Priority:** High

### 5.3 Accessibility Requirements

**ACR-001: Screen Reader Support**
- **Description:** Sistem harus compatible dengan screen reader
- **Implementation:** ARIA labels, semantic HTML, keyboard navigation
- **Standard:** WCAG 2.1 AA compliance

**ACR-002: Keyboard Navigation**
- **Description:** Semua fungsi harus accessible via keyboard
- **Implementation:** Tab navigation, keyboard shortcuts
- **Priority:** Medium

### 5.4 Portability Requirements

**POR-001: Cross-browser Compatibility**
- **Description:** Sistem harus berjalan di semua browser modern
- **Implementation:** Progressive enhancement, polyfills untuk legacy browser
- **Browsers:** Chrome 90+, Firefox 88+, Safari 14+, Edge 90+

**POR-002: Mobile Responsiveness**
- **Description:** Interface harus responsive di semua ukuran layar
- **Implementation:** Mobile-first design, flexible grid system
- **Breakpoints:** 320px, 768px, 1024px, 1440px

---

## 6. OTHER REQUIREMENTS

### 6.1 Installation Requirements

**INS-001: Server Requirements**
- **Operating System:** Linux Ubuntu 20.04 LTS atau CentOS 8
- **Web Server:** Apache 2.4+ atau Nginx 1.18+
- **PHP:** Version 8.1+ dengan extensions (PDO, MySQL, GD, cURL)
- **Database:** MySQL 8.0+ atau PostgreSQL 13+
- **Memory:** Minimum 4GB RAM, recommended 8GB
- **Storage:** Minimum 100GB SSD, recommended 500GB

**INS-002: Client Requirements**
- **Browser:** Modern browser dengan JavaScript enabled
- **Screen Resolution:** Minimum 1024x768
- **Internet:** Stable internet connection minimum 1 Mbps
- **Mobile:** Android 8.0+ atau iOS 12.0+

### 6.2 Training Requirements

**TRN-001: User Training**
- **Duration:** 4 jam untuk petugas perpustakaan
- **Content:** Overview sistem, operasional harian, troubleshooting
- **Method:** Hands-on training dengan manual dan video tutorial
- **Follow-up:** Support 30 hari pertama setelah go-live

**TRN-002: Administrator Training**
- **Duration:** 8 jam untuk administrator sistem
- **Content:** Konfigurasi sistem, backup, security, maintenance
- **Method:** Intensive training dengan lab exercises
- **Certification:** Sertifikat kompetensi administrator

### 6.3 Documentation Requirements

**DOC-001: User Manual**
- **Content:** Step-by-step guide untuk semua fungsi user
- **Format:** PDF dan online help system
- **Language:** Bahasa Indonesia dengan screenshot
- **Update:** Diperbarui setiap 6 bulan

**DOC-002: Technical Documentation**
- **Content:** API documentation, database schema, deployment guide
- **Format:** Markdown dengan code examples
- **Audience:** Developer dan system administrator
- **Version Control:** Git repository dengan versioning

### 6.4 Support and Maintenance

**SUP-001: Technical Support**
- **Availability:** 24/7 untuk critical issues, 8x5 untuk general support
- **Channels:** Email, phone, ticketing system
- **Response Time:** 4 jam untuk critical, 24 jam untuk general
- **Escalation:** 3-level escalation process

**SUP-002: Maintenance Schedule**
- **Regular Updates:** Monthly security patches
- **Major Updates:** Quarterly feature releases
- **Database Maintenance:** Weekly optimization dan cleanup
- **Backup Verification:** Daily backup testing

---

## 7. APPENDICES

### Appendix A: Glossary

**Anggota Perpustakaan**
Individu yang terdaftar sebagai pengguna perpustakaan dengan hak untuk meminjam koleksi.

**Barcode**
Kode batang yang digunakan untuk identifikasi unik setiap item koleksi.

**Denda**
Biaya yang dikenakan kepada anggota karena keterlambatan pengembalian buku.

**ISBN (International Standard Book Number)**
Nomor standar internasional untuk identifikasi unik buku.

**Katalog**
Database yang berisi informasi tentang semua koleksi perpustakaan.

**Peminjaman**
Proses meminjam koleksi perpustakaan untuk jangka waktu tertentu.

**Reservasi**
Pemesan koleksi yang sedang dipinjam oleh anggota lain.

**RFID (Radio Frequency Identification)**
Teknologi identifikasi menggunakan gelombang radio.

### Appendix B: Use Case Diagrams

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Anggota       │    │  Petugas        │    │ Administrator   │
│   Perpustakaan  │    │  Perpustakaan   │    │   Sistem        │
└─────────┬───────┘    └─────────┬───────┘    └─────────┬───────┘
          │                      │                      │
          │ ┌─────────────────┐  │ ┌─────────────────┐  │ ┌─────────────────┐
          │ │   Pencarian     │  │ │  Manajemen      │  │ │  Konfigurasi    │
          │ │   Buku          │  │ │  Koleksi        │  │ │  Sistem         │
          │ └─────────────────┘  │ └─────────────────┘  │ └─────────────────┘
          │                      │                      │
          │ ┌─────────────────┐  │ ┌─────────────────┐  │ ┌─────────────────┐
          │ │   Peminjaman    │  │ │  Verifikasi     │  │ │  Manajemen      │
          │ │   Buku          │  │ │  Peminjaman      │  │ │  User           │
          │ └─────────────────┘  │ └─────────────────┘  │ └─────────────────┘
          │                      │                      │
          │ ┌─────────────────┐  │ ┌─────────────────┐  │ ┌─────────────────┐
          │ │   Reservasi     │  │ │  Laporan        │  │ │  Backup Data    │
          │ │   Buku          │  │ │  Statistik      │  │ │  & Recovery     │
          │ └─────────────────┘  │ └─────────────────┘  │ └─────────────────┘
```

### Appendix C: Data Flow Diagrams

**Level 0 - Context Diagram:**
```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Anggota       │    │  Petugas        │    │  Administrator  │
│   Perpustakaan  │    │  Perpustakaan   │    │   Sistem        │
└─────────┬───────┘    └─────────┬───────┘    └─────────┬───────┘
          │                      │                      │
          │ Request/Response     │ Request/Response     │ Request/Response
          │                      │                      │
          └──────────────────────┼──────────────────────┘
                                 │
                    ┌─────────────┴─────────────┐
                    │   Sistem Manajemen        │
                    │   Perpustakaan Digital    │
                    └─────────────┬─────────────┘
                                  │
                    ┌─────────────┴─────────────┐
                    │       Database            │
                    │    (MySQL/PostgreSQL)     │
                    └───────────────────────────┘
```

### Appendix D: Entity Relationship Diagram

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│     Anggota     │    │      Buku       │    │   Peminjaman    │
│                 │    │                 │    │                 │
│ - id_anggota    │    │ - id_buku       │    │ - id_peminjaman │
│ - nama          │    │ - judul         │    │ - id_anggota    │
│ - email         │    │ - pengarang     │    │ - id_buku       │
│ - telepon        │    │ - ISBN          │    │ - tgl_pinjam    │
│ - alamat         │    │ - penerbit      │    │ - tgl_kembali   │
│ - status         │    │ - kategori      │    │ - status        │
│ - tgl_daftar     │    │ - status        │    │ - denda         │
└─────────┬───────┘    └─────────┬───────┘    └─────────┬───────┘
          │                      │                      │
          │ 1                    │ 1                    │ M
          │                      │                      │
          └──────────────────────┼──────────────────────┘
                                 │
                    ┌─────────────┴─────────────┐
                    │        Denda              │
                    │                           │
                    │ - id_denda                │
                    │ - id_peminjaman           │
                    │ - jumlah_denda            │
                    │ - tgl_bayar              │
                    │ - status_bayar           │
                    └───────────────────────────┘
```

### Appendix E: Screen Mockups

**Dashboard Anggota:**
```
┌─────────────────────────────────────────────────────────┐
│  [Logo]  Sistem Perpustakaan Digital    [User] [Logout]  │
├─────────────────────────────────────────────────────────┤
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐      │
│  │ Pencarian   │  │ Peminjaman  │  │ Riwayat     │      │
│  │ Buku        │  │ Aktif       │  │ Peminjaman  │      │
│  └─────────────┘  └─────────────┘  └─────────────┘      │
│                                                         │
│  ┌─────────────────────────────────────────────────────┐ │
│  │              Koleksi Terbaru                       │ │
│  │  [Buku 1]  [Buku 2]  [Buku 3]  [Buku 4]          │ │
│  └─────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────┘
```

**Form Peminjaman:**
```
┌─────────────────────────────────────────────────────────┐
│                    Form Peminjaman                     │
├─────────────────────────────────────────────────────────┤
│  ID Anggota: [________________] [Cari]                 │
│  Nama: [________________________]                       │
│                                                         │
│  ┌─────────────────────────────────────────────────────┐ │
│  │                Daftar Buku                          │ │
│  │  [✓] Buku 1 - Pengarang 1                          │ │
│  │  [✓] Buku 2 - Pengarang 2                          │ │
│  │  [ ] Buku 3 - Pengarang 3                          │ │
│  └─────────────────────────────────────────────────────┘ │
│                                                         │
│  [Simpan Peminjaman]  [Batal]                          │
└─────────────────────────────────────────────────────────┘
```

### Appendix F: API Documentation

**Endpoint: GET /api/books**
- **Description:** Mendapatkan daftar buku
- **Parameters:** 
  - `search` (optional): Kata kunci pencarian
  - `category` (optional): Kategori buku
  - `page` (optional): Nomor halaman
  - `limit` (optional): Jumlah item per halaman
- **Response:**
```json
{
  "status": "success",
  "data": {
    "books": [
      {
        "id": 1,
        "title": "Judul Buku",
        "author": "Nama Pengarang",
        "isbn": "978-1234567890",
        "status": "available"
      }
    ],
    "pagination": {
      "current_page": 1,
      "total_pages": 10,
      "total_items": 100
    }
  }
}
```

**Endpoint: POST /api/loans**
- **Description:** Membuat peminjaman baru
- **Request Body:**
```json
{
  "member_id": 123,
  "book_ids": [1, 2, 3],
  "loan_date": "2024-12-15"
}
```
- **Response:**
```json
{
  "status": "success",
  "data": {
    "loan_id": 456,
    "due_date": "2024-12-29",
    "books": [
      {
        "book_id": 1,
        "title": "Judul Buku 1"
      }
    ]
  }
}
```

---

**Dokumen ini telah disusun sesuai dengan standar IEEE 830-1998 dan siap untuk digunakan dalam proses pengembangan sistem perpustakaan digital.**

**Tanggal Penyelesaian:** 15 Desember 2024  
**Penyusun:** Sistem Analis  
**Reviewer:** Kepala Perpustakaan  
**Approval:** Direktur Perpustakaan
