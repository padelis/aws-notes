# Storage Summary

1. S3 is Object Base storage.
2. 0b - 5 Tb
3. Files are stored in buckets.
4. Bucket names are universal.
5. Read after write consistency for PUTS.
6. Overwrite PUTs and DELETEs take some time to propagate.

## Storage tiers

1. S3 Standard 11x9 durability 2x9 availability.
2. S3 - IA (You want low cost, but fast retrieval times)
3. S3 One Zone - IA. (Not across multiple facilities)
4. Glacier -> Expedited, Standard and Bulk

## S3 Fundamentals

1. Key
2. Value
3. Version ID
4. Metadata
5. Access Control Lists

## S3 Versioning

1. Stores all versions
2. Great Backup
3. Once enabled cannot be disabled
4. Versions MFA Delete capability.
5. Cross Region Replications

## Lifecycle Management

1. Can be used with versioning
2. Can be applied to current and previous versions
3. Trasnitions
    - Standard - Infrequent Access Storage Class
    - Glacier
    - Permantly Delete

## Cloud Front

**Edge Location** Is a location where content is cached.

**Origin** The origin of the files that the CDN will distribute (EC2,S3 Buckets).

**Distribution** the name of the CDN a collection of edge locations.

1. Edge Locations are not read only.
2. Object are cached for TTL.
3. You can clear cache

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
It's pure storage.
- Snowball Edge can run Lamba functions
- Snowmobile (Its a truck).


## Transfer Acceleration.
Use distinct URLs

## S3 Static Websites
Serverless - STATIC only.


## Several Tips
Responds 200.
Multipart Upload
S3 FAQ. Have to.
