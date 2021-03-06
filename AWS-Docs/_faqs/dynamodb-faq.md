What is DynamoDB?
Q: What is Amazon DynamoDB?

DynamoDB is a fast and flexible nonrelational database service for any scale. DynamoDB enables customers to offload the administrative burdens of operating and scaling distributed databases to AWS so that they don’t have to worry about hardware provisioning, setup and configuration, throughput capacity planning, replication, software patching, or cluster scaling.

Show less
Q: What does DynamoDB manage on my behalf?

DynamoDB takes away one of the main stumbling blocks of scaling databases: the management of database software and the provisioning of the hardware needed to run it. You can deploy a nonrelational database in a matter of minutes. DynamoDB automatically scales throughput capacity to meet workload demands, and partitions and repartitions your data as your table size grows. Also, DynamoDB synchronously replicates data across three facilities in an AWS Region, giving you high availability and data durability.

Show less
Q: What is the consistency model of DynamoDB?

When reading data from DynamoDB, users can specify whether they want the read to be eventually consistent or strongly consistent:

Eventually consistent reads (the default) – The eventual consistency option maximizes your read throughput. However, an eventually consistent read might not reflect the results of a recently completed write. All copies of data usually reach consistency within a second. Repeating a read after a short time should return the updated data.
Strongly consistent reads — In addition to eventual consistency, DynamoDB also gives you the flexibility and control to request a strongly consistent read if your application, or an element of your application, requires it. A strongly consistent read returns a result that reflects all writes that received a successful response before the read.
ACID transactions – DynamoDB transactions provide developers atomicity, consistency, isolation, and durability (ACID) across one or more tables within a single AWS account and region. You can use transactions when building applications that require coordinated inserts, deletes, or updates to multiple items as part of a single logical business operation.
Show less
Getting started
Q: What kind of query functionality does DynamoDB support?

DynamoDB supports GET/PUT operations by using a user-defined primary key. The primary key is the only required attribute for items in a table. You specify the primary key when you create a table, and it uniquely identifies each item. DynamoDB also provides flexible querying by letting you query on nonprimary key attributes using global secondary indexes and local secondary indexes.

A primary key can be either a single-attribute partition key or a composite partition-sort key. A single-attribute partition key could be, for example, UserID. Such a single attribute partition key would allow you to quickly read and write data for an item associated with a given user ID.

DynamoDB indexes a composite partition-sort key as a partition key element and a sort key element. This multipart key maintains a hierarchy between the first and second element values. For example, a composite partition-sort key could be a combination of UserID (partition) and Timestamp (sort). Holding the partition key element constant, you can search across the sort key element to retrieve items. Such searching would allow you to use the Query API to, for example, retrieve all items for a single UserID across a range of time stamps.

Show less
Q: How do I update and query data items with DynamoDB?

After you have created a table using the DynamoDB console or CreateTable API, you can use the PutItem or BatchWriteItem APIs to insert items. Then, you can use the GetItem, BatchGetItem, or, if composite primary keys are enabled and in use in your table, the Query API to retrieve the items you added to the table.

Show less
Q: Can DynamoDB be used by applications running on any operating system?

Yes. DynamoDB is a fully managed cloud service that you access via API. Applications running on any operating system (such as Linux, Windows, iOS, Android, Solaris, AIX, and HP-UX) can use DynamoDB. We recommend using the AWS SDKs to get started with DynamoDB.

Show less
Planning
Q: How am I charged for my use of DynamoDB?

Each DynamoDB table has provisioned read-throughput and write-throughput associated with it. You are billed by the hour for that throughput capacity if you exceed the free tier. Note that you are charged by the hour for the throughput capacity, whether or not you are sending requests to your table. If you would like to change your table’s provisioned throughput capacity, you can do so using the AWS Management Console, the UpdateTable API, or the PutScalingPolicy API for auto scaling. Also, DynamoDB charges for data storage as well as the standard internet data transfer fees.

To learn more about DynamoDB pricing, see the DynamoDB pricing page.

Show less
Q: What is the maximum throughput I can provision for a single DynamoDB table?

Maximum throughput per DynamoDB table is practically unlimited. For information about the limits in place, see Limits in DynamoDB. If you want to request a limit increase, contact Amazon.  

Show less
Q: What is the minimum throughput I can provision for a single DynamoDB table?

The smallest provisioned throughput you can request is 1 write capacity unit and 1 read capacity unit for both auto scaling and manual throughput provisioning. Such provisioning falls within the free tier which allows for 25 units of write capacity and 25 units of read capacity. The free tier applies at the account level, not the table level. In other words, if you add up the provisioned capacity of all your tables, and if the total capacity is no more than 25 units of write capacity and 25 units of read capacity, your provisioned capacity would fall into the free tier.

Show less
How it works
Q:  Data models and APIs

For more information about data models and APIs, see Amazon DynamoDB: How It Works.
Show less
Q: Scalability, availability, and durability

For information about scalability, availability, and durability, see Amazon DynamoDB Product Details.

Show less
Q: Auto scaling

For information about DynamoDB auto scaling, see Managing Throughput Capacity Automatically with DynamoDB Auto Scaling.

Show less
Q: Security and control

For information about DynamoDB security and control, see Authentication and Access Control for Amazon DynamoDB.

Show less