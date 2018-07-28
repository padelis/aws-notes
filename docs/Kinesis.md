# Kinesis

## Streaming Data

Streaming Data is data the is generated continuously by thousand of data sources, which send in the data records simultaneously, and in small sizes

## Kinesis

Amazon Kinesis is a platform on AWS, that allows to send your streaming data to. Kinesis makes it easy to load and analyze streaming data.

## Kinesis Streams

Data producers send data to Kinesis Streams. It's stored in Shards for 24 Hour - 7 Days Retention

The capacity of your stream is a function of the number of shards that you specify for your stream. The total capacity of the streams is the sum of the capacities of its shards.

Consumers send data to DynamoDB or S3

## Kinesis Firehose

It's completely automated. You can analyze data with Lambda in real time and then send them to S3 or other locations.

You don't have retention. Data send to Firehose are already analyzed.

No consumers. No shard management.

## Kinesis Analytics

Allows you to run SQL queries of that data (that exist in Streams or Firehose) and then send them to S3 or Redshift
