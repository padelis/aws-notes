# Databases

- Relational DBs (OLTP) available at AWS

  - SQL Server
  - Oracle
  - MySQL
  - PostgreSQL
  - Aurora (Amazon)
  - MariaDB

    - Non Relational JSON/NO SQL

  - DynamoDB

- Data Warehousing (Used for Business Intelligence)
  - RedShift
  - Cognos
  - Jaspersoft
  - SQL Server reporting services
  - Oracle Hyperion
  - SAP
    Used to pull large data sets

## OLTP vs OLAP

Online Transaction Processing differs from Online Analytics processing in terms of the types of queries you will run. OLAP example - Sum of barbies sold in EMEA.

## Elasticache

Elasticache is a web service that makes easy to deploy, operate and scale an in-memory cache in the cloud.

- Memcached
- Redis

## Connect to an RDS instance.

## Common Use Case

1 security group for the RDS Instance
1 security group for the EC2 Instance

In order to connect, you have to **add an inbound rule** to the security group of the RDS instance (open port 3306)
and **white-list the security group of the EC2 instance**.

## Multi-AZ

Multi-AZ is for **Disaster Recovery only**.
For performance improvements, you need Read Replicas.

Multi-AZ allows you to have an exact copy of your production database in another availability zone. AWS handles the replication (**writes are automatically synchronized**).

In the event of planned DB maintenance, DB failure, or AZ failure, Amazon RDS will automatically failover to the standby database.

### Read Replicas

Read Replicas allows you to have a read-only copy of your production db. This is achieved using **Asynchronous replication** from the primary RDS to the read replicas

## Tips

Maximum value of backup Retention is 35 days. Default is 1 day via the API and 7 days via console

Elasticache is a good choice, if your database is **read heavy** and not prone to frequent changing.

RedShift is a good choice if your database is stressed because of **OLAP transactions**

Maximum RDS Storage with Oracle and MySQL is 16TB (40000 IOPS).
