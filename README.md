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

ZFS comprises functions of a copy-on-write file system, logical volume manager, and software RAID for serving the purposes of highly scalable storage. To understand how ZFS works, you need to get familiarized with the basic concepts noticed below.
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

### Types of Cloud Storage:
1. Object Storage:

Applications developed in the cloud often take advantage of object storage's vast scalability and metadata characteristics. Object storage solutions like Amazon Simple Storage Service (Amazon S3) are ideal for building modern applications from scratch that require scale and flexibility, and can also be used to import existing data stores for analytics, backup, or archive.

2. File Storage:

Many applications need to access shared files and require a file system. This type of storage is often supported with a Network Attached Storage (NAS) server. File storage solutions like Amazon Elastic File System (EFS), Amazon FSx for NetApp ONTAP, Amazon FSx for OpenZFS, Amazon FSx for Windows File Server, and Amazon FSx for Lustre are for use cases like content repositories, development environments, machine learning, data science, media stores, and user home directories. Amazon FSx for Lustre is ideal for high-performance computing.

3. Block Storage:

Other enterprise applications like databases or ERP systems often require dedicated, low latency storage for each host. This is analogous to direct-attached storage (DAS) or a Storage Area Network (SAN). Block-based cloud storage solutions like Amazon Elastic Block Store (EBS) are provisioned with each virtual server and offer the ultra-low latency required for high performance workloads.

### Storage Protocols:

1. Small Computer System Interface (SCSI):

SCSI is the dominant block level access method for disk in the data center.  Blocks are typically the smallest unit that can be read or written to on a disk, they exist in various sizes depending on disk type and usage.  Block level access means that the server can directly access the disk blocks without the need for a file system in place on top of them, this is opposite of file-based storage discussed later.

SCSI has been in use since the early 1980’s and was originally used to move data within a single server.  The operating system handles writing data using the SCSI protocol to a SCSI drive controller which managed one or more devices on a SCSI cable within a system chassis.  The SCSI controller ensured that only one device would be active on the cable at any time which prevents contention on the SCSI bus.  Because SCSI was managed by a single controller and contained within a system the chance for data loss, or contention were minimal, this meant that SCSI did not require control mechanisms to handle data loss or contention as with networked protocols. SCSI itself is still widely used in its native format but it has also been encapsulated into other protocols for use within storage networks for consolidated storage.

2. Fibre Channel (FC):

Fibre Channel was designed to extend the functionality of SCSI into point-to-point, loop, and switched topologies.  This allows for longer distances as well as storage consolidation.  FC encapsulates SCSI data and Command Descriptor Blocks (CDB) into the payload of Fibre Channel frames.  Fibre Channel networks provided the addressing, routing, and flow-control required to support SCSI data.  Additionally Fibre Channel networks are designed to meet the needs of SCSI by providing ‘lossless’ in order delivery.  This means that in a stable network FC frames will not be dropped, and are delivered in order ensuring that the Upper Layer Protocols (ULP) will not be forced to reorder or resend frames.

Fibre Channel networks are typically carried over fiber-optic links on dedicated infrastructures.  These infrastructures are traditionally built-in pairs as exact mirrors of one another.  This provides complete physical redundancy end-to-end.  Additionally these networks provide high bandwidth and low-latency.  FC networks come in 1/2/4/8 Gbps speeds with 16/32 Gbps in the works.  Additionally 10Gbps FC links are typically available on a proprietary basis for links between switches.

3. internet/IP Small Computer System Interface (iSCSI):

iSCSI takes SCSI data and CDBs and places it in the payload of IP packets.  This allows the SCSI protocol to be extended across existing IP infrastructures.  While IP is routable within the data center and across the WAN iSCSI is not traditionally used/supported over routed boundaries (exceptions do exist.)  The draw of iSCSI has been that storage data can be extended across the existing infrastructure with minimal additional cost.

iSCSI has not gained the market share many have predicted over the years due to flaws in the protocol and limitations of the traditional Ethernet based data center networks.  until the standardization of 10 Gigabit Ethernet most data centers relied on 1GE links which were typically saturated already.  This meant implementing iSCSI required new switching infrastructure.  10GE has changed the bandwidth limits but still not catapulted iSCSI into the mainstream.  There are several reasons for this, one being that there is large existing investment in Fibre Channel, and two being the iSCSI protocol itself.

The problem with iSCSI from a protocol standpoint is that it takes the SCSI protocol which expects lossless, in-order delivery, and places it in TCP/IP packets which are designed to support heterogeneous WAN networks and experience packet loss and out-of-order delivery frequently.  This is done without providing any additional tools to either SCSI or TCP/IP for handling the SCSI payloads in the expected fashion.  This in no way means iSCSI is unusable or should be written off it just means that additional considerations must be made when designing iSCSI, especially in the Enterprise or larger environment.

In order to provide proper performance for iSCSI on shared networks Quality of Service (QoS), physical architecture, and jumbo frame support must be taken into account.  Because of these considerations many iSCSI networks have traditionally been placed on separate network hardware from the data center LAN (isolated iSCSI networks.)  This has minimized some of the benefits of consolidating on a single protocol.  With 10 Gigabit Ethernet and the standardization of Data Center Bridging (DCB) iSCSI looks more promising for a greater audience.

4. Fibre Channel over Ethernet (FCoE):

FCoE was ratified in 2009 and provides the functionality for moving native Fibre Channel across consolidated Ethernet networks.  FcoE relies on the DCB standards referenced above.  FCoE encapsulates full Fibre Channel frames inside Ethernet Jumbo Frame payloads.  Utilizing jumbo frames ensure that the FC frame is not fragmented or changed in any way.  The FCoE and DCB standards provide a robust tool set for consolidating existing Fibre Channel workloads on shared 10GE networks while providing the lossless, in-order delivery SCSI expects.  FCoE does not modify the existing Fibre Channel protocol suite and allows for the same management model including zoning, LUN masking, etc.  FCoE has started gaining ground over the last two years pushed by several large hardware vendors in the storage, network, and server markets.

5. Common Internet File System (CIFS):

CIFS is a file based storage system based on Small Message block (SMB.)  This is a shared storage protocol typically used in Microsoft environments for file sharing.  Windows-based file shares rely on CIFS as the transfer protocol of the file level data.  File based storage relies on an underlying files system such as FAT32, XFS, NTFS or otherwise which differs from block based storage which does not.  File level storage is an excellent medium for some applications but is not traditionally effective in others.  When an application needs direct block access to disk file based storage is not appropriate.  Deployments that fall into this category include some databases and most Operating Systems.

6. Network File System (NFS):

NFS is another file based storage protocol.  NFS is traditionally used in Linux and Unix environments.  NFS is also a widely used protocol for VMware environments and can offer several benefits for virtual machine storage.  As a file based storage protocol NFS experiences many of the same limitations as stated for CIFS above.

7. Hyper Text Transfer Protocol (HTTP) and others:

When the cloud discussion leaves the data center (private/internal cloud) and moves up to the service provider level such as Google, Amazon, or the TelCos the protocols listed above may not have the necessary scalability.  When you begin talking about supporting thousands of customers with multiple Terabytes each, traditional storage protocols may not suffice.  It has to do with both the scalability of the systems and the administration of the disk.  iSCSI and FC both require a fair amount of management for the RAID, volumes, and LUNs, whereas CIFS and NFS require a fair amount for the security and volumes.  Protocols such as HTTP based storage are being used to simplify storage configuration and increase its scalability.

Which is the right protocol to use when moving to the cloud?  Obviously there is only one answer!  As always in IT ‘it depends.’  Each protocol has it’s uses, benefits and drawbacks.  The most important thing to remember is that most environments can benefit from more than one or all of these protocols.  Every application is different and any given protocol may have advantages for a particular app.  The only universal truth in cloud storage is that protocol flexibility will be key.

### NFS 3 vs NFS 4 :
#### Export Management :
1. In NFSv3, client must rely on auxiliary protocol, the mount protocol to request a list of server’s exports and obtain root filehandle of a given export. It is fed into the NFS protocol proper once the root filehandle is obtained.
2. In NFSv4 uses the virtual file system to present the server’s export and associated root filehandles to the client.
3. NFSv4 defines a special operation to retrieve the Root filehandle and the NFS Server presents the appearance to the client that each export is just a directory in the pseudofs.
4. NFSv4 Pseudo File System is supposed to provide maximum flexibility. Exports Pathname on servers can be changed transparently to clients.

#### State :
1. NFSv3 is stateless. In other words if the server reboots, the clients can pick up where it left off. No state has been lost.
2. NFSv3 is typically used with NLM, an auxiliary protocol for file locking. NLM is stateful that the server LOCKD keeps track of locks.
3. In NFSv4, locking operations are part of the protocol.
4. NFSv4 servers keep track of open files and delegations.

#### Blocking Locks :
1. NFSv3 rely on NLM. Basically, Client process is put to “sleep”. When a callback is received from the server, client process is granted the lock.
2. For NFSv4, the client to put to sleep, but will poll the server periodically for the lock.
3. The benefits of the mechanism is that there is one-way reachability from client to server. But it may be less efficient.
