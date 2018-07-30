# Volumes and Snapshots

- Volumes exist on EBS.
- Snapshots exist on S3

- Snapshots are point in time copies of volumes (photos)
- Snapshots are incremental
  (only the blocks that have changed since the last snapshot are moved to s3)

## Key Points

- For root devices you should stop the instances first and then take a snapshot. You can take a snapshot in any case.

- You can create AMI's from EBS-backed Instances and Snapshots.

- You can change the volume size on the fly (Changing size and storage).

- Volumes are **always** in the same **availability zone as the EC2 instance**

- To move them, first take a snapshot and then copy it.

- Snapshot of encrypted volumes are auto encrypted.

- You can share snapshots that are unencrypted.

## RAID Volumes & Snapshots

Types of Redundant Array of Independent Disks:

- RAID 0 - Striped - Good performance
- RAID 1 - Mirrored, Redundancy
- RAID 5 - AWS does not recommend.
- RAID 10 - Mirrored and Striped.

Take snapshot of a raid array

- Stop the application from writing to disk.
- Flush all caches to disk.
  - Freeze the filesystem.
  - Unmount the RAID
  - Shutdown the EC2 instance

Root devices always stop first.

## AMI Types

- EBS backed - Launched from the AMI - Created from an EBS Snapshot.
- Instance Store. Launched from the AMI - Created from a template stored in amazon s3

## Tips

- We cant add instance store after AMI creation
- We can't stop the instance store.
- If it's on a failed host, you lose it. **Ephemeral Store**.
- By default root volumes will be deleted upon termination.
- EBS volumes can be kept if instructed.
