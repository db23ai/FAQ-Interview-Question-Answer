# Oracle Autonomous Database Serverless

## Overview

### What is Autonomous Database Serverless?
Oracle **Autonomous Database Serverless** is a fully-managed, elastic database optimized for various workloads, such as:
- **Data Warehousing and Analytics**
- **Transactional/Mixed Workloads**
- **APEX (Application Express)**
- **JSON**

With **serverless infrastructure**, Oracle autonomously handles all aspects of the database lifecycle, from database placement to backup and updates. The database automatically scales based on demand, providing a fully elastic experience with no manual intervention needed.

[Learn more about Autonomous Database](https://www.oracle.com/database/autonomous-database/)

---

## Technical Support and Forums

### Is there a technical forum for Autonomous Database?
Yes, Oracle uses [Stack Overflow](https://stackoverflow.com) for technical questions about Autonomous Database. When posting a question, please use the tag `oracle-autonomous-db`.

---

### Is it possible to construct a TCO (Total Cost of Ownership) report for Autonomous Database Serverless?
Yes, Oracle provides a **TCO report builder** for **Autonomous Database Serverless for Data Warehousing**. This tool helps you calculate the value of automation and estimate savings. 

[Try the TCO report builder](https://www.oracle.com/database/autonomous-database/tco-report.html)

---

## Architecture

### How does Autonomous Database Serverless configure parallelism?
Autonomous Database Serverless comes with five preconfigured database services:
- **HIGH**
- **MEDIUM**
- **LOW**
- **TP** (Transaction Processing)
- **TPURGENT**

These services manage session priorities and parallel execution:
- **HIGH** and **MEDIUM** services automatically execute queries in parallel.
- **TP**, **TPURGENT**, and **LOW** services run queries serially by default but allow users to specify parallel degrees using optimizer hints.

Parallelism is automatically configured based on the number of CPUs you provision, so no explicit configuration is needed.

---

### Is the Database In-Memory option available in Autonomous Database Serverless?
Yes, **Database In-Memory** is available and can be used to optimize performance in Autonomous Database. 

[Learn more about Database In-Memory](https://www.oracle.com/database/database-in-memory.html)

---

## Migration

### Can non-Oracle databases be migrated to Autonomous Database Serverless?
Yes, Oracle **SQL Developer** provides migration wizards to migrate data from non-Oracle databases such as:
- **AWS Redshift**
- **MySQL**
- **Microsoft SQL Server**
- **Sybase Adaptive Server**
- **IBM DB2 (UDB)**

These wizards export the metadata and data from the source database and import them into Autonomous Database. You can also save migration scripts for running outside of SQL Developer.

[Learn more about migrating non-Oracle databases](https://www.oracle.com/database/autonomous-database/migration.html)

---

## Pricing and Licensing

### Can I reuse my existing Oracle Database licenses with Autonomous Database?
Yes, you can bring your existing Oracle Database licenses to Autonomous Database under the **Bring Your Own License (BYOL)** model.

[Learn more about BYOL and pricing](https://www.oracle.com/database/autonomous-database/pricing.html)

---

### Can I use the machine learning features in Autonomous Database Serverless with BYOL if I haven't licensed Oracle Advanced Analytics?
Yes, **Oracle Advanced Analytics** licenses are not required to use machine learning features in Autonomous Database when using the BYOL option.

---

### Can I use the in-database spatial and graph features in Autonomous Database Serverless with BYOL if I haven't licensed Oracle Spatial and Graph?
Yes, **Oracle Spatial and Graph** licenses are not required for the BYOL option.

---

### Can I use the in-memory features of Autonomous Database Serverless with BYOL if I haven't licensed the in-memory option?
Yes, **Oracle Database In-Memory** is available for use under BYOL without requiring a separate license.

---

## Additional Resources
- [Oracle Autonomous Database Documentation](https://docs.oracle.com/en/database/autonomous-database/)
- [Oracle Autonomous Database on GitHub](https://github.com/oracle)

