General AWS Cost & Usage Report FAQs
Q: How can I get started using the AWS Cost & Usage Report?

The AWS Cost & Usage Report is your one-stop shop for accessing the most detailed information available about your AWS costs and usage. The AWS Cost & Usage Report can be generated at an hourly, daily, or monthly granularity. You can enable the AWS Cost & Usage Report from the Cost & Usage Reports page in the Billing Console. Please note that in order to receive the AWS Cost & Usage Report, you will need to create and configure an Amazon S3 bucket.

This CUR data is stored in a CSV (GZIP) or Parquet format in your selected S3 bucket. We suggest turning on versioning for the S3 bucket to avoid losing data. In case for large volume of data, you can select options such as Redshift, Athena or QuickSight to help manage and query data that you need.
For more information about the AWS Cost & Usage Report, please reference the Cost & Usage Report Data Dictionary. You can enable the AWS Cost & Usage Report from here.
Q: What else can I do with the AWS Cost & Usage Report?

When setting up an AWS Cost & Usage report, you can select the option to integrate with Amazon Athena. From there, you can use the AWS CloudFormation template that’s delivered along with the Athena-compatible Parquet files to automate an integration with Athena. This will ensure that your latest cost and usage information is always available in Amazon Athena – with no additional work required to prepare your data for analysis.

The AWS Cost & Usage Report can also be automatically uploaded into Amazon Redshift and/or Amazon QuickSight. In order for this to work, ensure that you select the option during setup to integrate with Amazon Redshift or Amazon QuickSight to receive your reports in the right format.

Features FAQs
Q: How do you determine the granularity of CUR?

It can depend on how much detail you need in your report. It is possible to choose the granularity of your data by selecting hourly, daily or monthly. Choosing “hourly” will time your data collection frequency by 24. The hourly granularity gives a more in-depth look at usage, such as EC2, enabling you to view spikes and trends in your data. However, this will increase the data volume in your CUR, and the data storage cost.

Q: What are Cost Allocation Tags in CUR?

These are tags that you define in your billing console which will be brought into your CUR file. For example, you can look up for costs per application, per environment or per team, all utilizing tags. This gives you the ability to translate your data to the way your teams think about their applications and get the most out of it. While we recommend having the tags set up before you create the CUR to allow this data to be picked up by the report and add an extra level of detail to your data, you can add cost allocation tags at any point.

Q: Who can set-up a Cost & Usage Report?

Permissions to set-up a Cost & Usage Report are governed by IAM policies, as are all billing and cost management permissions. In the IAM console, you can attach an existing policy (Billing – Cost and Usage Report) to an IAM user that you want to be able to set up or delete a Cost & Usage Report. IAM users without that permission will not be able to set up a Cost & Usage Report and it requires active opt-in. You can learn more about permissions for billing and the Cost & Usage Report here.

If you are the management account administrator of an AWS Organization and do not want any of the member accounts in your Organization to set up a Cost & Usage Report you can use Service Control Policies (SCPs) to prevent certain or all member accounts from being able to do so.