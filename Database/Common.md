
# 🏗️ Database Design & Management

---

### 1. 🔄 Explain database normalization and denormalization. When would you use each?

**Answer:**

- **Normalization** involves organizing data to reduce redundancy. Common forms include 1NF, 2NF, and 3NF.
  - Used in OLTP systems for data integrity and efficient updates.
- **Denormalization** is combining tables to improve read performance.
  - Used in reporting systems or read-heavy applications.

---

### 2. 📂 What is the difference between clustered and non-clustered indexes?

**Answer:**

- **Clustered Index** determines the physical order of data in the table.
- **Non-Clustered Index** is a separate structure that refers to the data location.

One table can have one clustered index but multiple non-clustered indexes.

---

### 3. 🛒 How would you design a database schema for a new application (e.g., an e-commerce site)?

**Answer:**

- Identify entities: Users, Products, Orders, Payments.
- Use ER diagrams.
- Normalize up to 3NF.
- Define foreign key relationships.
- Include indexing for frequently accessed fields.

---

### 4. 🔐 What are ACID properties? Explain with examples.

**Answer:**

- **Atomicity** – All steps of a transaction complete or none (e.g., bank transfer).
- **Consistency** – Database remains in valid state before and after transaction.
- **Isolation** – Concurrent transactions don’t interfere with each other.
- **Durability** – Once committed, changes persist even after failure.

---

### 5. 📈 How do you handle large amounts of data in a database? What techniques do you use for scalability and performance?

**Answer:**

- Indexing
- Partitioning
- Archiving old data
- Query optimization
- Caching with Redis or Memcached
- Vertical and horizontal scaling

---

### 6. 🔑 What is a composite key, and how does it differ from a primary key?

**Answer:**

- **Primary Key**: Unique identifier for a record.
- **Composite Key**: A combination of two or more columns to uniquely identify a record.

---

### 7. 🌱 How would you manage relationships in a database that could grow exponentially in the future?

**Answer:**

- Use indexing on foreign keys
- Implement cascading constraints carefully
- Consider NoSQL or distributed databases if relational performance becomes a bottleneck
- Archive historical data

---

### 8. 🧩 Explain partitioning in databases. What types of partitioning exist, and when would you use each type?

**Answer:**

- **Range Partitioning**: Based on ranges of values (e.g., date)
- **List Partitioning**: Based on predefined lists
- **Hash Partitioning**: Distributes data evenly
- **Composite Partitioning**: Combines two or more partitioning strategies

Used for large tables to improve query performance and manageability.

---

# 🧮 SQL & Query Optimization

---

### 9. 🧑‍💼 Write a SQL query to find the second highest salary from an employee table.

```sql
SELECT MAX(salary) AS SecondHighest
FROM employees
WHERE salary < (SELECT MAX(salary) FROM employees);
```

---

### 10. 🐢 How would you optimize a query that’s running slow?

**Answer:**

- Analyze with **EXPLAIN PLAN**
- Add missing indexes
- Avoid `SELECT *`
- Rewrite subqueries with JOINs
- Use query caching or materialized views

---

### 11. ⚠️ What are some common performance bottlenecks in a database, and how would you address them?

**Answer:**

- Missing indexes → Add proper indexes
- Locking → Review transactions
- Poor schema design → Normalize or refactor
- Hardware limitations → Scale vertically/horizontally

---

### 12. 🔗 What are the differences between INNER JOIN, LEFT JOIN, and RIGHT JOIN?

**Answer:**

- **INNER JOIN**: Matches records in both tables
- **LEFT JOIN**: All from left + matching from right
- **RIGHT JOIN**: All from right + matching from left

---

### 13. 🧭 Explain what an execution plan is and how you would use it to optimize a query.

**Answer:**

An **execution plan** shows how the DB engine processes a query:

- View with `EXPLAIN` or tools like AWR, SQL Developer
- Check for full table scans, nested loops, index usage

Use it to find inefficient paths and refactor queries.

---

# 🛡️ Backup, Recovery, and Security

---

### 14. 🛑 How would you ensure data integrity and prevent data loss in a large-scale production environment?

**Answer:**

- Use constraints and transactions
- Implement regular backups
- Use replication and standby DBs
- Monitor logs and anomalies

---

### 15. 🌀 What strategies do you employ for disaster recovery (DR)?

**Answer:**

- Geo-redundant backups
- Real-time replication (e.g., Data Guard)
- Regular DR drills and runbooks
- RTO and RPO definitions

---

### 16. 💽 Describe your approach to implementing backup strategies for large, mission-critical databases.

**Answer:**

- Use full + incremental backups
- Schedule backups during off-peak hours
- Automate with tools like RMAN, pgBackRest
- Verify restore regularly

---

### 17. 🔐 How do you ensure database security, and what best practices do you follow for protecting sensitive data?

**Answer:**

- Use RBAC (Role-Based Access Control)
- Encrypt data at rest and in transit
- Audit access logs
- Apply regular patches
- Mask sensitive fields

---

# 🌐 High Availability & Scalability

---

### 18. 🧬 Explain replication and the different types of replication mechanisms (master-slave, peer-to-peer).

**Answer:**

- **Master-Slave**: One writes, others read.
- **Peer-to-Peer**: All nodes are equal; write conflicts must be managed.

Used for load balancing and DR.

---

### 19. 🆙 How do you ensure high availability in a production database environment?

**Answer:**

- Use clustering (Oracle RAC, Patroni)
- Load balancers
- Replication
- Failover mechanisms (automatic/manual)

---

### 20. ⚖️ What are the differences between sharding and partitioning in a distributed database system?

**Answer:**

- **Sharding**: Splits data across different servers.
- **Partitioning**: Splits data within a table, often on the same server.

Sharding improves horizontal scalability; partitioning optimizes queries on large tables.

---

### 21. 🔁 How would you handle database failover and ensure minimal downtime?

**Answer:**

- Use automated failover with health checks
- Synchronous replication for minimal data loss
- Test failover regularly
- Monitor and alert for failover events

---

# 🏛️ Oracle DBA Interview Q&A

A compilation of essential Oracle DBA concepts and troubleshooting techniques frequently asked in interviews and practical scenarios.

---

## 🧠 Oracle Core Concepts

### 22. What is a Checkpoint and When Does It Occur?
A **checkpoint** flushes dirty buffers from memory to disk and updates datafile headers with the latest SCN. It occurs during:
- Log switches
- Database shutdowns
- Based on parameters like `LOG_CHECKPOINT_INTERVAL` and `LOG_CHECKPOINT_TIMEOUT`

### 23. Benefits of ASM (Automatic Storage Management)
- Automatic striping and mirroring
- Simplified storage management
- Online disk rebalancing
- Improved I/O performance
- Easy scalability

### 24. How Rebalancing Works in ASM
- Triggered when disks are added/removed
- Managed by background processes:
  - `RBAL` (Rebalance Coordinator)
  - `ARBn` (Rebalance Slaves)

### 25. How to Replace an Existing Disk in ASM
- Add new disk: `ALTER DISKGROUP dgname ADD DISK ...`
- Drop old disk: `ALTER DISKGROUP dgname DROP DISK ...`
- ASM will automatically rebalance data

---

## ⚙️ Oracle RAC (Real Application Clusters)

### 26. RAC Architecture and Background Processes
- Shared database with multiple instances
- Each instance has its own SGA
- Key background processes:
  - `LMD`, `LMS`, `LMON`, `LCK`

### 27. Cache Fusion
Allows data blocks to be transferred between instances via interconnect without disk I/O, maintaining consistency.

### 28. Scalability Features of RAC
- Add nodes to scale horizontally
- Load balancing via services
- High availability and fault tolerance
- Distributed workload across instances

---

## 💾 Backup & Disaster Recovery

### 29. RMAN and Its New Features
- Block change tracking
- Data Recovery Advisor
- Cloud backup support
- Duplicate database with minimal effort

---

## 🔁 Data Guard

### 30. Difference Between Physical and Logical Standby
- **Physical Standby**: Redo Apply, block-for-block replica
- **Logical Standby**: SQL Apply, allows data manipulation and reporting

### 31. How Logical Standby Converts Archive to SQL
- Uses **LogMiner** to transform redo into SQL
- Applied via **Logical Standby Process (LSP)**

### 32. Difference Between Max Performance and Max Availability
- **Max Performance**: Async redo, best performance
- **Max Availability**: Sync redo, minimal/no data loss

### 33. Sync, Async, Affirm, NoAffirm
- **SYNC**: Redo written and acknowledged
- **ASYNC**: Redo sent but not waited for acknowledgment
- **AFFIRM**: Confirmation needed from standby
- **NOAFFIRM**: No confirmation from standby

---

## 🧱 Performance Tuning & Troubleshooting

### 34. What is ITL Blocking?
Occurs when all ITL (Interested Transaction List) slots are occupied, blocking new transactions until one is released.

### 35. What is a Histogram?
Describes the distribution of column values to help the optimizer choose efficient query plans.

### 36. How to Troubleshoot Slowness and Long-Running Queries
- Analyze AWR/ASH reports
- Review execution plans
- Monitor wait events and locks

### 37. How to Read an AWR Report
- Focus on Top SQL, Wait Events, Load Profile
- Compare snapshots to identify spikes or regressions

### 38. Slowness Today, But Was Fast Yesterday 5–6PM – Troubleshooting Approach
- Compare AWR snapshots between both time periods
- Check execution plans, locking, stats changes
- Monitor system resources

### 39. How Query Plan Changes, and How to Fix It
- Caused by stats change, bind peeking, adaptive plans
- Use SQL Plan Baselines or SQL Profiles to lock the plan

---

## 📊 Statistics & Monitoring

### 40. How to Gather Stats for Specific Partitions

```sql
BEGIN
  DBMS_STATS.GATHER_TABLE_STATS(
    ownname => 'SCHEMA',
    tabname => 'TABLE_NAME',
    partname => 'PARTITION_NAME'
  );
END;

