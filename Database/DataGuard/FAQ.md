# 📘 Oracle Data Guard – Interview Questions & Answers

### 1. What is Oracle Data Guard?

Oracle Data Guard is a disaster recovery and high availability solution that maintains standby copies (physical or logical) of a production database. It ensures data integrity and enables failover if the primary database becomes unavailable.

---

### 2. What are the components of Oracle Data Guard?

- **Primary Database**
- **Standby Database** (Physical, Logical, Snapshot, or Far Sync)
- **Redo Transport Services**
- **Log Apply Services**
- **Data Guard Broker** (optional management tool)

---

### 3. Difference: Physical vs Logical Standby

| Feature    | Physical Standby      | Logical Standby       |
|------------|----------------------|-----------------------|
| Structure  | Exact replica        | Can differ structurally |
| Apply Method | Redo Apply         | SQL Apply             |
| Usage      | Best for DR          | Used for reporting/BI |
| Performance| Higher               | Lower                 |

---

### 4. What are the Data Guard Protection Modes?

- **Maximum Protection** – Zero data loss, commit only when standby confirms.
- **Maximum Availability** – Zero loss unless standby unavailable.
- **Maximum Performance** – Minimal impact, allows potential data loss.

---

### 5. How to configure Data Guard?

1. Setup TNS and listener
2. Enable `FORCE LOGGING` on primary
3. Create standby control file
4. Duplicate using RMAN
5. Configure log shipping and parameters:
   - `LOG_ARCHIVE_DEST_n`
   - `FAL_SERVER`
   - `FAL_CLIENT`

---

## 🔹 Intermediate Level

### 6. What is a Far Sync Instance?

A Far Sync instance receives redo from the primary and forwards it to standbys. It has no datafiles or apply services—just used for transport.

---

### 7. Purpose of `FAL_SERVER` and `FAL_CLIENT`?

- **FAL_SERVER** – Location to fetch missing logs (usually primary).
- **FAL_CLIENT** – Identity of the requesting database (usually standby).

---

### 8. Monitoring Data Guard

```sql
-- Database role
SELECT DATABASE_ROLE FROM V$DATABASE;

-- Managed recovery processes
SELECT PROCESS, STATUS FROM V$MANAGED_STANDBY;

-- Archive destination errors
SELECT DEST_ID, ERROR FROM V$ARCHIVE_DEST_STATUS;
