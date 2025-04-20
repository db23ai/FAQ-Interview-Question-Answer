
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

### 1. 🧑‍💼 Write a SQL query to find the second highest salary from an employee table.

```sql
SELECT MAX(salary) AS SecondHighest
FROM employees
WHERE salary < (SELECT MAX(salary) FROM employees);
```

---

### 2. 🐢 How would you optimize a query that’s running slow?

**Answer:**

- Analyze with **EXPLAIN PLAN**
- Add missing indexes
- Avoid `SELECT *`
- Rewrite subqueries with JOINs
- Use query caching or materialized views

---

### 3. ⚠️ What are some common performance bottlenecks in a database, and how would you address them?

**Answer:**

- Missing indexes → Add proper indexes
- Locking → Review transactions
- Poor schema design → Normalize or refactor
- Hardware limitations → Scale vertically/horizontally

---

### 4. 🔗 What are the differences between INNER JOIN, LEFT JOIN, and RIGHT JOIN?

**Answer:**

- **INNER JOIN**: Matches records in both tables
- **LEFT JOIN**: All from left + matching from right
- **RIGHT JOIN**: All from right + matching from left

---

### 5. 🧭 Explain what an execution plan is and how you would use it to optimize a query.

**Answer:**

An **execution plan** shows how the DB engine processes a query:

- View with `EXPLAIN` or tools like AWR, SQL Developer
- Check for full table scans, nested loops, index usage

Use it to find inefficient paths and refactor queries.

---

# 🛡️ Backup, Recovery, and Security

---

### 1. 🛑 How would you ensure data integrity and prevent data loss in a large-scale production environment?

**Answer:**

- Use constraints and transactions
- Implement regular backups
- Use replication and standby DBs
- Monitor logs and anomalies

---

### 2. 🌀 What strategies do you employ for disaster recovery (DR)?

**Answer:**

- Geo-redundant backups
- Real-time replication (e.g., Data Guard)
- Regular DR drills and runbooks
- RTO and RPO definitions

---

### 3. 💽 Describe your approach to implementing backup strategies for large, mission-critical databases.

**Answer:**

- Use full + incremental backups
- Schedule backups during off-peak hours
- Automate with tools like RMAN, pgBackRest
- Verify restore regularly

---

### 4. 🔐 How do you ensure database security, and what best practices do you follow for protecting sensitive data?

**Answer:**

- Use RBAC (Role-Based Access Control)
- Encrypt data at rest and in transit
- Audit access logs
- Apply regular patches
- Mask sensitive fields

---

# 🌐 High Availability & Scalability

---

### 1. 🧬 Explain replication and the different types of replication mechanisms (master-slave, peer-to-peer).

**Answer:**

- **Master-Slave**: One writes, others read.
- **Peer-to-Peer**: All nodes are equal; write conflicts must be managed.

Used for load balancing and DR.

---

### 2. 🆙 How do you ensure high availability in a production database environment?

**Answer:**

- Use clustering (Oracle RAC, Patroni)
- Load balancers
- Replication
- Failover mechanisms (automatic/manual)

---

### 3. ⚖️ What are the differences between sharding and partitioning in a distributed database system?

**Answer:**

- **Sharding**: Splits data across different servers.
- **Partitioning**: Splits data within a table, often on the same server.

Sharding improves horizontal scalability; partitioning optimizes queries on large tables.

---

### 4. 🔁 How would you handle database failover and ensure minimal downtime?

**Answer:**

- Use automated failover with health checks
- Synchronous replication for minimal data loss
- Test failover regularly
- Monitor and alert for failover events

---
