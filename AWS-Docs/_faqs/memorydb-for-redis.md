General
Q: What is Amazon MemoryDB for Redis?

A: Amazon MemoryDB for Redis is a Redis-compatible, durable, in-memory database service that delivers ultra-fast performance. MemoryDB enables you to achieve microsecond read latency, single-digit millisecond write latency, high throughput, and Multi-AZ durability for modern applications, like those built with microservices architectures. These applications require low latency, high scalability, and use Redis’ flexible data structures and APIs to make development agile and easy. MemoryDB stores your entire dataset in memory and leverages a distributed transactional log to provide both in-memory speed and data durability, consistency, and recoverability. You can use MemoryDB as a fully managed, primary database, enabling you to build high-performance applications without having to separately manage a cache, durable database, or the required underlying infrastructure.

Q: How do I get started with using MemoryDB?

A: You can get started by creating a new MemoryDB cluster using the AWS Management Console, Command Line Interface (CLI), or Software Development Kit (SDK). To create a MemoryDB cluster in the console, sign in and navigate to Amazon MemoryDB for Redis. From there, select “Get Started” then “Create new cluster.” For more detailed steps, and how to get started with the CLI, please see the MemoryDB documentation.

Q: What is Redis?

A: Redis is an open-source, in-memory, key-value data store that utilizes flexible data structures such as strings, lists, sets, hashes, sorted sets, and more. Redis also provides functionality for geospatial query, pub/sub, custom scripts using Lua, and more. Because it stores data in-memory, Redis offers ultra-fast performance and high throughput. Redis is Stack Overflow developers’ “Most Loved Database” for the fifth consecutive year and a top-ranked database to be adopted by the Cloud Native Computing Foundation (CNCF) End User Community. CNCF was founded to encourage and support cloud native computing including containers and microservices. For more information on Redis, visit this page to learn about running Redis on AWS or the open source documentation.

Q: Is MemoryDB compatible with Redis?

A: Yes. MemoryDB maintains compatibility with open source Redis and supports the same set of Redis data types, parameters, and commands that you are familiar with. This means that your application code, clients, and tools you already use today with Redis can be used with MemoryDB. MemoryDB supports all Redis data types such as strings, lists, sets, hashes, sorted sets, hyperloglogs, bitmaps, and streams. Also, MemoryDB supports the 200+ Redis commands with the exception of Redis admin commands, because MemoryDB manages your cluster for you.

Q: What Redis versions does MemoryDB support?

A: For information on the versions of Redis supported in MemoryDB, please visit the MemoryDB documentation.

Q: What is a MemoryDB cluster?

A: A MemoryDB cluster is a collection of one or more nodes serving a single dataset. A MemoryDB dataset is partitioned into shards, and each shard has a primary node and up to 5 optional replica nodes. A primary node serves read and write requests, while a replica only serves read requests. A primary node can failover to a replica node, promoting that replica to the new primary node for that shard. For more information, visit the MemoryDB documentation.

Q: When should I use MemoryDB versus Amazon ElastiCache for Redis?

A: MemoryDB for Redis is a durable, in-memory database for workloads that require an ultra-fast, Redis-compatible primary database. You should consider using MemoryDB if your workload requires a durable database that provides ultra-fast performance (microsecond read and single-digit millisecond write latency). MemoryDB may also be a good fit for your use case if you want to build an application using Redis data structures and APIs with a primary, durable database. Finally, you should consider using MemoryDB to simplify your application architecture and lower costs by replacing usage of a database with a cache for durability and performance.

ElastiCache for Redis is a service that is commonly used to cache data from other databases and data stores using Redis. You should consider ElastiCache for Redis for caching workloads where you want to accelerate data access with your existing primary database or data store (microsecond read and write performance). You should also consider ElastiCache for Redis for use cases where you want to use the Redis data structures and APIs to access data stored in a primary database or data store.

Q: What availability does MemoryDB have?

A: Please refer to the service level agreement (SLA).

Q: What are the current service limits and quotas?

For current limits and quotas, see the MemoryDB documentation.
Performance and Durability
Q: What latency and throughput can I achieve with MemoryDB?
A: MemoryDB’s throughput and latency vary based on the node type, payload size, and number of client connections. MemoryDB delivers microsecond read latency, single-digit millisecond write latency, and read-after-write latency on the primary node for a cluster shard. MemoryDB can support up to 390K read and 100K write requests per second and up to 1.3 GB/s read and 100 MB/s write throughput per node (based on internal testing on read-only and write-only workloads). A MemoryDB cluster shards data across one or more nodes, enabling you to add more shards or replicas to your cluster to increase aggregate throughput.
Q: How does MemoryDB durably store my data?

A: MemoryDB stores your entire data set in memory and uses a distributed Multi-AZ transactional log to provide data durability, consistency, and recoverability. By storing data across multiple AZs, MemoryDB has fast database recovery and restart. By also storing the data in-memory, MemoryDB can deliver ultra-fast performance and high throughput.

Q: How is MemoryDB’s durability functionality different from open source Redis’ append-only file (AOF)?

A: MemoryDB leverages a distributed transactional log to durably store data. By storing data across multiple AZs, MemoryDB has fast database recovery and restart. Also, MemoryDB offers eventual consistency for replica nodes and consistent reads on primary nodes.

Open source Redis includes an optional append-only file (AOF) feature, which persists data in a file on a primary node’s disk for durability. However, because AOF stores data locally on primary nodes in a single availability zone, there are risks for data loss. Also, in the event of a node failure, there are risks of consistency issues with replicas.
Q: Does MemoryDB support high availability?

A: Yes, MemoryDB supports high availability. You can create a MemoryDB cluster with Multi-AZ availability with up to 5 replicas in different AZs. When a failure occurs on a primary node, MemoryDB will automatically failover and promote one of the replicas to serve as the new primary and direct write traffic to it. Additionally, MemoryDB utilizes a distributed transactional log to ensure the data on replicas is kept up-to-date, even in the event of a primary node failure. Failover typically happens in under 10 seconds for unplanned outages and typically under 200 milliseconds for planned outages.

MemoryDB uses a distributed transactional log to durably store data written to your database during database recovery, restart, failover, and eventual consistency between primaries and replicas.
Q: How is MemoryDB’s consistency different from open source Redis?

A: Open source Redis allows writes and strongly consistent reads on the primary node of each shard and eventually consistent reads from read replicas. These consistency properties are not guaranteed if a primary node fails, as writes can become lost during a failover and thus violate the consistency model.

The consistency model of MemoryDB is similar to open source Redis. However, in MemoryDB, data is not lost across failovers, allowing clients to read their writes from primaries regardless of node failures. Only data that is successfully persisted in the multi-AZ transaction log is visible. Replica nodes are still eventually consistent, with lag metrics published to Amazon CloudWatch.
Data ingestion and query
Q: How do I write data to and read data from MemoryDB?

A: To write data to and read data from your MemoryDB cluster, you connect to your cluster using one of the supported Redis clients. For a list of supported Redis clients, please see the Redis documentation. For instructions on how to connect to your MemoryDB cluster using a Redis client, see the MemoryDB documentation.
Hardware, Scaling and Maintenance
Q: What is the largest cluster I can create with MemoryDB?
A: You create a MemoryDB cluster with up to 500 nodes. This gives a maximum memory storage capacity of ~100 TB, assuming you have 250 primary nodes each with one replica for high availability (500 nodes total).

Q: Can I resize my MemoryDB cluster?

A: Yes, you can resize your MemoryDB cluster horizontally and vertically. You can scale your cluster horizontally by adding or removing nodes. You can choose to add shards to spread your dataset across more shards, and you can add additional replica nodes to each shard to increase availability and read throughput. You can also remove shards and replicas to scale-in your cluster. Additionally, you can scale your cluster vertically by changing your node type, which changes your memory and CPU resources per node. During horizontal and vertical resizing operations, your cluster continues to stay online and serve read and write requests.

Q: How do I update my MemoryDB cluster?

A: MemoryDB makes maintenance and updates easy for your cluster, and provides two different processes for cluster maintenance. First, for some mandatory updates, MemoryDB automatically patches your cluster during maintenance windows which you specify. Second, for some updates, MemoryDB utilizes service updates, which you can apply at any time or schedule for a future maintenance window. Some service updates are automatically scheduled in a maintenance window after a certain date. Cluster updates help strengthen security, reliability, and operational performance of your clusters, and your cluster continues to stay online and serve read and write requests. For more information on cluster maintenance, see the MemoryDB documentation.

Backup and Restore
Q: Can I backup my MemoryDB cluster?
A: Yes, you create snapshots to back up the data and metadata of your MemoryDB cluster. You can manually create a snapshot, or you can use MemoryDB’s automated snapshot scheduler to take a new snapshot each day at a time you specify. You can choose to retain your snapshot for up to 35 days after it is created, and MemoryDB. Snapshots are stored in Amazon S3 which is designed for 99.999999999% (11 9's) durability. Also, you can choose to take a final snapshot of your cluster when you are deleting the cluster. Furthermore, you can export MemoryDB snapshots from the service to your Amazon S3 bucket. For more information on snapshots, see the MemoryDB documentation.

Q: Can I restore my MemoryDB cluster from a snapshot?

A: Yes, you can restore your MemoryDB cluster from a snapshot when creating a new MemoryDB cluster.

Q: Can I restore my MemoryDB cluster from a Redis RDB file?

A: Yes, you can restore your MemoryDB cluster from a Redis RDB file. You can specify the RDB file to restore from when creating a new MemoryDB cluster.

Q: Can I migrate data from ElastiCache for Redis to my MemoryDB cluster?

A: Yes, you can migrate data from ElastiCache for Redis to MemoryDB. First, create a snapshot of your ElastiCache for Redis cluster and export it to your S3 bucket. Next, create a new MemoryDB cluster and specify the backup to restore from. MemoryDB will create a new cluster with the data and Redis metadata from the snapshot. For more information on migrating data from ElastiCache for Redis to MemoryDB, see the MemoryDB documentation.
Metrics
Q: Does MemoryDB offer operational and performance metrics for my cluster?

A: Yes, MemoryDB offers operational and performance metrics for your cluster. MemoryDB has over 30 CloudWatch metrics, and you can view these metrics in the MemoryDB console. For more information on CloudWatch metrics and MemoryDB, see the MemoryDB documentation.
Security and compliance
Q: Does MemoryDB encrypt my data?
A: Yes, MemoryDB supports encryption of your data both at-rest and in-transit. For encryption at rest, you can use AWS Key Management Service customer managed keys (CMK) or a MemoryDB provided key. With Graviton2 instances for your MemoryDB cluster, your data is encrypted in memory using always-on 256-bit DRAM encryption.

Q: How do I configure authentication and authorization for my MemoryDB cluster?

A: MemoryDB uses Redis Access Control Lists (ACLs) to control both authentication and authorization for your cluster. ACLs enable you to define different permissions for different users in the same cluster. An ACL is a collection of one or more users. Each user has a password and access string, which is used to authorize access to Redis commands and data. To learn more about ACLs in MemoryDB, see the MemoryDB documentation.

Q: Can I use MemoryDB in a VPC?

A: Yes, all MemoryDB clusters must be launched in a VPC.

Q: What compliance certification readiness does MemoryDB meet?

A: We will continue to support more compliance certifications. See here for the latest compliance readiness information.
Q: Can I get a history of Amazon MemoryDB for Redis API calls made on my account for security analysis and operational troubleshooting purposes?

Yes. To receive a history of all Amazon MemoryDB API calls made on your account, you simply turn on CloudTrail in the AWS Management Console. For more information, visit the CloudTrail home page.