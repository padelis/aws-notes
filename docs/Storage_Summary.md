# Storage Summary

- S3 is Object Base storage.
- 0b - 5 Tb filesize
- Files are stored in buckets.
- Bucket names are universal.
- Read after write consistency for PUTS.
- Overwrite PUTs and DELETEs take some time to propagate.

## Storage tiers

- S3 Standard 11x9 durability 2x9 availability.
- S3 - IA (You want low cost, but fast retrieval times)
- S3 One Zone - IA. (Not across multiple facilities)
- Glacier -> Expedited, Standard and Bulk

## S3 Fundamentals

- Key-Value
- Version ID
- Metadata
- Access Control Lists

Bucket URL format:

```
http://s3-eu-west-1.amazonaws.com/mybucket
```

## S3 Versioning

- Stores all versions
- Great Backup
- Once enabled cannot be disabled
- Versions MFA Delete capability.
- Cross Region Replications

## S3 Cross Region replication.

1.  Versioning must be enabled (source + destination).
2.  Regions must be unique.
3.  Existing Files are not replicated(**new files** are replicated).
4.  Delete markers are replicated.
5.  Deleting versions or markers are not replicated.

## Lifecycle Management

1.  Can be used with versioning
2.  Can be applied to current and previous versions
3.  Trasnitions
    - Standard - Infrequent Access Storage Class
    - Glacier
    - Permantly Delete

## Cloud Front

**Edge Location** Is a location where content is cached.

**Origin** The origin of the files that the CDN will distribute (EC2,S3 Buckets).

**Distribution** the name of the CDN a collection of edge locations.

1.  Edge Locations are not read only.
2.  Object are cached for TTL.
3.  You can clear cache

## Security

- By Default all buckets are private
  - Bucket Policies
  - Access Control Lists
- Can create access logs

## Encryption

- In transit
  - SSL/TLS
- At rest
  - SSE-S3
  - SSE-KMS
  - SSE customer provided keys.

## Storage Gateway

- File Gateway
- Volume Gateway
  - Stored Volumes (asynchronously backed in S3)
  - Cached Volumes (stored on S3)
- Virtual Tapes

## Snowball

- Snowball Standard
- Snowball Edge can run Lamba functions
- Snowmobile (Its a truck).

## S3 Transfer Acceleration.

Utilizes the CloudFront Edge Network to accelerate S3 uploads.
You can use a **distinct URL** to upload to an edge location near you/

```
 mybucket.s3-accelerate.amazonaws.com
```

## S3 Static Websites

Serverless - STATIC only.

## Several Tips

Responds 200 when upload is complete.
[Multipart Uploads](https://docs.aws.amazon.com/AmazonS3/latest/dev/mpuoverview.html#mpuploadpricing) enables you to upload large objects in parts.
