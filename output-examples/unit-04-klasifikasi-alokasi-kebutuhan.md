# Unit 4: Contoh Output - Klasifikasi Alokasi Kebutuhan

## 1. Klasifikasi Kebutuhan Fungsional vs Non-Fungsional

### Kebutuhan Fungsional

| ID | Kebutuhan | Stakeholder | Prioritas | Kompleksitas |
|----|-----------|-------------|-----------|--------------|
| **F-001** | Sistem harus dapat melakukan autentikasi user | IT Manager | Tinggi | Medium |
| **F-002** | Sistem harus dapat menambah, mengedit, menghapus data buku | Pustakawan | Tinggi | Medium |
| **F-003** | Sistem harus dapat melakukan pencarian buku berdasarkan judul, penulis, kategori | Semua User | Tinggi | Medium |
| **F-004** | Sistem harus dapat memproses peminjaman buku | Pustakawan, Mahasiswa | Tinggi | High |
| **F-005** | Sistem harus dapat memproses pengembalian buku | Pustakawan, Mahasiswa | Tinggi | High |
| **F-006** | Sistem harus dapat menampilkan riwayat peminjaman | Mahasiswa | Sedang | Low |
| **F-007** | Sistem harus dapat mengirim notifikasi email/SMS | Semua User | Sedang | Medium |
| **F-008** | Sistem harus dapat menghasilkan laporan statistik | Manajer Perpustakaan | Sedang | High |
| **F-009** | Sistem harus dapat mengelola user roles dan permissions | IT Manager | Sedang | Medium |
| **F-010** | Sistem harus dapat melakukan backup data otomatis | IT Manager | Rendah | Medium |

### Kebutuhan Non-Fungsional

| ID | Kategori | Kebutuhan | Stakeholder | Prioritas | Kompleksitas |
|----|----------|-----------|-------------|-----------|--------------|
| **NF-001** | Performance | Sistem harus dapat menangani 1000 user concurrent | IT Manager | Tinggi | High |
| **NF-002** | Performance | Response time < 2 detik untuk semua operasi | Semua User | Tinggi | High |
| **NF-003** | Usability | Interface harus mudah digunakan oleh pustakawan | Pustakawan | Tinggi | Medium |
| **NF-004** | Usability | Sistem harus responsive untuk mobile devices | Mahasiswa | Tinggi | Medium |
| **NF-005** | Security | Data user harus dienkripsi | IT Manager | Tinggi | High |
| **NF-006** | Security | Sistem harus memiliki audit trail | IT Manager | Sedang | Medium |
| **NF-007** | Reliability | Uptime 99.9% | IT Manager | Tinggi | High |
| **NF-008** | Scalability | Sistem harus dapat menangani pertumbuhan data 50% per tahun | IT Manager | Sedang | High |
| **NF-009** | Compatibility | Sistem harus kompatibel dengan browser modern | Semua User | Sedang | Low |
| **NF-010** | Maintainability | Kode harus terdokumentasi dengan baik | Developer | Sedang | Medium |

## 2. Klasifikasi Berdasarkan MoSCoW

### Must Have (Wajib)
- **F-001:** Autentikasi user
- **F-002:** CRUD data buku
- **F-003:** Pencarian buku
- **F-004:** Peminjaman buku
- **F-005:** Pengembalian buku
- **NF-001:** 1000 user concurrent
- **NF-002:** Response time < 2 detik
- **NF-005:** Enkripsi data user

### Should Have (Harus)
- **F-006:** Riwayat peminjaman
- **F-007:** Notifikasi email/SMS
- **F-009:** User roles dan permissions
- **NF-003:** Interface mudah digunakan
- **NF-004:** Responsive mobile
- **NF-007:** Uptime 99.9%

### Could Have (Bisa)
- **F-008:** Laporan statistik
- **F-010:** Backup otomatis
- **NF-006:** Audit trail
- **NF-008:** Scalability 50% per tahun

### Won't Have (Tidak)
- **F-011:** Integrasi dengan sistem eksternal (tahun ini)
- **F-012:** AI recommendation system
- **F-013:** Multi-language support

## 3. Alokasi Kebutuhan ke Komponen Sistem

### Komponen: User Management
| Kebutuhan | Alokasi | Justifikasi |
|-----------|---------|-------------|
| **F-001** | Autentikasi user | Login/Logout module | Core functionality |
| **F-009** | User roles dan permissions | Authorization module | Security requirement |
| **NF-005** | Enkripsi data user | Security module | Data protection |

### Komponen: Book Management
| Kebutuhan | Alokasi | Justifikasi |
|-----------|---------|-------------|
| **F-002** | CRUD data buku | Book CRUD module | Core functionality |
| **F-003** | Pencarian buku | Search module | Core functionality |
| **NF-003** | Interface mudah digunakan | UI/UX module | User experience |

### Komponen: Borrowing System
| Kebutuhan | Alokasi | Justifikasi |
|-----------|---------|-------------|
| **F-004** | Peminjaman buku | Borrowing module | Core functionality |
| **F-005** | Pengembalian buku | Return module | Core functionality |
| **F-006** | Riwayat peminjaman | History module | User convenience |

### Komponen: Notification System
| Kebutuhan | Alokasi | Justifikasi |
|-----------|---------|-------------|
| **F-007** | Notifikasi email/SMS | Notification module | User communication |
| **NF-004** | Responsive mobile | Mobile module | User experience |

### Komponen: Reporting System
| Kebutuhan | Alokasi | Justifikasi |
|-----------|---------|-------------|
| **F-008** | Laporan statistik | Report module | Management need |
| **NF-006** | Audit trail | Audit module | Compliance |

### Komponen: Infrastructure
| Kebutuhan | Alokasi | Justifikasi |
|-----------|---------|-------------|
| **NF-001** | 1000 user concurrent | Load balancer | Performance |
| **NF-002** | Response time < 2 detik | Caching module | Performance |
| **NF-007** | Uptime 99.9% | Monitoring module | Reliability |
| **F-010** | Backup otomatis | Backup module | Data protection |

## 4. Matriks Traceability

### Traceability Matrix: Kebutuhan ke Komponen

| Kebutuhan | User Mgmt | Book Mgmt | Borrowing | Notification | Reporting | Infrastructure |
|-----------|------------|-----------|-----------|--------------|-----------|----------------|
| **F-001** | ✅ | | | | | |
| **F-002** | | ✅ | | | | |
| **F-003** | | ✅ | | | | |
| **F-004** | | | ✅ | | | |
| **F-005** | | | ✅ | | | |
| **F-006** | | | ✅ | | | |
| **F-007** | | | | ✅ | | |
| **F-008** | | | | | ✅ | |
| **F-009** | ✅ | | | | | |
| **F-010** | | | | | | ✅ |
| **NF-001** | | | | | | ✅ |
| **NF-002** | | | | | | ✅ |
| **NF-003** | | ✅ | | | | |
| **NF-004** | | | | ✅ | | |
| **NF-005** | ✅ | | | | | |
| **NF-006** | | | | | ✅ | |
| **NF-007** | | | | | | ✅ |
| **NF-008** | | | | | | ✅ |

## 5. Klasifikasi Berdasarkan Dampak Bisnis

### High Business Impact
| Kebutuhan | Dampak | Justifikasi |
|-----------|--------|-------------|
| **F-001** | Tinggi | Tanpa autentikasi, sistem tidak aman |
| **F-002** | Tinggi | Core functionality untuk manajemen koleksi |
| **F-003** | Tinggi | Tanpa pencarian, sistem tidak berguna |
| **F-004** | Tinggi | Core functionality untuk peminjaman |
| **F-005** | Tinggi | Core functionality untuk pengembalian |
| **NF-001** | Tinggi | Tanpa performa, sistem tidak bisa digunakan |

### Medium Business Impact
| Kebutuhan | Dampak | Justifikasi |
|-----------|--------|-------------|
| **F-006** | Sedang | Meningkatkan user experience |
| **F-007** | Sedang | Meningkatkan komunikasi |
| **F-008** | Sedang | Membantu manajemen |
| **F-009** | Sedang | Meningkatkan keamanan |
| **NF-003** | Sedang | Meningkatkan user experience |

### Low Business Impact
| Kebutuhan | Dampak | Justifikasi |
|-----------|--------|-------------|
| **F-010** | Rendah | Nice to have, bisa manual |
| **NF-006** | Rendah | Compliance, tidak critical |
| **NF-008** | Rendah | Future scalability |

## 6. Klasifikasi Berdasarkan Risiko Teknis

### High Technical Risk
| Kebutuhan | Risiko | Mitigasi |
|-----------|--------|---------|
| **NF-001** | Tinggi | Load testing, performance optimization |
| **NF-002** | Tinggi | Caching, database optimization |
| **NF-007** | Tinggi | Redundancy, monitoring |
| **F-004** | Tinggi | Complex business logic, testing |

### Medium Technical Risk
| Kebutuhan | Risiko | Mitigasi |
|-----------|--------|---------|
| **F-005** | Sedang | Business logic testing |
| **F-008** | Sedang | Report generation optimization |
| **NF-005** | Sedang | Security testing, encryption |

### Low Technical Risk
| Kebutuhan | Risiko | Mitigasi |
|-----------|--------|---------|
| **F-001** | Rendah | Standard authentication |
| **F-002** | Rendah | Standard CRUD operations |
| **F-003** | Rendah | Standard search functionality |

## 7. Rencana Implementasi Berdasarkan Klasifikasi

### Phase 1: Core Functionality (Sprint 1-4)
**Must Have + High Business Impact + Low Technical Risk**
- F-001: Autentikasi user
- F-002: CRUD data buku
- F-003: Pencarian buku
- F-004: Peminjaman buku
- F-005: Pengembalian buku

### Phase 2: Performance & Security (Sprint 5-8)
**Must Have + High Business Impact + High Technical Risk**
- NF-001: 1000 user concurrent
- NF-002: Response time < 2 detik
- NF-005: Enkripsi data user
- NF-007: Uptime 99.9%

### Phase 3: User Experience (Sprint 9-12)
**Should Have + Medium Business Impact + Medium Technical Risk**
- F-006: Riwayat peminjaman
- F-007: Notifikasi email/SMS
- F-009: User roles dan permissions
- NF-003: Interface mudah digunakan
- NF-004: Responsive mobile

### Phase 4: Management & Compliance (Sprint 13-16)
**Could Have + Medium Business Impact + Medium Technical Risk**
- F-008: Laporan statistik
- F-010: Backup otomatis
- NF-006: Audit trail
- NF-008: Scalability 50% per tahun

---

**Status:** Completed  
**Next Step:** Begin Unit 5 - Negosiasi Kebutuhan
