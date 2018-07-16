## CDN
A system of distributed servers (networks) that delivers content
based on geographical locations of the user, the origin of the webpage and a content delivery server.

### Edge Location
The location where the content will be cached.

### Origin
Apo pou tha parei tha arxeia.
It can be:
1. S3 Bucket
2. EC2 Instance
3. Elastic load balancer
4. Route53

### Distribution.
The name given to cdn a collections a edge locations.

The first user suffers the performance network.

## Summary.
1. Web Distribution -> For websites.
2. RTMP -> Media Streaming.
3. Edge Location (Are NOT read Only.)
4. Objects are cached for the life of TTL (Time to Live)
5. Clearing cahce (you will be charged.)

## Lab Notes

1. Restrict Viewer Access (Signed URL or Cookies)
