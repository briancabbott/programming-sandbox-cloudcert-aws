General
Q: What is AWS Chatbot?
AWS Chatbot makes it easy to securely integrate multiple AWS services with your Slack channels and Amazon Chime chat rooms for ChatOps. With AWS Chatbot, you can receive notifications about operational events, security findings, or budget alerts right in your chat room where your entire team can see and discuss them. You can run commands from Slack to retrieve diagnostic information, invoke AWS Lambda functions, or create AWS Support cases.

Q: What kind of notifications can I get with AWS Chatbot?
You can use AWS Chatbot to receive notifications from your AWS services, like CloudWatch alarms, Health events, Security Hub findings, Budgets alerts, and CloudFormation stack events. For the full list of supported services, refer to the AWS Chatbot documentation.

Q: What kind of commands can I run with AWS Chatbot?
AWS Chatbot supports read-only commands for most AWS services. You can also initiate workflows by invoking Lambda functions and create AWS Support cases. AWS Chatbot commands use the already-familiar AWS Command Line Interface syntax.
Q: How do I get started with AWS Chatbot?
To get started with AWS Chatbot, go to the AWS Chatbot console, perform a configuration with Slack or Chime, and add AWS Chatbot to your channels or chat rooms.

Q: When should I use AWS Chatbot?
AWS Chatbot helps your entire team to stay updated on and respond to operational events, security findings, or budget alerts for applications running in your AWS accounts. If your team uses a team chat application supported by AWS Chatbot, you can configure AWS Chatbot to publish notifications and run commands in a team channel or chat room where your entire team can see and quickly act on them. For example, you can set up CloudWatch alarms to go into a “Cloud DevOps” chat room where DevOps engineers can see alarms, discuss them, and retrieve diagnostic information immediately after events occur.

Q: What’s the difference between AWS Chatbot and Amazon Lex?
Amazon Lex provides the advanced deep learning capabilities of automatic speech recognition (ASR) for converting speech to text and natural language understanding (NLU) to recognize intent and build lifelike interactions. This lets you quickly and easily build your own sophisticated, natural language, conversational bots or “chatbots.” AWS Chatbot is a pre-built interactive agent designed to monitor and interact with your AWS resources (ChatOps). With AWS Chatbot you can securely receive alerts and request diagnostic information from services such as Amazon CloudWatch and AWS GuardDuty in your Slack channel or Amazon Chime chatroom. 

Q: How much does AWS Chatbot cost?
AWS Chatbot is available at no additional charge. You only pay for the AWS resources that are used with AWS Chatbot (e.g., SNS topics, CloudWatch alarms, etc.)

Q: In which regions is AWS Chatbot available?
AWS Chatbot is a global service and can be used in all commercial AWS regions. You can combine SNS topics from multiple regions in a single AWS Chatbot configuration. Please refer to the Regional Product and Services table for details about AWS resource availability.

Q: Does AWS Chatbot support AWS CloudFormation?
You can provision Slack channel configurations using AWS CloudFormation. Provisioning Chime webhook configurations with AWS CloudFormation is not currently supported.
Chat client integrations
Q: What chat clients does AWS Chatbot support?
AWS Chatbot supports Slack and Amazon Chime. Running commands is currently only supported in Slack.

Q: How does AWS Chatbot integrate with Amazon Chime?
AWS Chatbot integrates with Amazon Chime via webhooks.

Q: How does AWS Chatbot integrate with Slack?
AWS Chatbot integrates with Slack via an AWS Chatbot Slack app that you can install to your Slack workspace from the AWS Chatbot console. The installation is performed via a click-through OAuth 2.0 flow in a browser and takes just a few seconds.

Q: What is an AWS Chatbot configuration?
An AWS Chatbot configuration is a mapping of a Slack channel or an Amazon Chime chat room with SNS topics and an IAM role.

Notifications from AWS services
Q: How does AWS Chatbot integrate with AWS services?
AWS Chatbot integrates with supported AWS services via SNS topics. You need to configure the service to publish notifications to an SNS topic and then create an AWS Chatbot configuration that maps the SNS topic to a Slack channel or an Amazon Chime chat room.

Q: How does AWS Chatbot work with Amazon CloudWatch Events?
To use CloudWatch Events for notifications from supported services with AWS Chatbot, use an SNS topic as a target for a CloudWatch Event Rule and then use that SNS topic in an AWS Chatbot configuration. For the full list of supported services, refer to the AWS Chatbot documentation.
Q: How can I see more details about the notification I received in a channel or chat room?
You can click the title of the notification to navigate to the AWS Management Console page for the notification source. For example, if you click on the title on an AWS Budgets notification, you will be taken to the budget details page for that specific budget where you can review and analyze your budget performance.

Q: Can I use AWS Chatbot to receive arbitrary notifications?
No, AWS Chatbot only supports notifications from the services listed in the documentation. Events from unsupported sources will not be delivered to chat rooms.
Q: Can I use SNS topics from multiple AWS accounts within a single AWS Chatbot configuration?
No, only SNS topics from the AWS account that hosts the AWS Chatbot configuration can be used, however, you can create Chatbot configurations in other AWS accounts and map those configurations to a single chat room. Because each AWS Chatbot configuration is linked to a separate AWS account, the configurations will be independent of each other.
Q: Can I use SNS topics from multiple regions within an AWS Chatbot configuration?
Yes, you can use SNS topics from multiple public AWS regions in the same AWS Chatbot configuration.

Q: How can I filter notifications coming via AWS Chatbot?
You can filter notifications using an SNS filter policy or CloudWatch Event Rules for events that support filtering. For other events, filtering is not available.

Q: Can I add custom formatting to AWS Chatbot notifications?
No, the AWS Chatbot notifications formatting is not customizable.

Q: Are there rate limits for AWS Chatbot?
Yes, AWS Chatbot is subject to rate limits from Slack and Amazon Chime. Refer to Slack Web API documentation and Amazon Chime webhook documentation for specific details.

Q: What should I do if the AWS service I want notifications from is not supported by AWS Chatbot?
Until AWS Chatbot supports that service, you will not be able to use it with AWS Chatbot. Please submit a request using the Feedback button in the footer of the AWS Chatbot console for consideration.

Q: How can I unsubscribe from AWS Chatbot notifications in a channel or chat room?
To unsubscribe a channel or chat room from AWS Chatbot notifications, you can remove the respective configuration. If you want to unsubscribe only some notifications from the channel or chat room, you can remove specific SNS topics from the AWS Chatbot configuration.

Q: How can I troubleshoot AWS Chatbot?
You can see the details of notification attempts and failures in Amazon CloudWatch metrics and logs. See AWS Chatbot documentation for more details on troubleshooting.
Running commands and actions
Q: How do I run a command using AWS Chatbot?
To run a command in a Slack channel, first create a Slack channel configuration using the AWS Chatbot console. To start interacting with AWS Chatbot in Slack, type @aws followed by a command using the standard AWS Command Line Interface syntax. For example, to get a list and a chart of CloudWatch Alarms, type @aws cloudwatch describe-alarms. Please refer to AWS Chatbot documentation for the limitations compared to the AWS CLI.
Q: What services are supported by AWS Chatbot?
AWS Chatbot supports commands for most AWS services and its permissions scope is defined by the IAM role used in your AWS Chatbot configurations. Regardless of the IAM role permissions, access to certain services and commands, such as AWS IAM and AWS KMS, is disabled to prevent exposing credentials in Slack channels. Please refer to AWS Chatbot documentation for details on permissions.
Q: Can I interact with AWS Chatbot using direct messages in Slack?
Direct messages are not currently supported. You can create a private channel with just yourself and AWS Chatbot and use it as a channel for direct message communication.

Q: What is a notification action?
Notification actions are shortcuts that enable you to take a quick action by clicking a button on notifications sent by AWS Chatbot. For example, CloudWatch Alarm notifications for Lambda functions and API Gateway stages have “Show logs” and “Show error logs” buttons that will display the logs for the affected resource in the Slack channel.
Q: In which chat applications can I use commands and actions?
Currently, you can use commands and actions in Slack.
Security
Q: What is the purpose of the AWS Chatbot IAM role?
AWS Chatbot configurations use IAM roles that the AWS Chatbot service assumes when making API calls and running commands on behalf of AWS Chatbot users.
Q: What policies are included in the AWS Chatbot policy templates?
Refer to the AWS Chatbot documentation for the details.