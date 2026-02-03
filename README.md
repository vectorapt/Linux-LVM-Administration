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

## Environment

- VMware Virtual Machine running RHEL 9

---

## Implementation Overview

1. Added two new disks (`/dev/sda` and `/dev/sdb`), each with **5 GB** capacity, and verified their availability in the system  
2. Initialized both disks as **Physical Volumes (PVs)**  
3. Created a **Volume Group (vg_data)** using the first disk (`/dev/sda`)  
4. Created a **Logical Volume (lv_data)` of **4 GB** from the Volume Group  
5. Formatted the Logical Volume with the **XFS filesystem**  
6. Mounted the filesystem at `/mnt/lvm_data` and configured a **persistent mount** using `/etc/fstab`  
7. Created a **pre-resize snapshot** of the Logical Volume for rollback purposes  
8. Extended the Volume Group by adding the second disk (`/dev/sdb`), increasing total VG capacity to approximately **10 GB**  
9. Extended the Logical Volume by an additional **4 GB**, resulting in an **8 GB Logical Volume**  
10. Grew the XFS filesystem online to reflect the new Logical Volume size  
11. Created a **post-resize snapshot** of **1 GB** to capture the final expanded state  

---

## Skills Demonstrated

- LVM architecture and storage abstraction
- Dynamic storage expansion
- Filesystem resizing without downtime
- Snapshot-based backup concepts
- Linux system administration practices

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
