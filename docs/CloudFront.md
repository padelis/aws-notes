# CloudFront - Content Delivery Network

A system of distributed servers (networks) that delivers content
based on geographical locations of the user, the origin of the webpage and a content delivery server.

### Edge Location

The locations where the content will be cached.
Edge Locations are **NOT** read only.
You can restrict viewer access by using **Signed URLs** or **Cookies**.

### Origin

The source of the files distributed can be:

- S3 Bucket
- EC2 Instance
- Elastic Load Balancer
- Route53

### Distribution

The name given to CDN - A collection of a Edge Locations.
The first user's request suffers.

## Summary

- Web Distributions used for Static Websites.
- RTMP used for Media Streaming.
- Edge Locations are **NOT** read only.
- Objects are cached for the TTL (Time to Live)
- Clearing cache costs (You will be charged).
