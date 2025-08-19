# Foundations of Data Systems
    Reliable Scalable and Maintainable
    Data Nodels and Query Language
        - SQL
            - Object Relational mismatch, impedance mismatch, ORM
        - NoSql
            - Good for one-to-many relationship
            - Not good for many-to-many and many-to-one relationship
            - Document and Graph are popular ones
    Storage and Retrieval
        - Storage Engine
            - Log-Structured Storage Engine
                - Segment Files
                - Compaction and Merging
                - Deleting with Tombstone log
                - SSTables & LSM Tree
                    - The sorted in-memory structure is called the memtable
                    - Bloomfilter to check a key's existance
            - Page-Oriented Storage Engine (B-Tree)
    Encoding and Evolution
        - In-Memory
        - On-Disk
        - Encoding or Mrashaling or Serialization (In-memory to Disk)
        - Decoding or UnMrashaling or DeSerialization (Disk to In-Memory)
# Distributed Data
    We distribute data across multiple machines for
        - Scalability
        - High Availability/Fault Tolerance
        - Latency (multiple regions to serve users from closer server to their region)
    Replication
        - Single Leader
            - Reading your own writes
            - Monotonic Reads
            - Consistent prefix reads
        - Multi Leader
            - Multi Datacenter operations
            - Offline Apps
            - Collaborative editing Apps
            - Handling write conflicts
        - Leaderless
            - Read Repair
            - Anti-Entropy process
        - Problems with Replication Lag and gurantees provided by the datastore
    Partitioning
        - Partitioning by Key Range
        - Partitioning by Hash of Key
        - Secondary Key can be partitioned using 2 methods
            - Document-partitioned indexes(local indexes)
                - This will be within the same partition
                - This would require parallel queries to all partitions as this index is present with in the primary partition
            - Term-Partitioned indexes (global indexs)
                - Global outside of these partitions
                - This require finding all the partition that the primary index is in for given secondary index and then querying those partitions

    Transactions

    Trouble with Distributed Systems

    Consistency and Consensus
# Derived Data