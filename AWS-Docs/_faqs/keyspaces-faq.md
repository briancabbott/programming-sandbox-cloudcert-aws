General
Q: What is Amazon Keyspaces?

Amazon Keyspaces (for Apache Cassandra) is a scalable, highly available, and managed Apache Cassandra–compatible database service. With Amazon Keyspaces, you can run your Cassandra workloads on AWS by using the same Cassandra Query Language (CQL) code, Apache 2.0–licensed drivers, and tools that you use today. Amazon Keyspaces uses a modified version of Apache Cassandra. We have modified the Apache Cassandra code to allow us to run it as a managed, serverless offering. You don’t have to provision, patch, or manage servers, and you don’t have to install, maintain, or operate software. Tables can scale up and down automatically, and you pay for only the resources you use.
Q: What does “Cassandra compatible” mean?

Amazon Keyspaces is compatible with the CQL API. Amazon Keyspaces supports all the most commonly used Cassandra data-plane operations, such as creating keyspaces and tables, reading data, and writing data. Amazon Keyspaces is serverless, so you don’t have to provision, patch, or manage servers, and you don’t have to install, maintain, or operate software. With Amazon Keyspaces, there are no compaction strategies, tombstones, or garbage-collection settings to manage. Amazon Keyspaces gives you single-digit-millisecond performance. All writes in Amazon Keyspaces are replicated three times across multiple AWS Availability Zones for durability and availability.
Getting started
Q: How do I get started with Amazon Keyspaces?

To get started with Amazon Keyspaces, create a keyspace and table by using either the AWS Management Console or an Apache 2.0–licensed Cassandra driver.
Q: Do I need to change client drivers to use Amazon Keyspaces?

No. Amazon Keyspaces works with existing Apache 2.0–licensed Cassandra drivers.
Q: How do I access Amazon Keyspaces?

You can use your existing Apache 2.0–licensed Cassandra drivers and developer tools with Amazon Keyspaces. For more information, see Amazon Keyspaces Developer Guide.
Planning
Q: What is the maximum throughput an Amazon Keyspaces table can support? What is the maximum size of a table? What is the maximum number of items that can be stored in a table?

Amazon Keyspaces tables can scale up and down with virtually unlimited throughput and storage. There is no limit on the size of a table or the number of rows you can store in a table. For more information, see “Quotas” in the Amazon Keyspaces Developer Guide.
Q: What kind of performance can I expect from Amazon Keyspaces?

Amazon Keyspaces offers consistent single-digit-millisecond, server-side read and write performance, while also providing high availability and data durability.
Q: How does pricing work for Amazon Keyspaces?

Amazon Keyspaces offers both on-demand and provisioned capacity modes. With on-demand capacity mode, you pay for only the reads and writes that your application actually performs. Provisioned capacity mode helps you optimize the price of throughput if you have predictable application traffic and can forecast capacity requirements in advance. Additionally, Amazon Keyspaces charges for data storage and standard internet data transfer fees. For more information, see Amazon Keyspaces pricing.