# Unit 1: Contoh Output - Metodologi Pengembangan

## 1. Dokumen Pemilihan Metodologi

### Analisis Pemilihan Metodologi untuk Sistem Perpustakaan Digital

**Tanggal:** 15 Januari 2024  
**Proyek:** Sistem Manajemen Perpustakaan Digital  
**Analis:** [Nama Analis]

#### 1.1 Analisis Karakteristik Proyek

| Faktor | Deskripsi | Dampak |
|--------|-----------|---------|
| **Ukuran Tim** | 5 orang (1 PM, 2 Developer, 1 Designer, 1 Tester) | Tim kecil, cocok untuk Agile |
| **Kompleksitas** | Medium-High (multiple modules, integrations) | Perlu iterasi dan feedback |
| **Ketidakpastian Kebutuhan** | Medium (beberapa fitur belum jelas) | Perlu fleksibilitas |
| **Jadwal** | 6 bulan (24 minggu) | Perlu delivery bertahap |
| **Teknologi** | Modern stack (React, Node.js) | Perlu learning curve |

#### 1.2 Evaluasi Metodologi

##### Waterfall
- ✅ **Kelebihan:** Dokumentasi lengkap, struktur jelas
- ❌ **Kekurangan:** Tidak fleksibel, sulit adaptasi perubahan
- **Kesimpulan:** Tidak sesuai karena kebutuhan mungkin berubah

##### Agile-Scrum
- ✅ **Kelebihan:** Fleksibel, feedback cepat, tim kecil
- ❌ **Kekurangan:** Perlu disiplin tinggi, dokumentasi minimal
- **Kesimpulan:** Sangat sesuai untuk proyek ini

##### DevOps
- ✅ **Kelebihan:** Integrasi development-operations
- ❌ **Kekurangan:** Kompleks untuk tim kecil
- **Kesimpulan:** Dapat diintegrasikan dengan Scrum

#### 1.3 Rekomendasi

**Metodologi Terpilih:** Agile-Scrum dengan elemen DevOps

**Justifikasi:**
1. Tim kecil (5 orang) cocok untuk Scrum
2. Kebutuhan yang mungkin berubah memerlukan fleksibilitas
3. Perlu feedback cepat dari pengguna
4. Jadwal 6 bulan memungkinkan multiple sprints
5. Teknologi modern memerlukan pendekatan iteratif

## 2. Daftar Produk (Product Backlog)

### Epic 1: User Management
- **US-001:** Sebagai pustakawan, saya ingin dapat login ke sistem agar dapat mengakses fitur admin
- **US-002:** Sebagai mahasiswa, saya ingin dapat registrasi akun agar dapat meminjam buku
- **US-003:** Sebagai admin, saya ingin dapat mengelola user roles agar dapat mengontrol akses

### Epic 2: Book Management
- **US-004:** Sebagai pustakawan, saya ingin dapat menambah buku baru agar koleksi bertambah
- **US-005:** Sebagai pustakawan, saya ingin dapat mengedit informasi buku agar data akurat
- **US-006:** Sebagai pengguna, saya ingin dapat mencari buku berdasarkan judul, penulis, atau kategori

### Epic 3: Borrowing System
- **US-007:** Sebagai mahasiswa, saya ingin dapat meminjam buku agar dapat membaca di luar perpustakaan
- **US-008:** Sebagai pustakawan, saya ingin dapat mengembalikan buku agar status peminjaman terupdate
- **US-009:** Sebagai mahasiswa, saya ingin dapat melihat riwayat peminjaman agar dapat melacak buku yang dipinjam

### Epic 4: Reporting
- **US-010:** Sebagai manajer perpustakaan, saya ingin dapat melihat laporan statistik agar dapat monitoring penggunaan
- **US-011:** Sebagai pustakawan, saya ingin dapat melihat daftar buku terlambat agar dapat follow-up

## 3. Perencanaan Sprint Pertama

### Sprint 1: Foundation (2 minggu)
**Sprint Goal:** Setup dasar sistem dan autentikasi

#### Sprint Backlog:
- **US-001:** Login system untuk pustakawan
- **US-002:** Registrasi akun untuk mahasiswa
- **US-004:** CRUD buku (Create, Read, Update, Delete)

#### Definition of Done:
- [ ] Kode telah di-review
- [ ] Unit test coverage > 80%
- [ ] Dokumentasi API lengkap
- [ ] Deployed ke staging environment
- [ ] User acceptance testing passed

#### Sprint Planning:
- **Sprint Duration:** 2 minggu
- **Sprint Start:** 22 Januari 2024
- **Sprint End:** 5 Februari 2024
- **Daily Standup:** 09:00 WIB
- **Sprint Review:** 5 Februari 2024, 14:00 WIB
- **Sprint Retrospective:** 5 Februari 2024, 15:00 WIB

## 4. Piagam Proyek (Project Charter)

### Project Charter: Sistem Manajemen Perpustakaan Digital

**Project Name:** Sistem Manajemen Perpustakaan Digital  
**Project Manager:** [Nama PM]  
**Start Date:** 15 Januari 2024  
**End Date:** 15 Juli 2024  
**Budget:** Rp 500.000.000

#### Project Objectives:
1. Mengembangkan sistem perpustakaan digital yang modern dan user-friendly
2. Meningkatkan efisiensi operasional perpustakaan
3. Memberikan akses mudah bagi mahasiswa untuk mencari dan meminjam buku
4. Menyediakan laporan dan analitik untuk manajemen

#### Success Criteria:
- [ ] Sistem dapat menangani 1000+ user concurrent
- [ ] Response time < 2 detik untuk semua operasi
- [ ] 99.9% uptime availability
- [ ] User satisfaction > 85%
- [ ] Semua fitur core berfungsi dengan baik

#### Key Stakeholders:
- **Project Sponsor:** Rektor Universitas
- **Business Owner:** Manajer Perpustakaan
- **End Users:** Pustakawan, Mahasiswa
- **Technical Lead:** IT Manager
- **Project Team:** 5 orang

#### Risks and Mitigation:
- **Risk:** Perubahan kebutuhan yang signifikan
  - **Mitigation:** Agile approach, regular stakeholder communication
- **Risk:** Tim learning curve untuk teknologi baru
  - **Mitigation:** Training, pair programming, mentoring
- **Risk:** Integration dengan sistem existing
  - **Mitigation:** Early integration testing, API documentation

#### Approval:
- **Project Sponsor:** [Tanda Tangan] - 15 Januari 2024
- **Business Owner:** [Tanda Tangan] - 15 Januari 2024
- **Technical Lead:** [Tanda Tangan] - 15 Januari 2024

---

**Status:** Approved  
**Next Step:** Begin Sprint 1 Planning
