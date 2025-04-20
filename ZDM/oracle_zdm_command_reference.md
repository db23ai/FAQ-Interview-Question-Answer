
# 🚀 Oracle Zero Downtime Migration (ZDM) – Command Reference

This document provides a comprehensive list of `zdmcli` commands used in Oracle Zero Downtime Migration (ZDM) operations, including setup, migration, validation, job management, and customization.

---

## 📦 General Commands

| Command | Description |
|--------|-------------|
| `zdmcli -help` | Displays help for using ZDM CLI |
| `zdmcli -version` | Shows the current version of ZDM |
| `zdmcli -build` | Returns ZDM version info incl. Cloud Premigration Advisor |
| `zdmcli setup install` | Configures ZDM on a new server |
| `zdmcli setup wizard` | Launches the interactive setup wizard |

---

## 🛠️ Migration Commands

| Command | Description |
|--------|-------------|
| `zdmcli migrate database` | Initiates a new migration job |
| `zdmcli validate database` | Validates the source and target setup |
| `zdmcli migrate database -eval` | Evaluates the migration without running it |
| `zdmcli migrate database -listphases` | Lists all migration phases |
| `zdmcli migrate database -pauseafter <phase>` | Pauses the job after the specified phase |

---

## 📋 Job Management Commands

| Command | Description |
|--------|-------------|
| `zdmcli query job -jobid <job_id>` | Checks status and details of a job |
| `zdmcli list jobs` | Lists all migration jobs |
| `zdmcli describe job -jobid <job_id>` | Detailed info on a specific job |
| `zdmcli delete job -jobid <job_id>` | Deletes a specific migration job |
| `zdmcli abort job -jobid <job_id>` | Terminates a running job |
| `zdmcli resume job -jobid <job_id>` | Resumes a paused migration job |
| `zdmcli modify job -jobid <job_id> -rsp <response_file>` | Modifies job parameters during execution |

---

## 🧩 User Action & Image Type Commands

| Command | Description |
|--------|-------------|
| `zdmcli add imagetype -imagetype <name> -basetype <type> [-useractions <list>]` | Creates new image type |
| `zdmcli modify imagetype -imagetype <name> -useractions <list>` | Edits user actions for an image type |
| `zdmcli add useraction ...` | Adds pre/post user-defined actions (e.g., scripts) |
| `zdmcli modify useraction ...` | Modifies existing user actions for a phase |

---

## ⚙️ Migration Parameters (used with `migrate database`)

```bash
-sourcedb <source_db_unique_name>
-sourcesid <source_oracle_sid>
-rsp <response_file_path>
-sourcenode <source_host_name>
-targetnode <target_host_name>
-targethome <target_home>
-tdekeystorepasswd              # Prompt for source TDE keystore password
-tgttdekeystorepasswd           # Prompt for target TDE keystore password
-tdemasterkey                   # Master key for encryption
-useractiondata <json_data>
-imagetype <image_type>
-backupuser <user>
-backuppasswd                   # Prompt for backup password
-restoreuser <user>
-tgttdekeystorewallet <wallet_path>
-tgtuser <user>
```

---

## 📚 Resources

- [Oracle ZDM Documentation](https://docs.oracle.com/en/database/oracle/zero-downtime-migration/)
- [Oracle Blogs – ZDM Use Cases](https://blogs.oracle.com)
- [Oracle ZDM Troubleshooting](https://blog.gleb.ca/2020/06/23/oracle-zero-downtime-migration-troubleshooting/)

---

> 💡 **Tip:** Use `zdmcli -help` or `zdmcli <command> -help` for command-specific assistance.

---

## 🔒 License

Distributed under the MIT License. See `LICENSE` for more information.
