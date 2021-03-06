General
Q: What is time series data?

Time series data is a sequence of data points recorded over a time interval for measuring events that change over time. Examples are stock prices over time, temperature measurements over time, and the CPU utilization of an EC2 instance over time. With time-series data, each data point consists of a timestamp, one or more attributes, and the event that changes over time. This data is used to derive insights into the performance and health of an application, detect anomalies, and identify optimization opportunities. For example, DevOps engineers might want to view data that measures changes in infrastructure performance metrics, manufacturers might want to track IoT sensor data that measures changes in equipment across a facility, and online marketers might want to analyze clickstream data that captures how a user navigates a website over time. Time series data is generated from multiple sources in extremely high volumes, it needs to be cost-effectively collected in near real time, and it requires efficient storage that helps organize and analyze the data

Q: What is Amazon Timestream?

Amazon Timestream is a fast, scalable, and serverless time series database service for IoT and operational applications that makes it easy to store and analyze trillions of events per day up to 1,000 times faster and at as little as 1/10th the cost of relational databases. Amazon Timestream saves you time and cost in managing the lifecycle of time series data by keeping recent data in memory and moving historical data to a cost optimized storage tier based upon user defined policies. Amazon Timestream’s adaptive query engine lets you access and analyze recent and historical data together, without having to specify its location. Amazon Timestream has built-in time series analytics functions, helping you identify trends and patterns in your data in near real-time. Amazon Timestream is serverless and automatically scales up or down to adjust capacity and performance, so you don’t need to manage the underlying infrastructure, freeing you to focus on building your applications.

Q: How does Amazon Timestream work?

Amazon Timestream has been designed from the ground up to collect, store, and process time series data. Its serverless architecture supports fully decoupled data ingestion, storage, and query processing systems that can scale independently, enabling Amazon Timestream to offer virtually infinite scale for your application’s needs. Rather than pre-defining the schema at table creation time, a Timestream table’s schema is dynamically created based on the attributes of the incoming time series data, allowing for flexible and incremental schema definition. When stored, Amazon Timestream partitions the data by time and attributes of the data, accelerating data access using a purpose-built index. In addition, Amazon Timestream automates data lifecycle management by offering an in-memory store for recent data, a magnetic store for historical data, and by supporting configurable rules to automatically move data from the memory store to the magnetic store as it reaches a certain age. Amazon Timestream also simplifies data access through its purpose-built adaptive query engine that can seamlessly access and combine data across storage tiers without having to specify the data location, so you can quickly and easily derive insights from your data using SQL. Lastly, Amazon Timestream works seamlessly with your preferred data collection, visualization, analytics, and machine learning services, making it easy for you to include Amazon Timestream in your time series solutions.

Q: How do I get started with Amazon Timestream?

You can get started with Amazon Timestream using the AWS management console, CLI, or SDKs. For more information, including tutorials and other getting started content, please see the developer guide.
Pricing and availability
Q: How much does Amazon Timestream cost?

With Amazon Timestream, you pay only for what you use. You are billed separately for writes, data stored, and data scanned by queries. Amazon Timestream automatically scales your writes, storage, and query capacity based on usage. You can set the data retention policy for each table and choose to store data in an in-memory store or magnetic store. For detailed pricing, see the pricing page.

Q: In what regions is Amazon Timestream available?

For current region availability, see the pricing page.
Performance and scale
Q: What performance can I expect from Amazon Timestream?

Amazon Timestream offers near real-time latencies for data ingestion. Amazon Timestream’s built-in memory store is optimized for rapid point-in-time queries and the magnetic store is optimized to support fast analytical queries. With Amazon Timestream, you can run queries that analyze tens of gigabytes of time series data from the memory store within milliseconds, and analytical queries that analyze terabytes of time series data from the magnetic store within seconds. As your applications continue to send more data, Amazon Timestream automatically scales to accommodate the data ingestion and query needs of your application. You can store petabytes of data in a single table or store your data over tens of thousands of tables. As your data grows over time, Amazon Timestream leverages its distributed architecture and massive amounts of parallelism to process larger and larger volumes of data while keeping query latencies almost unchanged.

Q: How does Amazon Timestream scale?

Amazon Timestream’s serverless architecture supports fully decoupled data ingestion, storage, and query processing systems that can scale independently, enabling Amazon Timestream to offer virtually infinite scale for your application’s needs.

Q: What are the current limits and quotas?
For current limits and quotas, see the documentation.
Data ingestion
Q: How can I send data to Amazon Timestream?

You can collect time series data from connected devices, IT systems, and industrial equipment, and write it into Amazon Timestream. You can send data to Amazon Timestream using data collection services such as AWS IoT Core, Amazon Kinesis Data Analytics for Apache Flink, or Telegraf, or through the AWS SDKs. For more information, see the documentation.

Q: Do I need to define a schema before sending data to Amazon Timestream?

No. Amazon Timestream dynamically creates a table’s schema based on a set of dimensional attributes and measures. This offers flexible and incremental schema definition that may be adjusted at any time without affecting availability.

Q: How do I deal with late arrival data?

Incoming writes must land in the memory store, so memory store retention should be set using the user-configurable policies to cover a time range that is sufficient for processing any anticipated late arrival data

Q: What is the time stamp used by Amazon Timestream when ingesting data?

Amazon Timestream uses the timestamp of the time series event being written into the database. It supports timestamps with nanosecond granularity.

Q: How can I send data to Amazon Timestream using AWS IoT Core?

You can collect data from your IoT devices and store that data in Amazon Timestream using AWS IoT Core rule actions. For more detailed information, see the documentation.

Q: How can I send data to Amazon Timestream using AWS Lambda?

You can create AWS Lambda functions that interact with Amazon Timestream. For more detailed information, see the documentation.

Q: How can I send data to Amazon Timestream using Amazon Kinesis?

You can use Apache Flink to send your time series data from Amazon Kinesis directly into Amazon Timestream. For more detailed information, see the documentation.

Q: How can I send data to Amazon Timestream using Amazon Kinesis Data Analytics?

You can use Apache Flink to transfer your time series data from Amazon Kinesis Data Analytics directly into Amazon Timestream. For more detailed information, see the documentation.

Q: How can I send data to Amazon Timestream using Amazon MSK?

You can use Apache Flink to send your time series data from Amazon MSK directly into Amazon Timestream. For more detailed information, see the documentation.

Q: How can I send data to Amazon Timestream using open source Telegraf?

You can send time series data collected using open source Telegraf directly into Amazon Timestream using the Telegraf connector. For more detailed information, see the documentation.
Data storage
Q: How does Amazon Timestream store data?

Amazon Timestream organizes and stores time series data using is timestamp and it organizes data across time based on its dimensional attributes. Amazon Timestream supports an in-memory store for accepting and processing the incoming time series data and a magnetic store for historical data. Using Amazon Timestream, you can automate data lifecycle management by simply configuring data retention policies to automatically move data from the memory store to the magnetic store as it reaches the configured age.

Q: What are the benefits of the memory store?

Amazon Timestream’s memory store is a write-optimized store that accepts and deduplicates the incoming time series data. It also accepts and processes late arriving data from devices and applications with intermittent connectivity. The memory store is also optimized for latency sensitive point-in-time queries.

Q: What are the benefits of the magnetic store?

Amazon Timestream’s magnetic store is a read-optimized store that contains historical data. The magnetic store is also optimized for fast analytical queries that scan hundreds of terabytes of data.
Data access, analytics, and machine learning
Q: How can I query data with Amazon Timestream?

You can use SQL to query your time series data stored in Amazon Timestream. You can also conduct time series analytics functions for interpolation, regression, and smoothing using SQL. For more information, see the documentation.

Q: Can I use a JDBC driver with Amazon Timestream?

You can use a JDBC deriver to connect Amazon Timestream to your preferred business intelligence tools and other applications. See the documentation for additional details.

Q: What visualization, analytics, and machine learning tools can I use with Amazon Timestream?

You can visualize and analyze time series data in Amazon Timestream using Amazon QuickSight and Grafana. You can also use Amazon SageMaker with Amazon Timestream for your machine learning needs.

Q: How do I use Amazon Timestream with Amazon QuickSight?

You can create rich and interactive dashboards for your Amazon Timestream time series data using Amazon QuickSight. For more information, see the documentation.

Q: How do I use Amazon Timestream with Grafana?

You can visualize your Amazon Timestream time series data and create alerts using Grafana, a multi-platform, open source analytics and interactive visualization tool. To learn more and find sample applications, see the documentation.

Q: How do I use Amazon Timestream with Amazon SageMaker?

You can use Amazon SageMaker notebooks to integrate your machine learning models with Amazon Timestream. For more information, see the documentation.
Availability
Q: What availability does Amazon Timestream have?

Amazon Timestream provides 99.99% availability. Please refer to the service level agreement (SLA).
Security and compliance
Q: Does Amazon Timestream support data encryption?

In Amazon Timestream, data is always encrypted, whether at rest or in transit. Amazon Timestream also enables you to specify an AWS KMS customer managed key (CMK) for encrypting data in the magnetic store.

Q: What compliance certification readiness does Amazon Timestream meet?

We will continue to support more compliance certifications. See here for the latest compliance readiness information.

Q: Can I use Amazon Timestream in a VPC?

Not today. Support for VPCs will be added soon.