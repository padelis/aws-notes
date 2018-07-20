# Elastic File System

Is a file storage service for EC2.
Allows to create and configure file systems.
Storage capacity is **elastic**.
Apps have the storage when they need.

- Supports NFSv4
- You only pay what you use.
- Can scale to petabytes
- Data is stored across multiple AZ's within region
- It is block base storage - not object base.

EC2 instances **must** be in the same security group with the EFS.

```
sudo mount -t nfs4 -o nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2,noresvport fs-9fb372c6.efs.eu-central-1.amazonaws.com:/ efs
```

The main use case is a file server.
You can also apply user and directory level permissions.
