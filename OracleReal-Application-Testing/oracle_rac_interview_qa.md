
---
layout: default
title: Oracle RAC Interview Q&A
---

# 🧠 Oracle RAC Interview Questions & Answers

A collection of advanced Oracle RAC interview questions with detailed answers, curated from 10+ years of hands-on experience in real-world enterprise environments.

---

## 📌 1. What is Oracle RAC, and why is it used?

**Answer:**  
Oracle RAC (Real Application Clusters) allows multiple Oracle instances to access a single database in a clustered environment. It provides high availability, scalability, and load balancing. RAC is essential for mission-critical systems where downtime is unacceptable.

---

## 📌 2. What are the components of Oracle RAC architecture?

**Answer:**

- **Oracle Clusterware** – Manages nodes and cluster resources.
- **Grid Infrastructure** – Includes Clusterware and ASM.
- **Oracle ASM** – Manages shared storage.
- **Private Interconnect** – High-speed communication between RAC nodes.
- **Global Cache Services (GCS)** and **Global Enqueue Services (GES)** – Maintain data consistency and cache coherency.

---

## 📌 3. What is the difference between RAC and Data Guard?

| Feature       | Oracle RAC                         | Oracle Data Guard                |
|---------------|-------------------------------------|----------------------------------|
| Purpose       | High Availability & Load Balancing | Disaster Recovery                |
| Nodes Access  | All nodes access the same DB       | Standby DB is read-only or inactive |
| Failover Type | Instance failover                  | Site-level failover              |

---

## 📌 4. How do you troubleshoot node eviction in RAC?

**Answer:**

- Check logs:
  - `$GRID_HOME/log/<host>/cssd/ocssd.log`
  - `$GRID_HOME/log/<host>/crsd/crsd.log`
  - `/var/log/messages`
- Common causes:
  - Interconnect failure
  - Disk I/O issues
  - Voting disk inaccessibility
- Tools:
  - `cluvfy`, `diagcollection.sh`, system monitoring

---

## 📌 5. What is split-brain and how is it prevented?

**Answer:**  
Split-brain occurs when RAC nodes lose communication but continue operating independently, risking data corruption. Oracle Clusterware prevents this via:

- Voting disks for node membership
- Private interconnect monitoring
- Disk-based heartbeat

---

## 📌 6. Explain cache fusion in Oracle RAC.

**Answer:**  
Cache fusion ensures data consistency between RAC instances by transferring data blocks over the private interconnect rather than reading from disk. GCS/GES coordinate the transfers, significantly reducing I/O and improving performance.

---

## 📌 7. Common RAC performance issues and resolution?

**Answer:**

- **gc buffer busy / gc cr request waits** → Tune SQL and reduce block contention
- **Interconnect bottlenecks** → Use 10GbE or higher, jumbo frames, bonded NICs
- **Load imbalance** → Configure services with preferred/available instances
- **ASM contention** → Spread disks and monitor with `asmcmd` and `v$asm_*` views

---

## 📌 8. How do you apply patches in Oracle RAC?

**Answer:**

1. Download and stage patch
2. Use `opatchauto apply` for rolling patching
3. Apply on one node at a time
4. Validate cluster and services post-patch

---

## 🙋‍♂️ About Me

I’m an OCP-certified Oracle DBA with 10+ years of experience in:

- RAC, Data Guard, ASM, GoldenGate
- Exadata, VLDB performance tuning
- Backup & Recovery (RMAN), OEM
- Shell scripting, PL/SQL
- Financial & telecom enterprise systems

🔗 [Visit my GitHub](https://github.com/db23ai)  
📧 db23ai@example.com

---

*This page is part of a professional portfolio and knowledge-sharing initiative for Oracle Database Engineers.*
