# Unit 12: Merancang Komponen Perangkat Lunak
**Kode Unit:** J.62SAD00.012.1

## Tujuan Pembelajaran
Setelah menyelesaikan unit ini, peserta mampu:
- Merancang UI components yang user-friendly
- Merancang business logic components yang robust
- Merancang data access components yang efficient
- Merancang integration components yang scalable
- Membuat component specifications yang detail

## Materi Teori

### 1. Component Design Overview

#### A. Component Types
**User Interface Components:**
- Input components
- Display components
- Navigation components
- Layout components

**Business Logic Components:**
- Service components
- Controller components
- Manager components
- Utility components

**Data Access Components:**
- Repository components
- DAO components
- ORM components
- Cache components

**Integration Components:**
- API components
- Message components
- Event components
- Protocol components

#### B. Component Principles
**Single Responsibility:**
- Each component has one purpose
- Clear boundaries
- Independent functionality
- Easier testing

**Loose Coupling:**
- Minimal dependencies
- Interface-based design
- Dependency injection
- Easier maintenance

**High Cohesion:**
- Related functionality grouped
- Clear component boundaries
- Consistent interfaces
- Better organization

### 2. UI Component Design

#### A. Component Hierarchy
**Atomic Components:**
- Button
- Input
- Label
- Icon

**Molecular Components:**
- SearchBox
- BookCard
- UserProfile
- NavigationMenu

**Organism Components:**
- Header
- Sidebar
- BookList
- UserDashboard

**Template Components:**
- PageLayout
- FormLayout
- ListLayout
- DetailLayout

#### B. Component Properties
**Props Interface:**
- Required props
- Optional props
- Default values
- Type definitions

**State Management:**
- Local state
- Global state
- State updates
- State persistence

**Event Handling:**
- User interactions
- Event callbacks
- Event propagation
- Event validation

### 3. Business Logic Component Design

#### A. Service Components
**Service Interface:**
- Method definitions
- Parameter types
- Return types
- Exception handling

**Service Implementation:**
- Business logic
- Data validation
- Error handling
- Logging

**Service Dependencies:**
- Repository dependencies
- External service dependencies
- Configuration dependencies
- Utility dependencies

#### B. Controller Components
**Controller Responsibilities:**
- Request handling
- Response formatting
- Input validation
- Error handling

**Controller Methods:**
- CRUD operations
- Business operations
- Validation operations
- Error operations

**Controller Dependencies:**
- Service dependencies
- Repository dependencies
- Utility dependencies
- Configuration dependencies

### 4. Data Access Component Design

#### A. Repository Components
**Repository Interface:**
- CRUD operations
- Query methods
- Transaction methods
- Cache methods

**Repository Implementation:**
- Database operations
- Query optimization
- Caching strategies
- Error handling

**Repository Dependencies:**
- Database connection
- ORM dependencies
- Cache dependencies
- Configuration dependencies

#### B. DAO Components
**DAO Interface:**
- Data access methods
- Query methods
- Transaction methods
- Connection methods

**DAO Implementation:**
- SQL operations
- Query optimization
- Connection management
- Error handling

**DAO Dependencies:**
- Database connection
- SQL dependencies
- Configuration dependencies
- Utility dependencies

### 5. Integration Component Design

#### A. API Components
**API Client:**
- HTTP client
- Request/response handling
- Error handling
- Authentication

**API Service:**
- Service abstraction
- Business logic
- Data transformation
- Error handling

**API Configuration:**
- Endpoint configuration
- Authentication configuration
- Timeout configuration
- Retry configuration

#### B. Message Components
**Message Producer:**
- Message creation
- Message formatting
- Message sending
- Error handling

**Message Consumer:**
- Message receiving
- Message processing
- Message acknowledgment
- Error handling

**Message Configuration:**
- Queue configuration
- Topic configuration
- Consumer configuration
- Producer configuration

## Latihan Praktis

### Exercise 1: UI Component Design
**Tugas:** Rancang UI components untuk sistem perpustakaan

**Langkah:**
1. Identifikasi UI requirements
2. Rancang component hierarchy
3. Definisikan component interfaces
4. Buat component specifications
5. Validasi component design

### Exercise 2: Business Logic Component Design
**Tugas:** Rancang business logic components

**Langkah:**
1. Identifikasi business requirements
2. Rancang service components
3. Rancang controller components
4. Definisikan component interfaces
5. Validasi component design

### Exercise 3: Data Access Component Design
**Tugas:** Rancang data access components

**Langkah:**
1. Identifikasi data requirements
2. Rancang repository components
3. Rancang DAO components
4. Definisikan component interfaces
5. Validasi component design

### Exercise 4: Integration Component Design
**Tugas:** Rancang integration components

**Langkah:**
1. Identifikasi integration requirements
2. Rancang API components
3. Rancang message components
4. Definisikan component interfaces
5. Validasi component design

## Proyek Integrasi: Component Design

### Component Design untuk Sistem Perpustakaan

#### 1. UI Components

##### Atomic Components
**Button Component:**
```typescript
interface ButtonProps {
  label: string;
  type: 'primary' | 'secondary' | 'danger';
  size: 'small' | 'medium' | 'large';
  disabled?: boolean;
  onClick: () => void;
}
```

**Input Component:**
```typescript
interface InputProps {
  type: 'text' | 'email' | 'password' | 'number';
  placeholder?: string;
  value: string;
  onChange: (value: string) => void;
  error?: string;
  required?: boolean;
}
```

**Label Component:**
```typescript
interface LabelProps {
  text: string;
  required?: boolean;
  error?: string;
  htmlFor?: string;
}
```

##### Molecular Components
**SearchBox Component:**
```typescript
interface SearchBoxProps {
  placeholder: string;
  value: string;
  onChange: (value: string) => void;
  onSearch: (query: string) => void;
  suggestions?: string[];
}
```

**BookCard Component:**
```typescript
interface BookCardProps {
  book: {
    id: string;
    title: string;
    author: string;
    isbn: string;
    availability: boolean;
  };
  onBorrow: (bookId: string) => void;
  onReserve: (bookId: string) => void;
}
```

**UserProfile Component:**
```typescript
interface UserProfileProps {
  user: {
    id: string;
    name: string;
    email: string;
    role: string;
    avatar?: string;
  };
  onEdit: () => void;
  onLogout: () => void;
}
```

##### Organism Components
**Header Component:**
```typescript
interface HeaderProps {
  user: User;
  onLogout: () => void;
  onProfile: () => void;
  onSearch: (query: string) => void;
}
```

**BookList Component:**
```typescript
interface BookListProps {
  books: Book[];
  loading: boolean;
  onBookSelect: (book: Book) => void;
  onBorrow: (bookId: string) => void;
  onReserve: (bookId: string) => void;
}
```

**UserDashboard Component:**
```typescript
interface UserDashboardProps {
  user: User;
  borrowedBooks: Book[];
  reservedBooks: Book[];
  onReturn: (bookId: string) => void;
  onCancelReservation: (bookId: string) => void;
}
```

#### 2. Business Logic Components

##### Service Components
**AuthenticationService:**
```typescript
interface AuthenticationService {
  login(credentials: LoginCredentials): Promise<AuthResult>;
  logout(): Promise<void>;
  refreshToken(): Promise<string>;
  getCurrentUser(): Promise<User>;
  changePassword(oldPassword: string, newPassword: string): Promise<void>;
}
```

**BookService:**
```typescript
interface BookService {
  searchBooks(query: SearchQuery): Promise<Book[]>;
  getBookById(id: string): Promise<Book>;
  addBook(book: BookInput): Promise<Book>;
  updateBook(id: string, book: BookInput): Promise<Book>;
  deleteBook(id: string): Promise<void>;
  getBookCategories(): Promise<Category[]>;
}
```

**BorrowingService:**
```typescript
interface BorrowingService {
  borrowBook(userId: string, bookId: string): Promise<Borrowing>;
  returnBook(borrowingId: string): Promise<void>;
  getBorrowedBooks(userId: string): Promise<Borrowing[]>;
  getBorrowingHistory(userId: string): Promise<Borrowing[]>;
  calculateFine(borrowingId: string): Promise<number>;
}
```

**UserService:**
```typescript
interface UserService {
  createUser(user: UserInput): Promise<User>;
  updateUser(id: string, user: UserInput): Promise<User>;
  deleteUser(id: string): Promise<void>;
  getUserById(id: string): Promise<User>;
  getUsers(query: UserQuery): Promise<User[]>;
  changeUserRole(id: string, role: string): Promise<void>;
}
```

##### Controller Components
**AuthController:**
```typescript
class AuthController {
  async login(req: Request, res: Response): Promise<void>;
  async logout(req: Request, res: Response): Promise<void>;
  async refreshToken(req: Request, res: Response): Promise<void>;
  async getCurrentUser(req: Request, res: Response): Promise<void>;
}
```

**BookController:**
```typescript
class BookController {
  async searchBooks(req: Request, res: Response): Promise<void>;
  async getBookById(req: Request, res: Response): Promise<void>;
  async createBook(req: Request, res: Response): Promise<void>;
  async updateBook(req: Request, res: Response): Promise<void>;
  async deleteBook(req: Request, res: Response): Promise<void>;
}
```

**BorrowingController:**
```typescript
class BorrowingController {
  async borrowBook(req: Request, res: Response): Promise<void>;
  async returnBook(req: Request, res: Response): Promise<void>;
  async getBorrowedBooks(req: Request, res: Response): Promise<void>;
  async getBorrowingHistory(req: Request, res: Response): Promise<void>;
}
```

#### 3. Data Access Components

##### Repository Components
**BookRepository:**
```typescript
interface BookRepository {
  findById(id: string): Promise<Book | null>;
  findByTitle(title: string): Promise<Book[]>;
  findByAuthor(author: string): Promise<Book[]>;
  findByCategory(categoryId: string): Promise<Book[]>;
  search(query: SearchQuery): Promise<Book[]>;
  create(book: BookInput): Promise<Book>;
  update(id: string, book: BookInput): Promise<Book>;
  delete(id: string): Promise<void>;
  findAvailable(): Promise<Book[]>;
  findBorrowed(): Promise<Book[]>;
}
```

**UserRepository:**
```typescript
interface UserRepository {
  findById(id: string): Promise<User | null>;
  findByEmail(email: string): Promise<User | null>;
  findByUsername(username: string): Promise<User | null>;
  findByRole(role: string): Promise<User[]>;
  create(user: UserInput): Promise<User>;
  update(id: string, user: UserInput): Promise<User>;
  delete(id: string): Promise<void>;
  findAll(query: UserQuery): Promise<User[]>;
}
```

**BorrowingRepository:**
```typescript
interface BorrowingRepository {
  findById(id: string): Promise<Borrowing | null>;
  findByUserId(userId: string): Promise<Borrowing[]>;
  findByBookId(bookId: string): Promise<Borrowing[]>;
  findActive(): Promise<Borrowing[]>;
  findOverdue(): Promise<Borrowing[]>;
  create(borrowing: BorrowingInput): Promise<Borrowing>;
  update(id: string, borrowing: BorrowingInput): Promise<Borrowing>;
  delete(id: string): Promise<void>;
  findHistory(userId: string): Promise<Borrowing[]>;
}
```

##### DAO Components
**BookDAO:**
```typescript
class BookDAO {
  async findById(id: string): Promise<Book | null>;
  async findByTitle(title: string): Promise<Book[]>;
  async findByAuthor(author: string): Promise<Book[]>;
  async findByCategory(categoryId: string): Promise<Book[]>;
  async search(query: SearchQuery): Promise<Book[]>;
  async create(book: BookInput): Promise<Book>;
  async update(id: string, book: BookInput): Promise<Book>;
  async delete(id: string): Promise<void>;
}
```

**UserDAO:**
```typescript
class UserDAO {
  async findById(id: string): Promise<User | null>;
  async findByEmail(email: string): Promise<User | null>;
  async findByUsername(username: string): Promise<User | null>;
  async findByRole(role: string): Promise<User[]>;
  async create(user: UserInput): Promise<User>;
  async update(id: string, user: UserInput): Promise<User>;
  async delete(id: string): Promise<void>;
}
```

#### 4. Integration Components

##### API Components
**ExternalBookAPI:**
```typescript
interface ExternalBookAPI {
  searchBooks(query: string): Promise<ExternalBook[]>;
  getBookDetails(isbn: string): Promise<ExternalBook>;
  getBookCover(isbn: string): Promise<string>;
  getBookMetadata(isbn: string): Promise<BookMetadata>;
}
```

**EmailService:**
```typescript
interface EmailService {
  sendWelcomeEmail(user: User): Promise<void>;
  sendBorrowingNotification(borrowing: Borrowing): Promise<void>;
  sendReturnReminder(borrowing: Borrowing): Promise<void>;
  sendReservationNotification(reservation: Reservation): Promise<void>;
}
```

**SMSService:**
```typescript
interface SMSService {
  sendBorrowingSMS(borrowing: Borrowing): Promise<void>;
  sendReturnReminderSMS(borrowing: Borrowing): Promise<void>;
  sendReservationSMS(reservation: Reservation): Promise<void>;
}
```

##### Message Components
**NotificationProducer:**
```typescript
interface NotificationProducer {
  sendBorrowingNotification(borrowing: Borrowing): Promise<void>;
  sendReturnReminder(borrowing: Borrowing): Promise<void>;
  sendReservationNotification(reservation: Reservation): Promise<void>;
  sendFineNotification(fine: Fine): Promise<void>;
}
```

**NotificationConsumer:**
```typescript
interface NotificationConsumer {
  processBorrowingNotification(message: BorrowingMessage): Promise<void>;
  processReturnReminder(message: ReturnReminderMessage): Promise<void>;
  processReservationNotification(message: ReservationMessage): Promise<void>;
  processFineNotification(message: FineMessage): Promise<void>;
}
```

#### 5. Component Specifications

##### Component Interface Specifications
**Props Interface:**
- Required props
- Optional props
- Default values
- Type definitions
- Validation rules

**State Interface:**
- State properties
- State types
- State updates
- State persistence
- State validation

**Event Interface:**
- Event types
- Event handlers
- Event parameters
- Event validation
- Event propagation

##### Component Implementation Specifications
**Component Structure:**
- Component hierarchy
- Component composition
- Component inheritance
- Component dependencies
- Component interfaces

**Component Behavior:**
- Component lifecycle
- Component methods
- Component events
- Component validation
- Component error handling

**Component Testing:**
- Unit testing
- Integration testing
- Component testing
- User testing
- Performance testing

## Deliverables Unit 12:
1. **UI Component Specifications** - Spesifikasi komponen UI
2. **Business Logic Component Specifications** - Spesifikasi komponen business logic
3. **Data Access Component Specifications** - Spesifikasi komponen data access
4. **Integration Component Specifications** - Spesifikasi komponen integrasi
5. **Component Interface Documentation** - Dokumentasi interface komponen
6. **Component Implementation Guide** - Panduan implementasi komponen

## Assessment Criteria
- [ ] Mampu merancang UI components yang user-friendly
- [ ] Mampu merancang business logic components yang robust
- [ ] Mampu merancang data access components yang efficient
- [ ] Mampu merancang integration components yang scalable
- [ ] Mampu membuat component specifications yang detail

## Referensi
- [Component Design Patterns](https://www.oreilly.com/)
- [UI Component Best Practices](https://material.io/)
- [Business Logic Design](https://www.martinfowler.com/)
- [Data Access Patterns](https://www.martinfowler.com/)

---
**Previous Unit:** [Unit 11 - Struktur Perangkat Lunak](../modules/unit-11-struktur-perangkat-lunak.md)  
**Next Unit:** [Unit 13 - User Interface Design](../modules/unit-13-user-interface.md)




