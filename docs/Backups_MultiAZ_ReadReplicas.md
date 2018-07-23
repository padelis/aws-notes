# Databses Backups at AWS

- Automated Backups

  - Allows you to recover your database to any point in time within a **retention period** (1-35 days).
    Automated Backups will take a full daily snapshot and will store transaction logs throughout the day. When do a recovery AWS will first choose the most **recent** daily backup, and then apply transaction logs to that day. This allows a **point in time recovery down to a second**, within the retention period.
  - Automated backups are enabled by default.
  - Are stored in S3
  - You are getting storage space equal to the size of the database.
  - Backups are taken within a defined window(storage I/O may be suspended, or you may experience elevated latency).

- Snapshots
  - Always done manually (user initiated)
  - They are stored even after the deletion of the RDS instance.

## Restoring Backups

Whenever you restore Automatic Backups or Snapshots, the restored version will always be a new RDS instance, with a new DNS endpoint.

## Encryption

Encryption is done using AWS Key Management (KMS)
Once an RDS is encrypted:

1.  Data in the underlying storage is encrypted
2.  Automated Backups are encrypted
3.  Snapshots are encrypted
4.  Read Replicas are encrypted

To encrypt an existing RDS instance, you first take a snapshot, make a **snapshot copy** and encrypt that snapshot.

## Multi-AZ vs Read Replicas.

Multi-AZ are **synchronous** and Read Replicas are **asynchronous**.

### Multi-AZ

Multi-AZ is for **Disaster Recovery only**.
For performance improvements, you need Read Replicas.

Multi-AZ allows you to have an exact copy of your production database in another availability zone. AWS handles the replication (writes are automatically synchronized).

In the event of planned DB maintenance, DB failure, or AZ failure, Amazon RDS will automatically failover to the standby database.

Multi-AZ are available:

1.  SQL Server
2.  Oracle
3.  MySQL
4.  PostgreSQL
5.  MariaDB
6.  Aurora by default.

### Read Replicas

Read Replicas allows you to have a read-only copy of your production db. This is achieved using **Asynchronous replication** from the primary RDS to the read replicas

- Used for **read-heavy** database workloads
- You can have up to 5 read replicas.
- You must have automatic backups turned on, to deploy a read replica.
- Each replica has it's own DNS name.
- You can have Read Replicas that have Multi-AZ
- You can create Read Replicas of Multi-AZ databases.
- Can be promoted to Databases (**This beaks Replication**)
- You can have Read Replicas to a second region.

Read Replicas are available:

1.  MySQL
2.  PostgreSQL
3.  MariaDB
4.  Aurora by default.
