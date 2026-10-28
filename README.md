# Worker Database Case Study

Production-ready schema script definitions and relational analytics suite for standard enterprise corporate structures.

## 📋 Data Dictionary

### 1. Workers

| Column Name | Data Type | Key Type | Description |
| :--- | :--- | :--- | :--- |
| `WORKER_ID` | INT | Primary Key | Unique employee identifier |
| `FIRST_NAME` | VARCHAR(25) | - | Given employee name |
| `LAST_NAME` | VARCHAR(25) | - | Surname |
| `SALARY` | INT | - | Annual/Monthly gross base salary |
| `JOINING_DATE` | DATETIME | - | Timestamp of onboarding |
| `DEPARTMENT` | VARCHAR(25) | - | Organizational unit placement |

### 2. Bonuses

| Column Name | Data Type | Key Type | Description |
| :--- | :--- | :--- | :--- |
| `WORKER_REF_ID` | INT | Foreign Key | References `Workers(WORKER_ID)` |
| `BONUS_AMOUNT` | INT | - | Distributed monetary reward amount |
| `BONUS_DATE` | DATETIME | - | Transaction processing timestamp |

### 3. Titles

| Column Name | Data Type | Key Type | Description |
| :--- | :--- | :--- | :--- |
| `WORKER_REF_ID` | INT | Foreign Key | References `Workers(WORKER_ID)` |
| `JOB_TITLE` | VARCHAR(25) | - | Position title (Manager, Executive, etc.) |
| `AFFECTED_FROM` | DATETIME | - | Effective start timestamp for title change |

## ⚙️ Optimization & Design Details
* **Constraints:** Enforces `NOT NULL` validations across names, dates, and keys.
* **Cascades:** Configured with `ON DELETE CASCADE` strategies to prevent orphan records.
* **Compatibility:** Fully compliant with standard SQL syntax environments (MySQL 8.0+, PostgreSQL, Oracle).
