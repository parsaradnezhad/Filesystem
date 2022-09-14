# Filesystem:
### Types of Filesystem:
1. Ext2
2. Ext3
3. Ext4
4. JFS
5. Reiserfs
6. XFS
7. Btrfs

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

