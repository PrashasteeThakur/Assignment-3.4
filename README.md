# Assignment-3.4

1.Importance of Namenode in Hadoop cluster

Namenode is master daemon process of HDFS.
It keeps information about file system stored in HDFS. The information is meta data about files and directories.
It is important to note that actual data of HDFS files are stored on Data nodes in form of blocks. Namenode only stores on which data    node in HDFS the files blocks are stored.
If namenode is down, the file system is not available as it this only process which keep track of data on data nodes. Hence it is also called as SINGLE POINT OF FAILURE.
A NameNode contains two important files on its hard disk:
1.fsimage (file system image) contains: 
• A directory structure of the HDFS 
• Replication level of the files 
• Modification and access times of files 
• Access permissions of files and directories 
• Block size of files 
• Blocks constituting a file 
2.Edits 
• When any operation takes place in HDFS, the directory structure gets modified 
• These modifications are stored in the memory as well as in the edits files (edits files are stored on the hard disk) 
• If the existing fsimage file gets merged with edits, we’ll get an updated fsimage file 
• This process is called “checkpointing” and is carried out by the Secondary NameNode. It takes the fsimage and edits files from the NameNode and returns updated fsimage file after merging.
