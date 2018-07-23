# Amazon DynamoDB

Amazon DynamoDB is a fast and flexible NOSQL database for applications that need consistent, single digit millisecond latency at any scale.

It is fully managed and supports both document and key-value models.

- Stored on SSD storage
- Spread Across 3 geographically distinct data center.
- Eventual Consistency Reads
  - Consistency across all copies of data is usually reached within a second (Best Read Performance).
- Strongly Consistent Reads
  - A strongly consistent read returns a result that reflects all writes that received a successful response prior that read. (less than a second)

## Pricing

- Based on Provisioned Throughput Capacity.
  - Write Throughput hourly ($0.0065) fee every 10 units
  - Read Throughput hourly ($0.0065) fee every 50 units
- Storage Cost ($0.25 GB per month)

- Can be expensive for writes.
- You can reserve capacity
- Push Button Scaling (Change capacity units)
