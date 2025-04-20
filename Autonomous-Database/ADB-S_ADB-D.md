# Oracle Autonomous Database

## General Information

## 📌 1. What is the Oracle Autonomous Database?
Oracle Autonomous Database is the world’s first autonomous data management in the cloud. It delivers automated patching, upgrades, and tuning—including performing all routine database maintenance tasks while the system is running—without human intervention. 

Key features:
- **Self-managing, self-securing, and self-repairing** to eliminate manual database management and human errors.
- Fully **elastic**: Scale ECPUs and storage up or down at any time.
- Supports the following workloads:
  - Transaction processing and mixed workloads
  - Analytics and data warehousing
  - Transactions and analytics on JSON data
  - APEX Application Development

[Learn more](https://www.oracle.com/database/autonomous-database/)

---

## 📌 2. What is the difference between Dedicated vs. Serverless deployments?
- **Serverless**: Oracle manages all underlying infrastructure while you provision and manage only the Autonomous Database.
- **Dedicated**: Provides a private cloud for a single tenant with dedicated compute, storage, network, and database services.

---

## 📌 3. Where is Oracle Autonomous Database available?
You can find the full list of data centers [here](https://www.oracle.com/cloud/data-regions.html).

---

### Tools, Applications, and Services Compatible with Oracle Autonomous Database
Autonomous Database supports tools and services certified for Oracle Database and many others. For a comprehensive list of supported tools, [click here](https://www.oracle.com/database/autonomous-database/).

---

## 📌 4. How can I learn more about Oracle Autonomous Database?
A wealth of resources are available to help you get started and be successful with Autonomous Database. [Learn more](https://www.oracle.com/database/autonomous-database/).

---

## Pricing and Licensing

## 📌 5. What is the price of Oracle Autonomous Database?
Pricing details can be found on the [Autonomous Data Warehouse (ADW)](https://www.oracle.com/database/autonomous-database/pricing.html) or [Autonomous Transaction Processing (ATP)](https://www.oracle.com/database/autonomous-database/pricing.html) pages.

---

## 📌 6. What are the provisioning options for Oracle Autonomous Database?
You can provision a **License-included** version or a **Bring-Your-Own-License (BYOL)** instance. The BYOL requirements for ATP and ADW are detailed on their respective pricing pages.

---

## 📌 7. Does Oracle Autonomous Database support per-second billing?
Yes, ADB supports per-second billing with certain restrictions. More details [here](https://www.oracle.com/database/autonomous-database/pricing.html).

---

## 📌 8. Can auto-scaling help reduce my bills?
Yes. Auto-scaling allows ADB to automatically scale resources in real-time, only charging for actual usage. More information is available [here](https://www.oracle.com/database/autonomous-database/).

---

## 📌 9. Does ADB offer trial licenses?
Yes, ADB offers 30-day free trials. [Sign up here](https://www.oracle.com/database/autonomous-database/).

---

## Security

## 📌 10. Can a customer manage their own encryption keys?
Yes, you can manage your own encryption keys. More details [here](https://www.oracle.com/database/autonomous-database/security.html).

---

## 📌 11. How does Oracle Autonomous Database provide data security?
- **Encryption**: All data is encrypted at rest.
- **Security Updates**: Oracle applies security updates automatically.
- **In-database features**: Database Vault, Virtual Private Database, and Data Redaction are available.

---

## 📌 12. Is data redaction available with Oracle Autonomous Database?
Yes, data redaction is supported.

---

## 📌 13. Is it possible to leverage Database Vault with Oracle Autonomous Database?
Yes, Database Vault is available, and can be combined with Oracle Data Safe for a comprehensive security layer. [More information](https://www.oracle.com/database/autonomous-database/security.html).

---

## Availability

## 📌 14. What is the current availability SLA for Oracle Autonomous Database?
The SLA for ADB is 99.95% availability. Higher availability levels (99.995%) can be achieved with **Autonomous Data Guard**.

---

## 📌 15. Does Oracle Autonomous Database have a standby feature?
Yes, **Autonomous Data Guard** enables a standby instance with automated failover protection. [Learn more about ADW](https://www.oracle.com/database/autonomous-database/data-guard.html).

---

## 📌 16. What happens if Oracle Autonomous Database is down?
Oracle is responsible for getting the service back online as quickly as possible. For disaster recovery, use **Autonomous Data Guard**.

---

## Connecting to Oracle Autonomous Database

## 📌 17. Does ADB provide a web-based tool for end users?
Yes, **Database Actions** is a built-in toolkit for development, administration, and monitoring.

[More information](https://www.oracle.com/database/autonomous-database/tools.html)

---

## 📌 18. Does ADB support VPN and/or FastConnect?
Yes, you can connect your on-premises network to ADB using VPN or FastConnect.

---

## 📌 19. Does Oracle Autonomous Database support access to non-Oracle Databases?
Yes, ADB supports connectivity to various non-Oracle databases like PostgreSQL, Amazon Redshift, Snowflake, MySQL, etc.

---

## Loading Data

## 📌 20. What are the options for loading data into Oracle Autonomous Database?
- **Object Storage Integration**: Upload files to supported object stores like Oracle Object Storage, AWS S3, and Azure Blob Storage.
- **Data Pump**: Use Data Pump to load data from dump files stored in object storage.
- **Other Tools**: SQL*Loader, GoldenGate, and third-party ETL tools can also be used.

---

## 📌 21. What types of data files are supported for loading?
- **Local Files**: AVRO, CSV, JSON, TSV, delimited TXT, XLS, XLSX, XML.
- **Cloud Storage**: AVRO, CSV, JSON, Parquet, ORC, delimited TXT.

---

## 📌 22. Does Oracle Autonomous Database support access to Data Lakes?
Yes, ADB can synchronize metadata with **OCI Data Catalog** to support data governance and discovery. [Learn more](https://www.oracle.com/database/autonomous-database/data-lake.html).

---

### Schema Design and Querying

## 📌 23. Does ADB automatically create and manage indexes?
Yes, ADB can automatically create indexes, but auto-indexing is not enabled by default.

---

## 📌 24. Can ADB automatically manage partitioning strategies?
Yes, ADB supports auto-partitioning, but it is not enabled by default.

---

## Performance

## 📌 25. How does Oracle Autonomous Database isolate customer workloads for performance?
ADB uses **Database Resource Manager** and **IO Resource Manager** to ensure that each customer gets dedicated CPU, memory, and IO resources without over-provisioning, ensuring predictable performance.

---

## Migration

## 📌 26. How can I migrate my existing Oracle Database to Oracle Autonomous Database?
Use **Data Pump** for schema migration. For real-time sync, Oracle **GoldenGate** can replicate changes. Learn more about migration [here](https://www.oracle.com/database/autonomous-database/migration.html).

---

## 📌 27. Does Autonomous Database offer a pre-migration check tool?
Yes, the **Cloud Premigration Advisor Tool (CPAT)** helps analyze Oracle Database schemas to ensure a smooth migration to ADB.

---

## Managing and Monitoring

## 📌 28. Is there an option to delay or reschedule patches?
With **Serverless** deployments, patches occur automatically within predefined maintenance windows. With **Dedicated** deployments, you can manage maintenance schedules.

---

## 📌 29. Can I access the database server's operating system?
No, ADB does not provide OS-level access.

---

## Additional Resources
- [Oracle Autonomous Database Documentation](https://docs.oracle.com/en/database/autonomous-database/)
- [Oracle Autonomous Database on GitHub](https://github.com/oracle)

---

### Disclaimer
This document is for educational purposes only. Please refer to the official Oracle documentation for detailed and up-to-date information.
