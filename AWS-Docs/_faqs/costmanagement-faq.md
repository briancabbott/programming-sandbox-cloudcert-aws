General
Q: Who should use the AWS Cost Management products?
We have yet to meet a customer who does not consider cost management a priority. AWS Cost Management tools are used by IT professionals, financial analysts, resource managers, and developers across all industries to access detailed information related to their AWS costs and usage, analyze their cost drivers and usage trends, and take action on their insights.
Getting Started
Q: How do I get started with the AWS Cost Management tools?
The quickest way to get started with the AWS Cost Management tools is to access the Billing Dashboard. From there, you can access a number of products that can help you to better understand, analyze, and control your AWS costs, including, but not limited to, AWS Cost Explorer, AWS Budgets, and the AWS Cost & Usage Report.
AWS Cost Explorer
Q: What are the benefits of using AWS Cost Explorer?
AWS Cost Explorer lets you explore your AWS costs and usage at both a high level and at a detailed level of analysis, and empowering you to dive deeper using a number of filtering dimensions (e.g., AWS Service, Region, Member Account, etc.) AWS Cost Explorer also gives you access to a set of default reports to help you get started, while also allowing you to create custom reports from scratch.

For more information about the breadth of AWS Cost Explorer features, please click here or refer to the Managing your Usage and Costs user guide.
Q: What kinds of default reports are available?
AWS Cost Explorer provides a set of default reports to help you get familiar with the available filtering dimensions and types analyses that can be done using AWS Cost Explorer. These reports include a breakdown of your top 5 cost-accruing AWS services, and an analysis of your overall Amazon EC2 usage, an analysis of the total costs of your member accounts, and the Reserved Instance Utilization and Coverage reports.

To access these default reports, please access Cost Explorer.

For more information about the RI Utilization report and the RI Coverage reports, please reference the Reserved Instance Reporting FAQ section.
Q: Can I create and save custom AWS Cost Explorer reports?
Yes. You can currently save up to 50 custom AWS Cost Explorer reports.
Q: What can I do with the AWS Cost Explorer API?
The AWS Cost Explorer API is the low-latency, ad-hoc query service that powers AWS Cost Explorer, and is accessible via a command-line interface and supported AWS SDKs. Using the AWS Cost Explorer API, you can build custom, interactive cost management applications without having to set up and maintain any additional infrastructure.

The AWS Cost Explorer API incurs a charge of $.01 per request. Please note that if your result set is paginated each page counts as a separate request.

To learn more about the AWS Cost Explorer API, please reference the technical documentation.
Q: When should I use AWS Compute Optimizer and when should I use AWS Cost Explorer?

You should use AWS Cost Explorer if you want to identify under-utilized EC2 instances that may be downsized on an instance by instance basis within the same instance family, and you want to understand the potential impact on your AWS bill by taking into account your RIs and Savings Plans. Cost Explorer offers recommendations for all commercial regions (outside of China) and supports the A, T, M, C, R, X, Z, I, D, H instance families.

You should use AWS Compute Optimizer if you want to look at instance type recommendations beyond downsizing within an instance family. You can use AWS Compute Optimizer to get downsizing recommendations within or across instance families, upsizing recommendations to remove performance bottlenecks, and recommendations for EC2 instances that are parts of an Auto Scaling group. AWS Compute Optimizer provides you additional capabilities to enhance recommendation quality and the user experience, such as using machine learning to identify workload types and automatically choose workload-specific recommendation methodology for them. You should also use AWS Compute Optimizer if you want to understand the performance risks and how your workload would perform on various EC2 instance options to evaluate the price-performance trade-off for your workloads. AWS Compute Optimizer is available in US East (N. Virginia), US East (Ohio), US West (Oregon), EU (Ireland), and South America (Sao Paulo), and supports the M, C, R, T and X instance families.
AWS Cost & Usage Report
Q: How can I get started using the AWS Cost & Usage Report?

The AWS Cost & Usage Report is your one-stop shop for accessing the most detailed information available about your AWS costs and usage. The AWS Cost & Usage Report can be generated at an hourly, daily, or monthly granularity.

For more information about the AWS Cost & Usage Report, please reference the Cost & Usage Report Data Dictionary. You can enable the AWS Cost & Usage Report from here.
Q: How can I get started using the AWS Cost & Usage Report?

You can enable the AWS Cost & Usage Report from the Cost & Usage Reports page in the Billing Console. Please note that in order to receive the AWS Cost & Usage Report, you will need to create and configure an Amazon S3 bucket.
Q: How frequently is the AWS Cost & Usage Report updated?

The AWS Cost & Usage Report is updated at least once per day.
Q: What else can I do with the AWS Cost & Usage Report?

When setting up an AWS Cost & Usage report, you can select the option to integrate with Amazon Athena. From there, you can use the AWS CloudFormation template that’s delivered along with the Athena-compatible Parquet files to automate an integration with Athena. This will ensure that your latest cost and usage information is always available in Amazon Athena – with no additional work required to prepare your data for analysis.

The AWS Cost & Usage Report can also be automatically uploaded into Amazon Redshift and/or Amazon QuickSight. In order for this to work, ensure that you select the option during setup to integrate with Amazon Redshift or Amazon QuickSight to receive your reports in the right format.
Q: Who can set-up a Cost & Usage Report?

Permissions to set-up a Cost & Usage Report are governed by IAM policies, as are all billing and cost management permissions. In the IAM console, you can attach an existing policy (Billing – Cost and Usage Report) to an IAM user that you want to be able to set up or delete a Cost & Usage Report. IAM users without that permission will not be able to set up a Cost & Usage Report and it requires active opt-in. You can learn more about permissions for billing and the Cost & Usage Report here.

If you are the management account administrator of an AWS Organization and do not want any of the member accounts in your Organization to set up a Cost & Usage Report you can use Service Control Policies (SCPs) to prevent certain or all member accounts from being able to do so.
Reserved Instance (RI) Reporting
Q: How can I use AWS Cost Management tools to better understand the costs and usage associated with my Reserved Instances (RIs)?

There are three main ways to gain insight into the costs and usage associated with your RIs: the default RI reports in Cost Explorer, the reservation-related data in the Cost & Usage Report, and AWS Cost Explorer's RI purchase recommendations.
Q: What are some of the insights you can glean using the RI reports in Cost Explorer?

AWS Cost Explorer provides two reports out-of-the-box--the RI Utilization and RI Coverage reports--to help you understand how you are using your RIs. The RI Utilization report visualizes the degree to which you are using your existing resources and helps you identify opportunities to improve your RI cost efficiencies. The RI Coverage report allows you to discover how much of your overall instance usage is covered by RIs, so that you can make informed decisions about when to purchase or modify an RI to ensure maximum coverage.
Q: What kind of RI-related information can you gain from the Cost & Usage Report?

The Cost & Usage Report gives you access to a wealth of RI-related information, including the ARN of the Reserved Instance that received the RI discount, the total reserved units in a reservation, and pricing information. This can help you trace your RI discounts, understand how well you are using your RIs, and analyze your savings compared to the On-Demand instance usage prices.

You can learn more about the Cost & Usage Report here. You can enable the Cost & Usage Report here.
AWS Budgets
Q: What is AWS Budgets and how does it work?

Using AWS Budgets, you can set a budget that alerts you when you exceed (or are forecasted to exceed) your budgeted cost or usage amount. You can also set alerts based on your RI or Savings Plans Utilization and Coverage using AWS Budgets.
Learn more about AWS Budgets here, or reference the Monitoring your Usage and Costs user guide.
Q: What kinds of dimensions can be used to create a budget?

AWS Budgets gives you access to a number of filtering dimensions (i.e., AWS Service, Availability Zone, and Member Account), and allows you to create budgets that are tracked on a monthly, quarterly, or yearly cadence. Learn more about budgets dimensions and filters here.
Q: How many budgets can I create?

You can create up to 20,000 budgets. If you would like to increase your limit, please reach out to Customer Support. Learn more about AWS Budgets Limits and Restrictions.
Q: How many alerts and subscribers can I add for each budget?

For each budget, you are allowed to create up to five alerts. Each alert can be sent to 10 email subscribers and/or be published to an SNS topic.
Q: Is there a cost associated with using AWS Budgets?

Budgets without actions are free. You can create 2 actions-enabled budgets for free. Any additional active budgets accrue a cost that can be reviewed here.
AWS Cost Anomaly Detection
Q: What is AWS Cost Anomaly Detection and how does it work?

Cost Anomaly Detection helps you detect and alert on any abnormal or sudden spend increases in your AWS account. This is possible by using machine learning to understand your spend patterns and trigger alert as they seem abnormal.

Learn more about Cost Anomaly Detection from the product page, and the user guide. To learn more about programmatic capabilities, read the AWS Cost Explorer API documentation.
Q: How can I customize monitors to evaluate for anomalies?

Cost Anomaly Detection allows you to segment your spend by different dimensions (AWS Services, Linked Accounts, Cost Allocation Tags, and Cost Categories). This segmentation allows Anomaly Detection to detect more granular anomalies and customize alerting preferences.
Q: How many monitors can I create?

Cost Anomaly Detection allows you to create up to 101 monitors. There is a limit of 1 AWS Service monitor (which evaluates all of AWS Services separately) and up to 100 monitors for a combination of Linked Accounts, Cost Allocation Tags, and Cost Categories monitors.

Q: How many subscribers can I add to each monitor?

For each monitor, you can have up to 10 email recipients or 1 SNS topic.
Q: Is there a cost associated with using AWS Cost Anomaly Detection?

This service is provided free of charge. However, depending on your delivery settings, you may incur a charge, e.g. for SNS.
AWS Purchase Order Management
Q: What is AWS Purchase Order Management and how does it work?

AWS Purchase Order Management gives you the ability to define and manage your purchase orders (POs) for AWS services in a way that meets your unique business needs. You can configure multiple POs and define the rules of how they map to your invoices through PO line item configurations. You can define separate POs for different time periods, invoices, and AWS seller entities. You can also track the status as well as balance of your POs, and configure email contacts to receive PO balance tracking and expiration notifications. You have complete control to update your PO configuration at any time.
Learn more about AWS Purchase Order Management here, or reference the Managing your Purchase Orders user guide.

Q: What are purchase order line items?

Purchase order line items give you the flexibility to define various PO configurations according to your needs. By selecting different line item start and end periods, as well as line item types, you can define multiple configurations to match your POs to invoices, as well as track balances over different time periods and invoice types. To learn more, see Setting up purchase order configurations.
Q: How does purchase order balance tracking work?

Purchase order balance tracking is a feature that enables you to report and track the balance of your POs against your invoiced amounts. When adding/editing your PO details, you have the option to enable balance tracking and input amounts for your PO line items. Whenever an invoice is generated and matched with your PO, the balance of the corresponding line item as well as your PO will be reduced. If you have configured contacts on your PO, they will receive email notifications when the PO line item balance falls below a 75% threshold.
Q: Will my purchase order no longer be used for invoices once it runs out of
balance?

Your invoices are matched to your POs based on various criteria, such as effective and expiration periods, AWS seller entity (“Bill from”), line item type (e.g. AWS subscription, AWS Marketplace, AWS Monthly usage, or ALL), and line item start and end periods. PO balance is not an important criteria used for determining invoice association. When your PO runs out of balance, and in case you have not taken any action, such as updating the balance or adding a different PO, your PO will continue being associated with the same types of invoices as before.
Q: What are purchase order notifications?

You can configure contacts on your POs to receive email notifications for your POs running out of balance or nearing expiration. PO notifications enable you to proactively take actions to ensure the validity of your POs, and achieve on-time and accurate payments.
Q: What is purchase order status management?

You can easily track the status of your POs on the Purchase Orders dashboard. When adding/updating your PO, you can input its effective and expiration periods. Your PO is Active during this time period and is used for matching with invoices. Once your PO is past its expiration date, it’s status is automatically updated to Expired and it is no longer used for your invoices.

If you want to pause using an Active PO for your invoices, you can update its status to Suspended at any time by choosing Change status from your Purchase Order Details page. Suspended POs are not used for invoice association. You can change the status back to Active at any time to activate the PO for invoicing. This feature is helpful if you want to use a one-time PO for a specific purchase. You can do so by adding your one-time PO and suspending your other active POs. Once your purchase is complete and invoice is generated with your one-time PO, you can again activate your other POs, and suspend (or delete) the one-time PO.
Q: How many purchase orders can I add?

You can add up to 100 active purchase orders with up to 100 line items for each purchase order.
Q: How many email contacts can I configure to receive PO alerts?

You can add up to 10 email contacts for each purchase order.
Q: Is there a cost associated with using this feature?

No, the feature is provided free of charge.
Q: Can I update my invoicing and payment terms using this feature?

AWS Purchase Order Management is provided by AWS for your convenience. Any use of AWS Purchase Order Management does not modify the agreement between you and AWS governing your access or use of AWS services. For any questions related to payment terms, please reach out to Customer Support.

AWS Cost Categories
Q: What is AWS Cost Categories and how does it work?

Using AWS Cost Categories, you can group your cost and usage information into meaningful categories based on your business needs. You can create custom categories and map your cost and usage information into these categories based on the rules you define using various dimensions, such as, account, tag, service, charge type, and other cost categories. Once Cost Categories are set up, you can use them across various products in the AWS Billing and Cost Management console. This includes AWS Cost Explorer, AWS Budgets, AWS Cost and Usage Reports (AWS CUR), and AWS Cost Anomaly Detection. A Cost Category comprises the following components:

Cost Category name – A unique perspective that is meaningful to your business (Example: Cost Center, Team, Application)
Cost Category value – The groupings within your Cost Category (Example: Alpha and Beta for “Team” Cost Category; FinOps, Engineering, and Marketing for “Cost Center” Cost Category)
Dimensions – The dimensions you can use to create your cost category rules (Example: accounts, tags, service, charge types, and other cost categories)
Cost Category rules – A Cost Category rule comprises one or more dimensions that are used to categorize your costs into a Cost Category value.

Learn more about Cost Categories from the product page, and the user guide. To learn more about programmatic capabilities, read the AWS Cost Explorer API documentation.

Q: When should I create a Cost Category vs a Cost Category value?

Organizations have multiple perspectives on their business, such as projects, cost centers, applications, teams etc. A Cost Category is a unique perspective of your business that contains multiple groups of category values. For instance, if your business is organized by teams, you can create a cost category named Team. Then, you can map your costs to cost category values Team Alpha and Team Beta by selecting appropriate dimensions in the rule builder.
Cost Category values are mutually exclusive, but rules are not, so you can write multiple rules that map your costs to a particular Cost Categories value. For instance, one rule can map account ABC and account XYZ using Account dimension into Team Alpha, and another rule can use the Tag dimension to map tag key owner with tag value as Alpha-owners into Team Alpha. Both of these rules can be used to categorize your costs into Team Alpha.
Q: How does Cost Categories work?

Cost Categories uses a rule-based engine to categorize your cost and usage information. When your bill is computed (which happens multiple times every day), your costs are categorized to the values within each of your Cost Category based on the rules that you define. For example, consider you have three Cost Categories – Teams, Departments, and Cost Centers; your costs will be categorized based on your rules for each of your Cost Category into its values. Your Cost Category name will appear as a new column in your AWS Cost and Usage Report (CUR), and each row of your billing line item will be assigned the appropriate Cost Category value. 

Your Cost Category name will also appear as a filter in Cost Management products such as AWS Cost Explorer, AWS Budgets, and AWS Cost Anomaly Detection, with the corresponding Cost Category values as filter options. In this example, you will see three new columns in your CUR (Teams, Departments, and Cost Centers) and corresponding filters on other Cost Management products.
Q: What is an Inherited Value rule?

Inherited Value provides you the flexibility of defining a rule that dynamically inherits the Cost Category value from the dimension value defined. For example, if you want to dynamically group costs based on the value of a specific tag key, you can first choose the inherited value rule type, then choose the Tag dimension and specify the tag key to use. For instance, you can use a tag key, Teams, to tag your resources with values as alpha, beta, and gamma. Then, with an inherited value rule, you could select Tag as the dimension and specify teams as the tag key. This will dynamically generate alpha, beta, and gamma as Cost Category values.
Q: What is a Default value?

Any costs that are not captured in your Cost Category rules remain uncategorized. These costs show up on your AWS Cost and Usage Report with an empty value, and on your Cost Explorer with a “No Cost Category” label. You can use Default Value to assign a contextually meaningful name to uncategorized costs. For example, for your Cost Categories Teams you can define the default value as other teams and reference it on all Cost Management products.
Q: What is the JSON Editor and why should I use it?

You have two ways to define your Cost Categories in your AWS Billing and Cost Management Console – the GUI based Rule builder or the JSON editor. The Rule builder supports static GUI based components and contains only the AND logical operator to add dimensions to your rules. Using the JSON editor, you can write more complex rules with nested conditions, and use additional logical operators such as NOT and OR besides AND. Refer to API documentation for the JSON format to use with JSON editor
Q: How many Cost Categories can I create?

You can create up to 50 Cost Categories. With the Rule builder, you can create up to 100 rules per Cost Category, and with the JSON editor, you can create up to 500 rules per Cost Category. For more details on service limits, refer to the user guide.
Q: Can I create nested or hierarchical Cost Categories?

Yes, you can create multilevel hierarchical relationships among your cost categories by using Cost Category as a dimension to select other categories when defining a Cost Category. For example, if your organization comprises multiple cost centers spanning across several departments, with each department itself containing multiple teams. You can easily set up Teams, Departments, and Cost Centers as hierarchical Cost Categories to track your cost and usage at every level.
Q: What are Split Charge Rules?

Every organization has a set of costs that are shared by multiple teams, business units, or financial owners, for instance, data transfer costs, enterprise support, or operational costs of a centralized infrastructure team. These costs are not directly attributable to a singular owner, and hence cannot be categorized into a singular cost category value. With Split Charge rules, you can equitably allocate these charges across your Cost Category values.

Defining Split Charge rules is an optional step when you create or edit your Cost Categories. A Split Charge rule consists of a source, one or more targets, and an allocation method.

Source: These are the group of shared costs that you want to split. Source can be any of your existing Cost Category values
Targets: These are the Cost Category values across which you want to split your shared costs defined by the source
Charge allocation method: This is how you want your source costs to be split across your targets. You can choose from three allocation methods: proportional, fixed, or even split. Proportional method allocates costs across your targets based on the proportional weighted cost of each target. Fixed method allows you to input a user-defined allocation percentage to compute the splits. Even split allocates costs evenly across all targets.

Q: Will Split Charge Rules introduce new line items in my Cost and Usage Report (CUR)?

Split charge rules as well as the resultant cost allocations are only presented within Cost Categories and are not surfaced in other Cost Management products such as AWS Cost Explorer, AWS Budgets, and AWS Cost Anomaly Detection. You can view your cost allocations before and after split charges are applied on the Cost Categories details page and download a CSV report of your cost allocations.

Q: Is there a cost associated with using AWS Cost Categories?

This service is provided free of charge.