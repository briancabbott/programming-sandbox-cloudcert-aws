Q: What is Amazon MWAA?

Amazon Managed Workflows for Apache Airflows (MWAA), is a managed Apache Airflow service used to extract business insights across an organization by combining, enriching, and transforming data through a series of tasks called a workflow. Managed Workflows free you from managing, configuring, and scaling the Airflow environment while you orchestrate data processing workflows and manage their execution through AWS-backed logging and monitoring capabilities. You can run your existing Airflow workflows on Amazon MWAA and interact with their environment programmatically using the AWS console, API, and command line interface (CLI).

Q: When should I use Managed Workflows?

You should use Amazon MWAA to spend more engineering/data science time building workflows and less time managing the infrastructure and Airflow environment, all while realizing consistent performance from the managed service. Data engineering and data science teams have been using Airflow as a leading open source orchestration environment for building and executing workflows that define extract-transform-load (ETL) jobs and machine learning data pipelines. You will appreciate the Airflow’s ability to programmatically build, schedule, and monitor workflows authored in Python, the preferred language of data processing. The Airflow task plugin model and open architecture that allows you to build custom workflows including support for on-premise data sources. However, a team that wants to reap the benefits of Airflow’s programmatic interface must first configure and maintain the servers and monitoring for it to function. Many customers dedicate data engineers to manage the worker fleet, install dependencies, scale the system up and down, and restart the scheduler. Managed Workflows eliminate the need for these hands-on operations by providing you with a managed Airflow environment that is highly available, monitored, and automatically scalable.

Q: What does Amazon MWAA manage on my behalf?

Amazon MWAA manages the work involved in setting up Airflow, from provisioning the infrastructure capacity (server instances and storage) to installing the software and providing simplified user management and authorization through AWS Identity and Access Management (IAM) and Single Sign-On (SSO). Once your Airflow is up and running, Amazon MWAA scales your workers to accommodate the volume of executing workflows and automates common administrative tasks such as patching the operating system and updating the Airflow software.

Q: How does this service relate to/work with other AWS services?

Amazon MWAA is a workflow environment that allows data engineers and data scientists to build workflows using other AWS, on-premise, and other cloud services. Amazon MWAA workflows retrieve input from sources like S3 using Athena queries, perform transformations on EMR clusters, and can use the resulting data to train machine learning (ML) models on SageMaker. Workflows in Amazon MWAA are authored as Directed Acyclic Graphs (DAGs) using Python. A key benefit of Airflow is its open extensibility through plugins which allows you to create task plugins for any AWS or on-premise resources required for your workflows including Athena, Batch, Cloudwatch, DynamoDB, DataSync, EMR, ECS/Fargate, EKS, Firehose, Glue, Lambda, Redshift, SQS, SNS, Sagemaker, and S3.

Q: How will new Airflow versions, patches, and upgrades be handled?

Amazon MWAA will provide automatic minor version upgrades and patches by default, with an option to designate a maintenance window in which these upgrades are performed. The maintenance window is your opportunity to control when software patching occurs in the event they are requested or required. If a maintenance event is scheduled for a given week it will be initiated and completed at some point during the maintenance window you identify. Maintenance windows are 2 hours in duration.

Q: How do I monitor my Amazon MWAA service and exeution of workflows?

Amazon MWAA will provide access to available Airflow environments via the AWS management console, AWS CLI, and SDK. The Airflow user interface can be configured for direct Internet and/or VPC access. Airflow command line instructions will be available through an API call and the AWS CLI.

Q: What Airflow plugins does the service support?

Amazon MWAA will support all of the 100+ Airflow community plugins developed to date, plus any custom plugins you create, simply by placing them in an S3 bucket.

Q: How can I monitor my Amazon MWAA service and executing workflows?

You can directly access each Airflow environment through the Amazon MWAA management console and the Airflow UI. Airflow metrics will be published to Amazon CloudWatch Metrics, and logs will be published to CloudWatch Logs.

Q: When should I use Amazon MWAA vs. AWS Step Functions?

You should use Amazon MWAA if you prioritize open source and portability. Airflow has a large and active open source community that contributes new functionality and integrations regularly. Amazon MWAA supports existing Airflow workflows and integrations without changes to code, migration is easy, and the environment is familiar.

You should use Step Functions if you prioritize cost and performance. For example, if you were processing streaming data and transforming it through multiple steps before putting it in a DynamoDB database or S3, you should use Step Functions because it has higher performance at a lower cost.