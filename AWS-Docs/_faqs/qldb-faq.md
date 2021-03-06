General
Q: What is Amazon Quantum Ledger Database?

Amazon Quantum Ledger Database (QLDB) is a purpose-built ledger database that provides a complete and cryptographically verifiable history of all changes made to your application data.

Q: How is a ledger database different from other databases?

Traditional databases allow you to overwrite or delete data, so developers use techniques such as audit tables and audit trails to help track data lineage. While these approaches can work, they require custom development, can be difficult to scale, and put the onus on the application developer to ensure all the right data is being recorded. Data in Amazon QLDB is written to an append-only journal, providing the developer with full data lineage. Moreover, data in Amazon QLDB's journal is immutable and verifiable, meaning you can trust the data in your ledger.
Q: What data should I store in a ledger database?

Amazon QLDB's features make it a natural fit for system-of-record applications – those for which data integrity, completeness, and verifiability are critical. For example, in the supply chain and logistics space, an application built on Amazon QLDB would have the entire history of changes, such as movement between carriers and across borders, available for query and analysis. In finance, system-of-record applications track critical data, such as credit and debit transactions. Instead of building complex record keeping functionality within their application, banks can use QLDB to easily store a permanent and complete record of all financial transactions.
Q: Is Amazon Quantum Ledger Database a distributed ledger or blockchain service?

Amazon QLDB is not a blockchain or distributed ledger technology. Blockchain and distributed ledger technologies focus on solving the problem of decentralized applications involving multiple parties where there can be no single entity that owns the application, and the parties do not necessarily trust each other fully. On the other hand, QLDB is a ledger database purpose-built for customers who need to maintain a complete and verifiable history of data changes in an application that they own. Amazon QLDB offers history, immutability and verifiability combined with the familiarity, scalability and ease of use of a fully managed AWS database. If your application requires decentralization and involves multiple, untrusted parties, a blockchain solution may be appropriate. If your application requires a complete and verifiable history of all application data changes, but does not involve multiple, untrusted parties, Amazon QLDB is a great fit. If you have a use case for distributed ledgers or blockchain, please see Amazon Managed Blockchain.
Q: What kind of functionality does Amazon QLDB support?

In addition to providing a complete and verifiable history of application data changes, Amazon QLDB supports transactions with ACID semantics, a flexible document data model, and a familiar SQL-like API. QLDB is also fully managed and automatically scales to meet the needs of your application with no provisioning required.
Q: How do I connect to Amazon QLDB from my application?

In order to connect to Amazon QLDB and transact with the data in the ledger, you need to use the AWS-provided QLDB driver. Follow the steps in this link to download the driver and configure a connection.
Q: How do I try Amazon QLDB?

Getting started with Amazon QLDB is easy as there are no servers to manage or capacity to provision. You can create a new ledger in minutes using the AWS Management Console, AWS Command Line Interface (CLI), an AWS CloudFormation template, or by making calls to the QLDB API.
Performance
Q: What type of performance can I expect from Amazon QLDB?

Amazon QLDB can execute 2 – 3X as many transactions than ledgers in common blockchain frameworks. Blockchain frameworks are decentralized so to execute a transaction, they require a majority of members of the network to reach consensus on the validity of the transaction. On the other hand, QLDB has a centralized design, allowing its transactions to execute without the need for multi-party consensus.
Querying
Q: What is PartiQL? How does Amazon QLDB support it?

Amazon QLDB allows you to access and manipulate your data using PartiQL, which is a new open standard query language that supports SQL-compatible access to QLDB's document-oriented data model that includes semi-structured and nested data while remaining independent of any particular data source. To learn more about PartiQL read here.
Pricing
Q. How much does Amazon QLDB cost?

For Amazon QLDB pricing, please refer to our pricing page.
Q. In which AWS regions is Amazon QLDB available?

Amazon QLDB is available in the following AWS regions: US East (N. Virginia, Ohio), US West (Oregon), Europe (Ireland, Frankfurt), and Asia Pacific (Singapore, Sydney, Seoul, Tokyo), with additional regions coming soon.
Scalability
Q. How does Amazon QLDB scale?

With Amazon QLDB, you don’t have to worry about provisioning capacity or configuring read and write limits. You create a ledger, define your tables, and QLDB automatically scales to support the demands of your application.
Q. What are the limits associated with an Amazon QLDB?

You can see the limits associated with Amazon QLDB on the AWS Service Limits page.
Backup and Restore
Q. Can I take a snapshot or backup of my ledger?

Amazon QLDB does not support a backup and restore feature as of now. At present, an export to S3 functionality is available. Using this functionality you can export the contents of your QLDB journal to S3.
Q. Can I restore my ledger to a particular point in time?

Amazon QLDB does not support a point-in-time restore feature as of now.
Availability, Durability, and Replication
Q. Is Amazon QLDB durable?

Amazon QLDB's ledger is deployed across multiple AZs with multiple copies per AZ. We maintain redundancy within the region and ensure full recovery from availability zone failures. A write is acknowledged only after being written to a durable storage in multiple AZs, and hence, QLDB is strongly durable.
Q. How does high availability work in Amazon QLDB?

Amazon QLDB is a highly available service. By default, multiple copies of your QLDB ledger are replicated across availability zones in a region. So, in the case of a zone failure you can still continue to operate QLDB.
Q. Does Amazon QLDB have cross-region replication?

Amazon QLDB does not support cross-region replication as of now. QLDB's export to S3 feature enables customers to export the contents of the QLDB journal to a S3 bucket. The S3 buckets can be configured for cross-region replication.
Security
Q: Can I use Amazon QLDB in Amazon Virtual Private Cloud (Amazon VPC)?

Amazon QLDB is integrated with AWS Private Link. Customers can create a VPC endpoint, which enables them to privately connect a VPC to supported AWS services powered by PrivateLink without requiring an internet gateway, NAT device, VPN connection, or AWS Direct Connect connection.
Q: How does authentication work with Amazon QLDB?

Amazon QLDB uses the same authentication mechanism as other AWS services. The mechanism requires a request signature to be attached to the HTTP requests (header or query string). The signature is computed using other requests fields and the AWS credentials (Access Key ID and Secret Access Key).
Q. How does encryption work in Amazon QLDB?

By default, all data in transit and at rest is encrypted. Today, Amazon QLDB does not support customer managed CMKs (Customer Master Keys). Amazon QLDB uses AWS-owned keys to encrypt customer data.
Streaming Capability
Q: How do customers get started using Amazon QLDB Streaming Capability?

1/ Create an Amazon Kinesis Data Stream (KDS): Customers create a KDS stream either by using Amazon Kinesis console or AWS SDK. They can also use an existing stream.

2/ Create an Amazon QLDB Stream: Customers create an Amazon QLDB Stream using Amazon QLDB console or AWS SDK. The following key aspects need to be configured for creating the stream:

Amazon QLDB Ledger name
Target KDS stream
IAM role that Amazon QLDB will assume, which has permissions to write the KDS stream
Start time, that specifies the clock time from which to start streaming
End time, that specifies the clock time to end streaming. Omitting this optional parameter implies a continuous stream.
3/ Consume the KDS Stream: Customers can write Kinesis applications using Kinesis services, such as Kinesis Data Firehose and Kinesis Data Analytics, to consume and process the stream. Customers can also use AWS Lambda to consume the Kinesis Data Stream records.
Q: What is QLDB Streams delivery guarantee and ordering behavior?QLDB

Amazon QLDB Streaming capability provide at-least-once delivery guarantee. Each control, block summary and revision details record generated from the journal by a QLDB Stream, is streamed to Amazon Kinesis at least once. Since duplicate records can appear in the Kinesis stream under some circumstances, customers will need to have deduplication logic in the application layer, if it is needed by the application. There are no ordering guarantees, as previous blocks and revisions can be published in the Kinesis stream out-of-order.
