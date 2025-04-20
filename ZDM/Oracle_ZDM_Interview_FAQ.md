
# 📦 Oracle Zero Downtime Migration (ZDM) – FAQ

**Oracle Zero Downtime Migration (ZDM)** is an automated Oracle tool designed to simplify and automate Oracle database migrations with minimal or zero downtime, leveraging **Oracle Maximum Availability Architecture (MAA)** best practices.

Below are frequently asked interview questions and answers based on the latest Oracle documentation and expert experience.

---

## 📌 1. What is Oracle Zero Downtime Migration (ZDM)?

**Answer:**  
Oracle ZDM is an automated migration solution that enables seamless database migrations from on-premises or cloud environments to Oracle Cloud, or between Oracle infrastructures, with minimal to zero downtime.  
It orchestrates the entire migration process, reducing human error and ensuring high availability by integrating:

- Oracle Data Guard  
- Oracle GoldenGate  
- RMAN (Recovery Manager)  
- Oracle Data Pump  

---

## 📌 2. What are the main components and technologies used by ZDM?

**Answer:**

- **Oracle Data Guard** – Physical standby creation and synchronization.  
- **Oracle GoldenGate** – Real-time replication for logical migrations.  
- **RMAN** – Backup and restore operations.  
- **Data Pump** – Logical export/import migrations.  
- **Database Links & Object Storage** – For data transfer and connectivity.  
- **ZDM Service Host** – Dedicated Linux server to orchestrate the migration.

---

## 📌 3. What types of migration workflows does Oracle ZDM support?

**Answer:**

- **Physical Migration Workflow** – Uses Data Guard to create a standby, sync data, and switch over with minimal downtime.  
- **Logical Migration Workflow** – Uses GoldenGate with Data Pump for migrations like to Autonomous DB where physical standby isn’t applicable.

---

## 📌 4. What are the high-level steps in a ZDM Physical Migration?

**Answer:**

1. Install and configure the ZDM service.  
2. Start the migration job.  
3. Connect the source DB to Object Store.  
4. Transfer backup files to target.  
5. Instantiate standby DB on the target.  
6. Sync primary and standby DBs.  
7. Perform switchover.  
8. Finalize and clean up.

---

## 📌 5. What are the prerequisites for using Oracle ZDM?

**Answer:**

- Source and target DBs must be same Oracle version (11.2.0.4+).  
- Source DB must be in **ARCHIVELOG** mode.  
- **TDE wallet** (if used) must be configured and open.  
- A separate Linux host must be used for ZDM with required packages.  
- Network connectivity (VPN, ExpressRoute, etc.) between all nodes.  
- Proper **SSH keys** and DB access permissions.

---

## 📌 6. How does ZDM ensure zero downtime during migration?

**Answer:**  
ZDM uses Data Guard or GoldenGate for continuous data replication, keeping source and target in sync.  
The final cutover (switchover) is quick, reducing downtime to seconds, ensuring service continuity.

---

## 📌 7. How is security handled during ZDM migrations?

**Answer:**

- Transparent Data Encryption (TDE) for data-at-rest.  
- Secure networks using VCN/Subnet rules, NSGs, or firewalls.  
- Encrypted communication via **SSH** and **TLS**.  
- Follow Oracle **MAA security best practices**.

---

## 📌 8. What are the differences between Oracle ZDM and Oracle GoldenGate?

**Answer:**

| Feature | Oracle ZDM | Oracle GoldenGate |
|--------|-------------|-------------------|
| Type | Orchestration Tool | Replication Engine |
| Usage | End-to-end automation | Real-time replication |
| Scope | Uses RMAN, GG, Data Guard, Data Pump | Data-level replication |
| Integration | Fully automated | Can be used standalone or with ZDM |

---

## 📌 9. Can ZDM migrate RAC databases?

**Answer:**  
Yes, ZDM supports:

- Single Instance DBs  
- RAC (Real Application Clusters)  
- RAC One Node  

It can migrate to either **similar RAC** or **single instance** targets using MAA practices.

---

## 📌 10. What platforms and targets does Oracle ZDM support?

**Answer:**

- **Source**: On-premises or any cloud  
- **Target**:
  - Oracle Cloud Infrastructure (OCI)
  - Exadata Cloud Service / Exadata Cloud@Customer
  - Autonomous Database
  - Oracle DB@Azure / @Google Cloud / @AWS

---
## 📌 11. How to find Oracle ZDM Whitepaper or technical brief?

**Answer:**

You can use several official Oracle channels and search strategies. Oracle Official Documentation & Tech Briefs :


  - https://www.oracle.com/a/ocom/docs/oracle-zdm-technical-brief.pdf
  - Cloud Premigration Advisor Tool (CPAT) Analyzes Databases for Suitability of Cloud Migration (Doc ID 2758371.1) - Oracle Support (MOS) (requires account): https://support.oracle.com/
  - https://docs.oracle.com/en/database/oracle/zero-downtime-migration/21.1/zdmug/move-oracle-cloud-using-zero-downtime-migration.pdf
  - [Oracle Zero Downtime Migration](https://www.oracle.com/database/technologies/rac/zdm.html)


---
