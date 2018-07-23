# Aurora

Amazon Aurora is MySQL-compatible, relational database that combines speed and availability of high-end commercial databases with the simplicity and cost effectiveness of open source databases.

- 5 times more performance than MySQL.
- Runs only on AWS.
- It's mySQL compatible.

## Aurora Scaling

- Starts with 10 GB
- Storage Auto-scales.
- Compute resources also scale up.
- 6 Copies of your data (2 in each AZ)
- Storage is self healing

### Replica Features

- Aurora Replicas (currently 15)
- MySQL Read Replicas (currently 5)

Aurora Replicas **automatically fail over** (MySQL not).
