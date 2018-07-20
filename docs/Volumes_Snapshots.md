# Volumes and Snapshots

Volumes exist on EBS

- Virtual Hard Disks

Snapshots exist on S3
Snapshots are point in time copies of volumes (photos)

Snapshots are incremental
(only the blocks that have changed since the last snapshot are moved to s3)

For root devices you should stop the instances
You can take it in any case.

You can create AMI's from EBS-backed Instances and Spanshots.

You can change the volume size on the fly
(changing size and storage)

Volumes are **always** in the same availability zone as the EC2 instance

To move them -> snapshot -> then copy.

Snapshot of encrypted volumes are auto encrypted.

You can share snapshots that are unencrypted.

How to move!

# RAID Volumes & Snapshots

RAID = Reduntant Array of Independent Disks
RAID 0 - Striped - Good performance
RAID 1 - Mirrored, Redundancy
RAID 5 - aws does not recommend.
RAID 10 - Mirrored and Striped.

Take snapshot of a raid array

- Stop the application from writing to disk.
- Flush all caches to disk.

Freeze the filesystem
Unmount the raid
Shutdown the EC2 instance

Root devices always stop first.

# AMI Types

- EBS backed - Launched from the AMI - Created from an EBS Snapshot.
- Instance Store. Launched from the AMI - Created from a template stored in amazon s3

Region
OS
Arch 32-64
Permissions
Storage

We cant add instance store after AMI creation
We can't stop the instance store.
if it is on failed host we lose it. ephemeral store.

By default root volumes will be deleted upon termination
ebs volumes can be kept.
