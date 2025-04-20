# Oracle Autonomous Database on Exadata Cloud@Customer (ADB-ExaC@C)

## Overview

### What is Autonomous Database on Exadata Cloud@Customer (ADB-ExaC@C)?
**Autonomous Database on Exadata Cloud@Customer (ADB-ExaC@C)** is the same **Autonomous Database Dedicated** cloud service but running on **Exadata Cloud@Customer** infrastructure for **on-premises deployment**. 

It allows customers to leverage Oracle’s **Autonomous Database** capabilities while keeping the infrastructure within their own data centers. This solution is ideal for customers who cannot use the public cloud due to:
- Data sovereignty laws
- Industry regulations
- Corporate policies
- Network latency and security requirements
- On-premises applications that are tightly coupled with local databases

ADB-ExaC@C provides the same features as **ADB Dedicated** on Oracle Cloud Infrastructure (OCI), with the added flexibility of deployment in the customer’s data center.

---

## Key Differences Between ADB on OCI and ADB on Exadata Cloud@Customer

While **Autonomous Database Dedicated** on both **OCI** and **Exadata Cloud@Customer** provide the same core service, there are some differences:

### **1. Network Configuration**
- **OCI**: Customers configure networking via **VCN**.
- **ExaC@C**: Requires setting up connectivity to the **cloud control plane** and defining **Exadata system primary** and **client networks**. This process is validated on-site by an **Oracle field engineer**.

### **2. Backup Locations**
- **OCI**: Only **Object Storage** is supported for backups.
- **ExaC@C**: Customers can back up to **object storage**, **local Exadata storage**, **customer-managed NFS**, or **ZDLRA (Zero Data Loss Recovery Appliance)**.

---

## Operational Management

### Who is Responsible for Backup and Restore on Exadata Cloud@Customer?
- **Oracle** manages backup and restore operations using **object storage** and **local Exadata storage**.
- **Customer** is responsible for backup and restore using **customer-managed storage** (e.g., **NFS** or **ZDLRA**).

### Who is Responsible for Patching on Exadata Cloud@Customer?
- **Oracle** manages patching for both **Exadata infrastructure** and **user databases**.
- Customers can **override the default patching schedule** with their preferred patching timeline.

### Can I Run Both Exadata Database and Autonomous Database on Exadata Cloud@Customer?
- In the **first release**, customers must choose whether an **ExaC@C rack** is for **Autonomous Database** or **Exadata Database**.
- Supporting a **mix** of both on the same rack is a roadmap item for **CY 2021**.

---

## Architecture and Scalability

### Exadata Infrastructure Supported for ADB Dedicated on OCI
- **Exadata X8** and **X7** Quarter, Half, and Full Racks are supported.

### Exadata Infrastructure Supported for ADB on Exadata Cloud@Customer
- **Gen 2 Exadata Cloud@Customer** Quarter, Half, and Full Racks are supported.
- **Note**: ADB is not available on **Base System** or **Gen 1 Exadata Cloud@Customer Infrastructure**.

### How Many OCPUs Are Available for ADB-D on an X8 Quarter Rack?
- An **Exadata X8 Quarter Rack** has **100 enabled CPU cores**.
- It supports up to **100 Autonomous Databases** with **1 database per OCPU core**.

### How Many Autonomous Container Databases (ACDs) and Autonomous Databases Are Supported on ADB Dedicated?
- **Quarter Rack**: Up to **100 Autonomous Databases** per **Autonomous Container Database**.
- **Half and Full Rack**: Up to **12 Autonomous Container Databases**, with a maximum of **200 Autonomous Databases** per container.

---

## Managing and Monitoring

### What is the Role of a Fleet Administrator in ADB Dedicated?
- A **Fleet Administrator** manages **Autonomous Exadata Infrastructure (AEI)** and **Autonomous Container Database (ACD)** resources.
- On Exadata Cloud@Customer, the fleet administrator is also responsible for managing **Backup Destinations** and **Autonomous Exadata VM Clusters**.
- The role is materialized via **IAM privileges** granted to a **Fleet Administrator Group**.

### What is the Role of a Database Administrator in ADB Dedicated?
- A **Database Administrator** manages **Autonomous Databases**, including:
  - Creation
  - Monitoring
  - Management of schema and user access
- **IAM privileges** are used to assign database administrator rights.

### Can I Use Enterprise Manager to Monitor ADB Dedicated Instances?
Yes, **Enterprise Manager (EM 13.3+)** can be used to monitor both **ADB Dedicated on OCI** and **Autonomous Database on Exadata Cloud@Customer**.
- **On-prem EM** or the **OCI Marketplace EM 13c Image** can be used for monitoring.
- For more information, refer to the **EM Cloud Control Administrator’s Guide**.

---

## Pricing and Licensing

### How is ADB Dedicated Priced?
There are two main components of pricing:
1. **Infrastructure**: Subscription for **Exadata Cloud Infrastructure** (OCI or Exadata Cloud@Customer).
2. **Database OCPUs**: Subscription based on the **hourly consumption of active OCPUs** (using either **License Included** or **BYOL**).

- For **OCI pricing**, refer to the [Autonomous Database pricing pages](https://www.oracle.com/database/autonomous-database/).
- For **Exadata Cloud@Customer pricing**, refer to the [Exadata Cloud@Customer pricing page](https://www.oracle.com/cloud/exadata-cloud-customer.html).

### Where is the Database License Type Defined on ADB Dedicated?
- On **OCI**, the license type is defined at the **Exadata Infrastructure** level.
- On **Exadata Cloud@Customer**, it is defined at the **Autonomous VM Cluster** level.
- Currently, only one license type (**License Included** or **BYOL**) is allowed per **Exadata rack** until **multiple VM clusters per rack** are supported.

---

## Additional Resources
- [Autonomous Database on Exadata Cloud@Customer Documentation](https://www.oracle.com/database/autonomous-database-on-exadata-cloud-at-customer.html)
- [Exadata Cloud@Customer Overview](https://www.oracle.com/cloud/exadata-cloud-customer.html)
