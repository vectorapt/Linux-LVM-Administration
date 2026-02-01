# Linux LVM Administration

This project demonstrates advanced Linux storage management using Logical Volume Manager (LVM) to create flexible and scalable storage.

It simulates real-world scenarios where storage needs to be expanded dynamically without downtime, along with snapshot creation for backup and recovery purposes.

---

## Project Scope

- Physical Volume (PV) creation
- Volume Group (VG) creation and extension
- Logical Volume (LV) creation
- Filesystem setup and mounting
- Dynamic storage expansion
- Filesystem growth
- LVM snapshot creation

---

## Technologies & Tools

- RHEL 9 (Linux)
- LVM utilities (pvcreate, vgcreate, vgextend, lvcreate, lvextend)
- mkfs (ext4/xfs)
- mount and filesystem tools
- resize2fs / xfs_growfs
- lsblk, df -h

---

## Implementation Overview

1. Attached additional disks and verified them in the system
2. Created Physical Volumes on new disks
3. Created a Volume Group using the first disk
4. Extended the Volume Group by adding a second disk
5. Created a Logical Volume from the Volume Group
6. Formatted the Logical Volume with a Linux filesystem
7. Mounted the filesystem
8. Extended the Logical Volume to use added storage
9. Grew the filesystem to reflect new capacity
10. Created and mounted an LVM snapshot

---

## Skills Demonstrated

- LVM architecture and storage abstraction
- Dynamic storage expansion
- Filesystem resizing without downtime
- Snapshot-based backup concepts
- Linux system administration practices

---

## Environment

- VMware Virtual Machine running RHEL 9

---

## Result

Successfully implemented scalable storage using LVM with live expansion and filesystem growth, including snapshot functionality for data protection.

---

## Documentation

Screenshots demonstrating each major stage (PV creation, VG setup and extension, LV creation, mounting, expansion, filesystem growth, and snapshot creation) are available in the documentation folder.

---

## Key Commands & Configuration Used

- lsblk – Display block devices and disk layout
- pvcreate – Create Physical Volumes
- vgcreate – Create Volume Groups
- vgextend – Extend Volume Groups
- lvcreate – Create Logical Volumes and snapshots
- lvextend – Extend Logical Volumes
- mkfs – Create filesystems
- mount / umount – Mount and unmount filesystems
- resize2fs / xfs_growfs – Resize filesystems
- df -h – Verify storage usage
