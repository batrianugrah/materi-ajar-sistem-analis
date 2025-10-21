# Unit 2: Contoh Output - Identifikasi Sumber Kebutuhan

## 1. Daftar Stakeholder Lengkap

### Stakeholder Internal

| No | Stakeholder | Peran | Departemen | Kontak |
|----|-------------|-------|------------|--------|
| 1 | Dr. Siti Aminah | Manajer Perpustakaan | Perpustakaan | siti.aminah@univ.ac.id |
| 2 | Budi Santoso | Pustakawan Senior | Perpustakaan | budi.santoso@univ.ac.id |
| 3 | Rina Wijaya | Pustakawan | Perpustakaan | rina.wijaya@univ.ac.id |
| 4 | Ahmad Fauzi | IT Manager | IT Department | ahmad.fauzi@univ.ac.id |
| 5 | Sarah Putri | Mahasiswa (User Representative) | Mahasiswa | sarah.putri@student.univ.ac.id |
| 6 | Prof. Dr. John Doe | Dosen (User Representative) | Akademik | john.doe@univ.ac.id |

### Stakeholder Eksternal

| No | Stakeholder | Peran | Organisasi | Kontak |
|----|-------------|-------|------------|--------|
| 1 | PT. Penerbit ABC | Pemasok Buku | Vendor | contact@penerbitabc.com |
| 2 | Kementerian Pendidikan | Regulator | Pemerintah | info@kemdikbud.go.id |
| 3 | Perpustakaan Nasional | Standar Perpustakaan | Pemerintah | info@perpusnas.go.id |

## 2. Grid Kekuatan-Minat (Power-Interest Grid)

```
                    TINGGI
                     │
                     │
    Kekuatan Tinggi   │   Kekuatan Tinggi
    Minat Rendah      │   Minat Tinggi
    ──────────────────┼──────────────────
                     │
    Kekuatan Rendah   │   Kekuatan Rendah
    Minat Rendah      │   Minat Tinggi
                     │
                     └─────────────────
                    RENDAH              TINGGI
                              Minat
```

### Kategori Stakeholder:

#### Kekuatan Tinggi, Minat Tinggi (Kelola dengan Ketat)
- **Dr. Siti Aminah** (Manajer Perpustakaan)
- **Ahmad Fauzi** (IT Manager)

#### Kekuatan Tinggi, Minat Rendah (Jaga Kepuasan)
- **Kementerian Pendidikan** (Regulator)
- **Perpustakaan Nasional** (Standar)

#### Kekuatan Rendah, Minat Tinggi (Jaga Informasi)
- **Budi Santoso** (Pustakawan Senior)
- **Rina Wijaya** (Pustakawan)
- **Sarah Putri** (Mahasiswa)
- **Prof. Dr. John Doe** (Dosen)

#### Kekuatan Rendah, Minat Rendah (Pantau)
- **PT. Penerbit ABC** (Vendor)

## 3. Rencana Komunikasi

### Matriks Komunikasi Stakeholder

| Stakeholder | Frekuensi | Metode | Format | Tanggung Jawab |
|-------------|-----------|--------|--------|----------------|
| **Dr. Siti Aminah** | Mingguan | Meeting | Laporan Progress | Project Manager |
| **Ahmad Fauzi** | Mingguan | Email + Meeting | Technical Update | Technical Lead |
| **Budi Santoso** | 2x per minggu | Workshop | Demo & Feedback | Business Analyst |
| **Rina Wijaya** | 2x per minggu | Workshop | Demo & Feedback | Business Analyst |
| **Sarah Putri** | Bulanan | Focus Group | User Testing | UX Designer |
| **Prof. Dr. John Doe** | Bulanan | Interview | Requirements Review | Business Analyst |
| **PT. Penerbit ABC** | Triwulan | Email | Status Update | Project Manager |
| **Kementerian Pendidikan** | Triwulan | Email | Compliance Report | Project Manager |

### Jadwal Komunikasi

#### Mingguan (Setiap Senin, 10:00 WIB)
- **Meeting dengan Manajer Perpustakaan**
  - Agenda: Progress update, issues, decisions needed
  - Durasi: 1 jam
  - Participants: PM, Business Owner, Technical Lead

#### Mingguan (Setiap Rabu, 14:00 WIB)
- **Technical Review dengan IT Manager**
  - Agenda: Technical progress, infrastructure, security
  - Durasi: 1 jam
  - Participants: Technical Lead, IT Manager, Developers

#### 2x per Minggu (Selasa & Kamis, 15:00 WIB)
- **Workshop dengan Pustakawan**
  - Agenda: Feature demo, feedback, requirements clarification
  - Durasi: 2 jam
  - Participants: Business Analyst, Pustakawan, UX Designer

#### Bulanan (Akhir bulan)
- **Focus Group dengan Mahasiswa**
  - Agenda: User testing, usability feedback
  - Durasi: 3 jam
  - Participants: UX Designer, Mahasiswa (5-8 orang)

## 4. Matriks Sumber Kebutuhan

### Pemetaan Stakeholder dengan Jenis Kebutuhan

#### Kebutuhan Fungsional

| Stakeholder | Kebutuhan Fungsional | Prioritas | Kompleksitas |
|-------------|---------------------|-----------|--------------|
| **Pustakawan** | - Pencarian buku<br>- Manajemen koleksi<br>- Peminjaman/pengembalian | Tinggi | Medium |
| **Mahasiswa** | - Pencarian buku<br>- Peminjaman online<br>- Riwayat peminjaman | Tinggi | Medium |
| **Manajer Perpustakaan** | - Laporan statistik<br>- Monitoring sistem<br>- User management | Sedang | High |
| **Dosen** | - Pencarian jurnal<br>- Reservasi buku<br>- Notifikasi | Sedang | Low |

#### Kebutuhan Non-Fungsional

| Stakeholder | Kebutuhan Non-Fungsional | Prioritas | Kompleksitas |
|-------------|-------------------------|-----------|--------------|
| **IT Manager** | - Keamanan sistem<br>- Performa tinggi<br>- Skalabilitas | Tinggi | High |
| **Pustakawan** | - Kemudahan penggunaan<br>- Interface intuitif | Tinggi | Medium |
| **Mahasiswa** | - Akses mobile<br>- Response time cepat | Sedang | Medium |
| **Manajer** | - Backup otomatis<br>- Audit trail | Sedang | High |

#### Kebutuhan Bisnis

| Stakeholder | Kebutuhan Bisnis | Prioritas | Dampak |
|-------------|------------------|-----------|--------|
| **Manajer Perpustakaan** | - ROI positif<br>- Efisiensi operasional | Tinggi | High |
| **Kementerian Pendidikan** | - Kepatuhan standar<br>- Laporan regulasi | Tinggi | Medium |
| **Perpustakaan Nasional** | - Standar metadata<br>- Interoperabilitas | Sedang | Medium |
| **Vendor** | - Integrasi API<br>- Data exchange | Rendah | Low |

## 5. Analisis Pengaruh dan Minat

### Matriks Analisis Stakeholder

| Stakeholder | Pengaruh | Minat | Strategi | Risiko |
|-------------|----------|-------|----------|--------|
| **Dr. Siti Aminah** | Sangat Tinggi | Sangat Tinggi | Engage & Manage | High - Bisa membatalkan proyek |
| **Ahmad Fauzi** | Tinggi | Tinggi | Keep Satisfied | Medium - Bisa menghambat implementasi |
| **Budi Santoso** | Sedang | Tinggi | Keep Informed | Low - Bisa memberikan feedback negatif |
| **Rina Wijaya** | Sedang | Tinggi | Keep Informed | Low - Bisa memberikan feedback negatif |
| **Sarah Putri** | Rendah | Tinggi | Monitor | Low - Bisa mempengaruhi user adoption |
| **Prof. Dr. John Doe** | Rendah | Sedang | Monitor | Low - Bisa mempengaruhi user adoption |
| **Kementerian Pendidikan** | Tinggi | Rendah | Keep Satisfied | Medium - Bisa mempengaruhi compliance |
| **Perpustakaan Nasional** | Sedang | Rendah | Monitor | Low - Bisa mempengaruhi standar |
| **PT. Penerbit ABC** | Rendah | Rendah | Monitor | Low - Bisa mempengaruhi integrasi |

## 6. Rencana Engagement Stakeholder

### Phase 1: Project Initiation (Minggu 1-2)
- **Kick-off meeting** dengan semua stakeholder internal
- **Stakeholder analysis workshop** untuk validasi dan tambahan stakeholder
- **Communication plan setup** dan tools yang akan digunakan

### Phase 2: Requirements Gathering (Minggu 3-6)
- **Individual interviews** dengan key stakeholders
- **Focus groups** dengan user groups
- **Workshop** untuk requirements prioritization

### Phase 3: Development (Minggu 7-20)
- **Regular updates** sesuai jadwal komunikasi
- **Demo sessions** untuk feedback
- **Change management** untuk requirement changes

### Phase 4: Testing & Deployment (Minggu 21-24)
- **User acceptance testing** dengan end users
- **Training sessions** untuk semua user groups
- **Go-live support** dan monitoring

---

**Status:** Completed  
**Next Step:** Begin Unit 3 - Teknik Elisitasi
