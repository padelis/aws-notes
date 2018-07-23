# Elasticache

Elasticache is a web service that makes easy to deploy, operate and scale an in-memory cache in the cloud.

Can be used to:

- Improve latency and throughput for **read-heavy** apps
- Improve application performance with caching critical pieces of data in memory

## Types

- Memecached
  - Elasticache is protocol compliant with Memcached.
- Redis
  - Supports data structures (e.g sorted stes)
  - Elasticache supports Master/Slave Replication and Multi-AZ to achieve cross AZ redundancy

** Redis gets you multi AZ capabilities instead of Memcached **

## Tips

Elasticache is a good choice, if your database is read heavy and not prone to frequent changing.

RedShift is a good choice if your database is stressed because of OLAP transactions
