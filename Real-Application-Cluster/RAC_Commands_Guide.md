
# **RAC Commands Quick Guide**

**By:** SARAVANAKUMAR K  
[Blog](https://skumar22k.blogspot.com/)  
[LinkedIn](https://www.linkedin.com/in/saravanakumar-k-87768914/)

---

## :book: **Table of Contents**

- [Clusterware Utilities](#clusterware-utilities)
- [Checking Resource Status](#checking-resource-status)
- [Starting and Stopping the Cluster and OHAS Locally and Remotely (as root)](#starting-and-stopping-the-cluster-and-ohas-locally-and-remotely-as-root)
- [Enabling or Disabling Cluster Resource Auto-Start](#enabling-or-disabling-cluster-resource-auto-start)
- [CRS Log and Its Use](#crs-log-and-its-use)
- [Oracle Clusterware Configuration Files](#oracle-clusterware-configuration-files)
- [OCR Backup and Maintenance](#ocr-backup-and-maintenance)
- [Voting Disk Management](#voting-disk-management)
- [OLR Location, Data, Export and Import](#olr-location-data-export-and-import)
- [SCAN Configuration Information](#scan-configuration-information)
- [Cluster Database Start and Stop](#cluster-database-start-and-stop)
- [Cluster Instances Start and Stop](#cluster-instances-start-and-stop)
- [ASM Start, Stop, Status, and Configuration](#asm-start-stop-status-and-configuration)
- [Nodeapps Start, Stop, Status, and Configuration](#nodeapps-start-stop-status-and-configuration)
- [Network Interface Configuration – List, Get, Set and Delete](#network-interface-configuration--list-get-set-and-delete)
- [Cluster Node Information](#cluster-node-information)
- [Database Service Start and Stop, Add, Modify, Relocate and Remove](#database-service-start-and-stop-add-modify-relocate-and-remove)
- [Miscellaneous Commands](#miscellaneous-commands)

---

## :zap: **Clusterware Utilities**

- **`crsctl`**: Manage cluster
- **`srvctl`**: Managing cluster resources
- **`ocrconfig`**: Configuration tool for Oracle Cluster/Local Registry to Manage OCR
- **`ocrcheck`**: Displays health of Oracle Cluster/Local Registry and troubleshoot OCR
- **`ocrdump`**: Dump contents of Oracle Cluster/Local Registry to a file
- **`oifcfg`**: Oracle Interface Configuration Tool to manage network interfaces
- **`olsnodes`**: Find node information

---

## :bar_chart: **Checking Resource Status**

This process involves verifying the current status of a resource to ensure it is functioning properly.

```bash
crsctl stat res -t
```

---

## :rocket: **Starting and Stopping the Cluster and OHAS Locally and Remotely (as root)**

Cluster services can be managed locally or remotely by the root user.

```bash
crsctl start cluster
crsctl start cluster -n srv1
crsctl start cluster -all
crsctl start crs
```

---

## :gear: **Enabling or Disabling Cluster Resource Auto-Start**

Control whether a cluster resource starts automatically during server reboot.

```bash
crsctl enable crs
crsctl disable crs
```

---

## :clipboard: **CRS Log and Its Use**

CRS logs are critical for diagnosing issues related to Oracle Clusterware.

```bash
crsctl stat res -t -init
```

---

## :file_folder: **Oracle Clusterware Configuration Files**

Verify the integrity and location of critical configuration files like OCR.

```bash
ocrcheck
```

---

## :calendar: **OCR Backup and Maintenance**

Backup OCR to ensure you can recover in case of corruption or failure.

```bash
ocrconfig -showbackup
ocrconfig -manualbackup
```

---

## :shield: **Voting Disk Management**

Voting disks ensure proper node membership and quorum in the cluster.

```bash
crsctl replace votedisk +DATADG02
```

---

## :clipboard: **OLR Location, Data, Export and Import**

OLR stores Oracle RAC cluster configuration and is crucial for cluster operations.

```bash
ocrconfig -local -export <file_name>
```

---

## :arrows_counterclockwise: **SCAN Configuration Information**

SCAN (Single Client Access Name) simplifies client connections by using a single network name for Oracle RAC.

```bash
crsctl query css votedisk
```

---

## :file_cabinet: **Cluster Database Start and Stop**

Commands to start and stop the Oracle RAC database.

```bash
srvctl start database -d rac -startoption nomount
srvctl stop database -d rac -stopoption immediate
```

---

## :stopwatch: **Cluster Instances Start and Stop**

Start and stop instances in an Oracle RAC environment.

```bash
srvctl start instance -d rac -i rac1
```

---

## :floppy_disk: **ASM Start, Stop, Status, and Configuration**

ASM manages storage for Oracle RAC.

```bash
srvctl start asm -n srv1
```

---

## :cloud: **Nodeapps Start, Stop, Status, and Configuration**

Nodeapps are crucial Oracle RAC components such as VIP, GSD, Listener, and ONS.

```bash
srvctl start nodeapps
```

---

## :network: **Network Interface Configuration – List, Get, Set and Delete**

Use `oifcfg` to manage Oracle RAC network interfaces.

```bash
oifcfg setif -global eth1/10.0.0.0:cluster_interconnect
```

---

## :gear: **Cluster Node Information**

Display information about cluster nodes using `olsnodes`.

```bash
olsnodes -n -i -s
```

---

## :repeat: **Database Service Start and Stop, Add, Modify, Relocate and Remove**

Manage database services to enable workload distribution and high availability.

```bash
srvctl start service -d rac -s pdb01_oln -i rac1,rac2
```

---

## :bulb: **Miscellaneous Commands**

Other useful commands for managing Oracle RAC.

- **Check cluster version:**
```bash
crsctl query crs releaseversion
```

- **Start a service:**
```bash
srvctl start service -d <db_unique_name> -s <service_name_list>
```

---

For more details, visit the [blog](https://skumar22k.blogspot.com/).
