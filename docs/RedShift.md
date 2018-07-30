# RedShift (Data Warehouse)

Fully managed Data Warehouse service in the cloud.
Around $1000 dollars per TB.

<!-- OLAP Transaction Example. -->

Redshift Configuration

- Single Node (Up to 160GB)
- Multi Node
  - Leader Node (manage client connection)
  - Compute Node (store data and perform computations (up to 128 nodes))

## Columnar Data Storage

Amazon Redshift organizes data by column (instead of series of rows). Column-based systems are ideal for data warehousing and analytics. Column-based system require far fewer I/Os, greatly improving query performance. **Blocksize is 1024KB**.

## Advanced Compression

Columnar Data Storage can be compressed much more than row-based stored because similar data is stored sequentially on disk.

When loading data into an empty table, Amazon Redshift automatically sample your data and selects the most appropriate compression schema.

## Massively Parallel Processing (MPP)

RedShift distributes data and query loads across all nodes.

## Pricing

- Compute Node Hours
  - 1 unit per node per hour
- Backup
- Data Transfer

## Security

- Encrypted in transit using SSL
- Encrypted at rest using AES-256
- By default RedShift takes care of key management.
  - You can manage your own keys

## Availability

- Currently only availabe in 1 AZ
- You can restore snapshots to a new AZ
