# Filesystem:
### Types of Filesystem:
1. Ext2
2. Ext3
3. Ext4
4. JFS
5. Reiserfs
6. XFS
7. Btrfs
8. ZFS

#### Ext ( Extended Filesystem ):
- primarily was developed for MINIX. 
- The second extended version (Ext2) was an improved version.
- Ext3 added performance improvement. 
- Ext4 was a performance improvement besides additional providing additional features.

#### JFS ( Journaled File System ):
- developed by IBM for AIX UNIX which was used as an alternative to system Ext.
- JFS is an alternative to Ext4 currently and is used where stability is required with the use of very few resources.
- When CPU power is limited JFS comes handy.

#### ReiserFS:
- It was introduced as an alternative to Ext3 with improved performance and advanced features.
- There was a time when SuSE Linux‘s default file format was ReiserFS but later Reiser went out of business and SuSe had no option other than to return back to Ext3.
- ReiserFS supports file System Extension dynamically which was relatively an advanced feature but the file system lacked certain area of performance.

#### XFS:
- XFS was a high speed JFS which aimed at parallel I/O processing. NASA still usages this file system on their 300+ terabyte storage server.

#### Btrfs ( B-Tree File System ):
- Focus on fault tolerance, fun administration, repair System, large storage configuration and is still under development. Btrfs is not recommended for Production System.

#### ZFS ( Zettabyte File System ):
ZFS is a file system originally developed by Sun Microsystems for building next-generation NAS solutions with better security, reliability, and performance. ZFS was designed in 2001 by Matthew Ahrens and Jeff Bonwick and it was supposed to be a next-generation file system for another Sun Microsystems’ system called OpenSolaris. A port for FreeBSD was made in 2008. Unlike other systems on the market, ZFS is a 128-bit file system offering virtually unlimited capacity. In turn, ZFS on Linux (ZOL) was created in 2013. Brian Behlendorf, Jorgen Lundman, Aron Xu, and Richard Yao were among those who helped to create and maintain ZOL.

ZFS comprises functions of a copy-on-write file system, logical volume manager, and software RAID for serving the purposes of highly scalable storage. To understand how ZFS works, you need to get familiarized with the basic concepts displayed in the diagram below.
- Pooled storage:

Pooled storage is basically a ZFS pool that is a collection of one or more vdevs that are virtual devices storing the data. The ZFS pool, also called Zpool, serves as the highest data container in the whole ZFS system. The Zpool is used to create one or more file systems (datasets) or block devices (volumes). These file systems and block devices share the remaining pool’s space. Partitioning and formatting operations will be conducted by the ZFS system.
- Copy-on-write:

Copy-on-write can be explained as follows. On most file systems, the data is lost forever once it is overwritten. On ZFS, on the other hand, the new information is written to a different block. The file systems’ metadata is then updated to the point of the new information once the write is complete. This results in preserving the old data in case of a system crash or other harmful event.
- Snapshots:

The snapshot is a read-only copy of the file system created during a particular point in time. It is possible to make snapshots of entire datasets or pools. The snapshot includes the original system version of the file system together with any changes made once the snapshot has been taken. In simple terms, a differential read-only copy is being created while creating a snapshot. You are able to revert the changes by performing a rollback operation of the snapshot. Bear in mind that you will lose all changes since the snapshot was taken. 
- Data integrity:

Data integrity can be elaborated in the following way. While writing data, a checksum is calculated and written together with it. Later on, when the data is read, the checksum is calculated once more. In case the checksums of the written and read data do not match, a data error is detected. An attempt to correct the error automatically will be then made by the system.
- RAID-Z:

RAID-Z is an implementation of a modified RAID-5. On ZFS, it is capable of overcoming the write hole error detected in original RAID-5. The basic level of RAID-Z, that is, RAID-Z1 requires three disks to work: two disks for storage and one for parity. In turn, RAID-Z2 has to have two disks for storage and two for parity. RAID-Z3 has to have minimum two storage drives and three drives for parity. Note that drives have to be placed in multiples of two when they are added to the RAID-Z pools.

### In Addition:
#### Clustered File Format:
- Clustered file System is not required for booting but best suited in shared environment form storage point of view.

#### Non-Linux File Format:
- NTFS by Microsoft.
- HFS by Apple/Mac os.
- Most of these can be used under Linux by mounting them using certain tools like ntfs-3g to Mount NTFS file system but not preferred under Linux.

> IMPORTANT NOTE: Ext4 is the preferred and most widely used Linux file System. In certain Special case XFS and ReiserFS are used. Btrfs is still used in experimental environment.



# Cloud Filesystem and Storage:
### Cloud File storage:
Cloud file storage is a method for storing data in the cloud that provides servers and applications access to data through shared file systems. This compatibility makes cloud file storage ideal for workloads that rely on shared file systems and provides simple integration without code changes.

### Cloud Filesystem:
A file system in the cloud is a hierarchical storage system that provides shared access to file data. Users can create, delete, modify, read, and write files and can organize them logically in directory trees for intuitive access.

### Benefits:
1. Scalability : 
Although not every cloud file storage solution can scale, leveraging all the capabilities of the cloud, the most advanced solutions provide the ability to start with the capacity and performance you need today and grow your capacity as needed. No more over provisioning to try and anticipate future needs.

2. Interoperability : 
Many existing applications require integration with shared file services that follow existing file system semantics. Cloud file storage solutions offer a distinct advantage as there is no new code to write to have secure, shared file access.

3. Budget and Resources : 
Operating file services on-premises requires budget for hardware, ongoing maintenance, power, cooling, and physical space. Cloud file storage enables organizations to redeploy technical resources to other projects that bring more value to the business.

## A File System in the Cloud and A Cloud File System :
There are two types of cloud based file systems. One is designed to extend cloud storage into the organization. The other is designed to allow organizations to run applications in the cloud but use more traditional file protocols like NFS and SMB. Both have their roles, but the organizations needs to make sure it is picking the right tool for the job.

### A File System in the Cloud:
A file system in the cloud is exactly what it sounds like. The vendor creates a file system that offers traditional file protocols like NFS or SMB to cloud hosted applications. Essentially, the vendor provides an instance of their file system and the organization implements it in the cloud provider of their choice. It then allocates the appropriate storage compute performance and the storage IO.

### A Cloud File System:
A cloud file system is a file system that creates a hub and spoke method of distributing data. The “hub” is the central storage area, typically located at a public cloud provider like Amazon AWS, Microsoft Azure or Google Cloud. The “spokes” are the organization’s local locations (data centers, branch offices, remote offices). At each spoke a software or hardware appliance is installed and it acts as a cache for that location’s most active data.

It is important to note that all vendors claiming to have a cloud file system are not created equal. The distribution of data, while critical, is just the first step. Organizations need to examine how accurate the vendor’s caching algorithms are and how efficiently they can transfer data to and from the cloud. Beyond the critical first step of data distribution, organizations need to look for solutions that provide high performance access, global file locking, granular scaling of capacity and intelligent archiving.
