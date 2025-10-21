# Unit 4: Melakukan Klasifikasi dan Alokasi Kebutuhan Perangkat Lunak
**Kode Unit:** J.62SAD00.004.1

## Tujuan Pembelajaran
Setelah menyelesaikan unit ini, peserta mampu:
- Mengklasifikasi kebutuhan berdasarkan kategori dan prioritas
- Melakukan alokasi kebutuhan ke komponen sistem
- Membuat traceability matrix
- Mengelola dependencies antar kebutuhan

## Materi Teori

### 1. Klasifikasi Kebutuhan

#### A. Berdasarkan Jenis
**Functional Requirements:**
- Fitur yang harus disediakan sistem
- Input-output yang diharapkan
- Behavior sistem

**Non-Functional Requirements:**
- Performance (response time, throughput)
- Security (authentication, authorization)
- Usability (user interface, accessibility)
- Reliability (availability, fault tolerance)
- Scalability (capacity planning)

#### B. Berdasarkan Prioritas
**MoSCoW Prioritization:**
- **Must Have** - Critical, system tidak bisa berfungsi tanpa ini
- **Should Have** - Important, system bisa berfungsi tapi kurang optimal
- **Could Have** - Nice to have, meningkatkan user experience
- **Won't Have** - Tidak akan diimplementasi dalam release ini

#### C. Berdasarkan Sumber
**Business Requirements:**
- Strategic objectives
- Business rules
- Compliance requirements

**User Requirements:**
- User stories
- Use cases
- User scenarios

**System Requirements:**
- Technical specifications
- Integration requirements
- Performance requirements

### 2. Alokasi Kebutuhan

#### A. Komponen Sistem
**Presentation Layer:**
- User Interface
- User Experience
- Input validation

**Business Logic Layer:**
- Business rules
- Workflow
- Calculations

**Data Access Layer:**
- Database operations
- Data validation
- Data transformation

**Integration Layer:**
- External APIs
- Third-party services
- Legacy systems

#### B. Traceability Matrix
| Requirement ID | Source | Component | Priority | Status | Test Case |
|----------------|--------|-----------|----------|--------|-----------|
| REQ-001 | User Story | UI | Must | Approved | TC-001 |
| REQ-002 | Business Rule | Business Logic | Should | Pending | TC-002 |

### 3. Dependencies Management

#### A. Jenis Dependencies
**Functional Dependencies:**
- Requirement A harus diimplementasi sebelum Requirement B
- Sequential implementation

**Technical Dependencies:**
- Infrastructure requirements
- Third-party integrations
- Database schema

**Resource Dependencies:**
- Skill requirements
- External resources
- Budget allocation

## Latihan Praktis

### Exercise 1: Requirements Classification
**Tugas:** Klasifikasi requirements untuk sistem perpustakaan

**Langkah:**
1. Kategorikan requirements berdasarkan jenis (Functional/Non-functional)
2. Tentukan prioritas menggunakan MoSCoW
3. Identifikasi sumber requirements
4. Buat classification matrix

### Exercise 2: Component Allocation
**Tugas:** Alokasi requirements ke komponen sistem

**Langkah:**
1. Identifikasi komponen sistem
2. Alokasi setiap requirement ke komponen
3. Identifikasi dependencies
4. Buat allocation matrix

### Exercise 3: Traceability Matrix
**Tugas:** Buat traceability matrix lengkap

**Langkah:**
1. Assign unique ID untuk setiap requirement
2. Link requirements dengan source
3. Map ke komponen sistem
4. Link dengan test cases

## Proyek Integrasi: Requirements Classification

### Functional Requirements (Sistem Perpustakaan):

#### Must Have (Critical):
1. **User Authentication** - Login/logout, role-based access
2. **Book Search** - Search by title, author, ISBN
3. **Book Borrowing** - Check-out, check-in process
4. **User Management** - Add/edit/delete users
5. **Inventory Management** - Add/edit/delete books

#### Should Have (Important):
1. **Reservation System** - Book reservation, notification
2. **Fine Management** - Calculate and track fines
3. **Reporting** - Usage statistics, overdue reports
4. **Book Categories** - Genre classification
5. **User History** - Borrowing history

#### Could Have (Nice to Have):
1. **Recommendation System** - Book suggestions
2. **Mobile App** - Mobile interface
3. **Social Features** - Reviews, ratings
4. **Advanced Search** - Filters, sorting options
5. **Integration** - External library systems

### Non-Functional Requirements:

#### Performance:
- Response time < 2 seconds
- Support 100 concurrent users
- 99.9% uptime

#### Security:
- Role-based access control
- Data encryption
- Audit logging

#### Usability:
- Intuitive interface
- Mobile responsive
- Accessibility compliance

### Component Allocation:

#### Presentation Layer:
- User Interface (UI/UX)
- Input validation
- Error handling

#### Business Logic Layer:
- Authentication logic
- Borrowing rules
- Fine calculation
- Search algorithms

#### Data Access Layer:
- Database operations
- Data validation
- Data transformation

#### Integration Layer:
- Email notifications
- External APIs
- File uploads

## Deliverables Unit 4:
1. **Requirements Classification Matrix** - Klasifikasi lengkap requirements
2. **Component Allocation Matrix** - Alokasi ke komponen
3. **Traceability Matrix** - Mapping requirements
4. **Dependencies Diagram** - Visualisasi dependencies
5. **Prioritization Report** - Justifikasi prioritas

## Assessment Criteria
- [ ] Mampu mengklasifikasi requirements berdasarkan jenis
- [ ] Mampu menentukan prioritas menggunakan MoSCoW
- [ ] Mampu mengalokasi requirements ke komponen
- [ ] Mampu membuat traceability matrix
- [ ] Mampu mengidentifikasi dependencies

## Referensi
- [Requirements Engineering Best Practices](https://www.ireb.org/)
- [MoSCoW Prioritization](https://www.agilealliance.org/glossary/moscow/)
- [Traceability in Requirements](https://www.pmi.org/learning/library/requirements-traceability-6080)

---
**Previous Unit:** [Unit 3 - Teknik Elisitasi](../modules/unit-03-teknik-elisitasi.md)  
**Next Unit:** [Unit 5 - Negosiasi Kebutuhan](../modules/unit-05-negosiasi-kebutuhan.md)




