# Unit 7: Contoh Output - Software Environment

## 1. Spesifikasi Environment Development

### Development Environment
**Environment Name:** DEV  
**Purpose:** Development dan testing oleh tim developer  
**Access:** Tim development (5 orang)

#### Hardware Requirements
| Komponen | Spesifikasi | Justifikasi |
|----------|-------------|-------------|
| **CPU** | Intel i7-10700K atau AMD Ryzen 7 3700X | Multi-threading untuk development |
| **RAM** | 32GB DDR4 | Multiple applications dan database |
| **Storage** | 1TB NVMe SSD | Fast I/O untuk development |
| **Network** | Gigabit Ethernet | Fast code synchronization |

#### Software Requirements
| Software | Version | Purpose |
|----------|---------|---------|
| **Operating System** | Ubuntu 20.04 LTS | Development platform |
| **Node.js** | 16.18.0 | Backend runtime |
| **npm** | 8.19.2 | Package manager |
| **React** | 18.2.0 | Frontend framework |
| **PostgreSQL** | 14.5 | Database |
| **Git** | 2.34.1 | Version control |
| **Docker** | 20.10.21 | Containerization |
| **VS Code** | 1.73.0 | IDE |

#### Development Tools
| Tool | Version | Purpose |
|------|---------|---------|
| **Postman** | 10.5.0 | API testing |
| **pgAdmin** | 7.1 | Database management |
| **Chrome DevTools** | Latest | Frontend debugging |
| **ESLint** | 8.30.0 | Code quality |
| **Prettier** | 2.8.0 | Code formatting |
| **Jest** | 29.3.1 | Unit testing |
| **Cypress** | 12.3.0 | E2E testing |

### Testing Environment
**Environment Name:** TEST  
**Purpose:** Testing dan quality assurance  
**Access:** QA team dan stakeholders

#### Hardware Requirements
| Komponen | Spesifikasi | Justifikasi |
|----------|-------------|-------------|
| **CPU** | Intel i5-10400 atau AMD Ryzen 5 3600 | Sufficient untuk testing |
| **RAM** | 16GB DDR4 | Multiple test scenarios |
| **Storage** | 500GB SSD | Test data storage |
| **Network** | Gigabit Ethernet | Test network conditions |

#### Software Requirements
| Software | Version | Purpose |
|----------|---------|---------|
| **Operating System** | Ubuntu 20.04 LTS | Testing platform |
| **Node.js** | 16.18.0 | Application runtime |
| **PostgreSQL** | 14.5 | Test database |
| **Docker** | 20.10.21 | Containerized testing |
| **Selenium** | 4.8.0 | Automated testing |
| **JMeter** | 5.5 | Performance testing |

### Staging Environment
**Environment Name:** STAGING  
**Purpose:** Pre-production testing dan stakeholder review  
**Access:** Stakeholders dan end users

#### Hardware Requirements
| Komponen | Spesifikasi | Justifikasi |
|----------|-------------|-------------|
| **CPU** | Intel Xeon E5-2680 v4 | Production-like performance |
| **RAM** | 32GB DDR4 | Production-like memory |
| **Storage** | 1TB SSD | Production-like storage |
| **Network** | Gigabit Ethernet | Production-like network |

#### Software Requirements
| Software | Version | Purpose |
|----------|---------|---------|
| **Operating System** | Ubuntu 20.04 LTS | Production platform |
| **Node.js** | 16.18.0 | Application runtime |
| **PostgreSQL** | 14.5 | Database |
| **Nginx** | 1.18.0 | Web server |
| **PM2** | 5.2.0 | Process manager |
| **Docker** | 20.10.21 | Containerization |

### Production Environment
**Environment Name:** PROD  
**Purpose:** Live system untuk end users  
**Access:** End users dan administrators

#### Hardware Requirements
| Komponen | Spesifikasi | Justifikasi |
|----------|-------------|-------------|
| **CPU** | Intel Xeon E5-2680 v4 (2x) | High performance untuk production |
| **RAM** | 64GB DDR4 | High memory untuk concurrent users |
| **Storage** | 2TB SSD (RAID 1) | High availability storage |
| **Network** | 10 Gigabit Ethernet | High bandwidth untuk production |
| **Backup** | 4TB HDD | Data backup |

#### Software Requirements
| Software | Version | Purpose |
|----------|---------|---------|
| **Operating System** | Ubuntu 20.04 LTS | Production platform |
| **Node.js** | 16.18.0 | Application runtime |
| **PostgreSQL** | 14.5 | Production database |
| **Nginx** | 1.18.0 | Load balancer dan web server |
| **PM2** | 5.2.0 | Process manager |
| **Docker** | 20.10.21 | Containerization |
| **Redis** | 6.2.7 | Caching |
| **Let's Encrypt** | Latest | SSL certificates |

## 2. Konfigurasi Environment

### Development Environment Configuration

#### Database Configuration
```sql
-- Development Database Setup
CREATE DATABASE library_dev;
CREATE USER dev_user WITH PASSWORD 'dev_password';
GRANT ALL PRIVILEGES ON DATABASE library_dev TO dev_user;

-- Development Tables
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    role VARCHAR(20) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE books (
    id SERIAL PRIMARY KEY,
    title VARCHAR(200) NOT NULL,
    author VARCHAR(100) NOT NULL,
    isbn VARCHAR(20) UNIQUE,
    category VARCHAR(50),
    status VARCHAR(20) DEFAULT 'available',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

#### Application Configuration
```javascript
// config/development.js
module.exports = {
  database: {
    host: 'localhost',
    port: 5432,
    database: 'library_dev',
    username: 'dev_user',
    password: 'dev_password'
  },
  server: {
    port: 3000,
    host: 'localhost'
  },
  jwt: {
    secret: 'dev_secret_key',
    expiresIn: '24h'
  },
  email: {
    service: 'gmail',
    user: 'dev@library.com',
    password: 'dev_password'
  }
};
```

### Testing Environment Configuration

#### Test Database Setup
```sql
-- Testing Database Setup
CREATE DATABASE library_test;
CREATE USER test_user WITH PASSWORD 'test_password';
GRANT ALL PRIVILEGES ON DATABASE library_test TO test_user;

-- Test Data
INSERT INTO users (name, email, role) VALUES
('Test User', 'test@library.com', 'student'),
('Test Librarian', 'librarian@library.com', 'librarian');

INSERT INTO books (title, author, isbn, category) VALUES
('Test Book 1', 'Test Author 1', '1234567890', 'Fiction'),
('Test Book 2', 'Test Author 2', '0987654321', 'Non-Fiction');
```

#### Test Configuration
```javascript
// config/testing.js
module.exports = {
  database: {
    host: 'localhost',
    port: 5432,
    database: 'library_test',
    username: 'test_user',
    password: 'test_password'
  },
  server: {
    port: 3001,
    host: 'localhost'
  },
  jwt: {
    secret: 'test_secret_key',
    expiresIn: '1h'
  }
};
```

### Staging Environment Configuration

#### Staging Database Setup
```sql
-- Staging Database Setup
CREATE DATABASE library_staging;
CREATE USER staging_user WITH PASSWORD 'staging_password';
GRANT ALL PRIVILEGES ON DATABASE library_staging TO staging_user;

-- Staging Data (Production-like)
INSERT INTO users (name, email, role) VALUES
('Staging User', 'user@staging.library.com', 'student'),
('Staging Librarian', 'librarian@staging.library.com', 'librarian'),
('Staging Manager', 'manager@staging.library.com', 'manager');
```

#### Staging Configuration
```javascript
// config/staging.js
module.exports = {
  database: {
    host: 'staging-db.library.com',
    port: 5432,
    database: 'library_staging',
    username: 'staging_user',
    password: 'staging_password'
  },
  server: {
    port: 3000,
    host: 'staging.library.com'
  },
  jwt: {
    secret: 'staging_secret_key',
    expiresIn: '8h'
  },
  email: {
    service: 'gmail',
    user: 'noreply@staging.library.com',
    password: 'staging_email_password'
  }
};
```

### Production Environment Configuration

#### Production Database Setup
```sql
-- Production Database Setup
CREATE DATABASE library_prod;
CREATE USER prod_user WITH PASSWORD 'prod_password';
GRANT ALL PRIVILEGES ON DATABASE library_prod TO prod_user;

-- Production Security
ALTER USER prod_user WITH CONNECTION LIMIT 100;
```

#### Production Configuration
```javascript
// config/production.js
module.exports = {
  database: {
    host: 'prod-db.library.com',
    port: 5432,
    database: 'library_prod',
    username: 'prod_user',
    password: process.env.DB_PASSWORD
  },
  server: {
    port: 3000,
    host: 'library.com'
  },
  jwt: {
    secret: process.env.JWT_SECRET,
    expiresIn: '8h'
  },
  email: {
    service: 'gmail',
    user: 'noreply@library.com',
    password: process.env.EMAIL_PASSWORD
  },
  redis: {
    host: 'redis.library.com',
    port: 6379,
    password: process.env.REDIS_PASSWORD
  }
};
```

## 3. Security Requirements

### Development Environment Security
- **Access Control:** VPN required untuk remote access
- **Authentication:** SSH key-based authentication
- **Data Protection:** No production data in development
- **Network Security:** Firewall rules untuk development ports

### Testing Environment Security
- **Access Control:** VPN required untuk remote access
- **Authentication:** SSH key-based authentication
- **Data Protection:** Anonymized test data only
- **Network Security:** Firewall rules untuk testing ports

### Staging Environment Security
- **Access Control:** VPN required untuk remote access
- **Authentication:** Multi-factor authentication
- **Data Protection:** Staging data only, no production data
- **Network Security:** Firewall rules untuk staging ports
- **SSL/TLS:** Let's Encrypt certificates

### Production Environment Security
- **Access Control:** VPN required untuk remote access
- **Authentication:** Multi-factor authentication
- **Data Protection:** Encryption at rest dan in transit
- **Network Security:** Firewall rules untuk production ports
- **SSL/TLS:** Let's Encrypt certificates
- **Monitoring:** Security monitoring dan alerting
- **Backup:** Encrypted backups

## 4. Monitoring dan Logging

### Development Environment
- **Logging:** Console logging untuk debugging
- **Monitoring:** Basic application monitoring
- **Alerts:** Email alerts untuk critical errors

### Testing Environment
- **Logging:** File logging untuk test results
- **Monitoring:** Test execution monitoring
- **Alerts:** Email alerts untuk test failures

### Staging Environment
- **Logging:** File logging untuk staging activities
- **Monitoring:** Application performance monitoring
- **Alerts:** Email alerts untuk staging issues

### Production Environment
- **Logging:** Centralized logging dengan ELK stack
- **Monitoring:** Comprehensive monitoring dengan Prometheus
- **Alerts:** Multiple alert channels (email, SMS, Slack)
- **Metrics:** Performance metrics dan business metrics

## 5. Backup dan Recovery

### Development Environment
- **Backup:** Daily automated backup
- **Retention:** 7 days
- **Recovery:** Manual recovery process

### Testing Environment
- **Backup:** Daily automated backup
- **Retention:** 14 days
- **Recovery:** Manual recovery process

### Staging Environment
- **Backup:** Daily automated backup
- **Retention:** 30 days
- **Recovery:** Automated recovery process

### Production Environment
- **Backup:** Daily automated backup dengan encryption
- **Retention:** 365 days
- **Recovery:** Automated recovery process
- **Disaster Recovery:** Multi-site backup strategy

## 6. Deployment Strategy

### Development to Testing
- **Trigger:** Manual deployment
- **Process:** Automated build dan deployment
- **Validation:** Automated testing
- **Rollback:** Manual rollback

### Testing to Staging
- **Trigger:** Manual deployment
- **Process:** Automated build dan deployment
- **Validation:** Automated testing dan stakeholder approval
- **Rollback:** Manual rollback

### Staging to Production
- **Trigger:** Manual deployment
- **Process:** Automated build dan deployment
- **Validation:** Automated testing dan stakeholder approval
- **Rollback:** Automated rollback capability

---

**Status:** Completed  
**Next Step:** Begin Unit 8 - Spesifikasi Kebutuhan
