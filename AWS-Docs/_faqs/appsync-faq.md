Q. What is AWS AppSync?

AWS AppSync is a new service that enables developers to manage and synchronize mobile app data in real time across devices and users, but still allows the data to be accessed and altered when the mobile device is in an offline state.

The service further allows developers to optimize the user experience by selecting which data is automatically synchronized to each user's device when changes are made, minimizing storage and bandwidth requirements, with a query language called GraphQL.

Using these capabilities, developers can, in minutes, build real time collaborative experiences spanning browsers, mobile apps, Alexa skills, and IoT devices that remain usable when network connectivity is lost.
Q. What types of apps can I build using the features released today? 

AWS AppSync can be used to build mobile apps that would benefit from being able to synchronize user and app data across devices, continue functioning when disconnected, and offer real-time collaboration experiences. There are applications across all verticals. Examples include:

Gaming apps with real-time scoreboards
News feeds and financial data
Customer service dashboards
Shared wallet, travel or itinerary tracking with offline usage
Social Media with content feeds and search/discovery/messaging
Dating apps with likes, messaging and geo/proximity awareness
Field service apps that need to allow for querying and CRUD operations, even when disconnected
Document collaboration
3D collaboration such as shared whiteboards
AR/VR with multiple actors (doctors in surgery with observers, teachers and students)
Multi-device (e.g., Alexa, mobile, web, IoT) and multi-modal applications (e.g., task list) that need to work offline yet reflect the same eventually consistent state
Chat apps, including presence indicators and conversation history
Q. What application developer languages are supported in AWS AppSync?

AWS AppSync SDKs support iOS, Android, and JavaScript. The JavaScript support spans web frameworks such as React and Angular as well as technologies such as React Native and Ionic. You can also use open source clients to connect to the AppSync GraphQL endpoint for using other platform such as generic HTTP libraries or even a simple CURL commands.

Q. What is GraphQL ? 

GraphQL is a data language to enable client apps to fetch, change and subscribe to data from servers. In a GraphQL query, the client specifies how the data is to be structured when it is returned by the server. This makes it possible for the client to query only for the data it needs, in the format that it needs it in.
Q. What is a GraphQL Schema? 

A GraphQL schema is a definition of what data capabilities are available for the client application to operate on. For example, a schema might say what queries are available or how an app can subscribe to data without needing to know about the underlying data source. Schemas are defined by a type system, which an application's data model can leverage.
Q. Do I need to know GraphQL to get started? 

No, AWS AppSync can automatically setup your entire API, schema, and connect data sources with a simple UI builder that allows you to type in your data model in seconds. You can then immediately begin using the endpoint in a client application. The console also provides many sample schema and data sources for fully functioning applications.
Q. Can I use AWS AppSync with my existing AWS resources? 

Yes. With AWS AppSync you can use existing tables, functions, and domains from Amazon DynamoDB, AWS Lambda and Amazon Elasticsearch Service with a GraphQL schema. AWS AppSync allows you to create data sources using existing AWS resources and configure the interactions using Mapping Templates.
Q. What is a Mapping Template? 

GraphQL requests execute as "resolvers" and need to be converted into the appropriate message format for the different AWS Services that AWS AppSync integrates. For example, a GraphQL query on a field will need to be converted into a unique format for Amazon DynamoDB, AWS Lambda, and Amazon Elasticsearch Service respectively. AWS AppSync provides Mapping Templates for this, which are written in Apache Velocity Template Language (VTL) allowing you to provide custom logic to meet your needs. AWS AppSync also provides built-in templates for the different services and utility functions for enhanced usability.
Q. How is data secured with AWS AppSync? 

Application data is stored at rest in your AWS account and not in the AWS AppSync service. You can protect access to this data from applications by using security controls with AWS AppSync including AWS Identity and Access Management (IAM), as well as Amazon Cognito User Pools. Additionally, user context can be passed through for authenticated requests so that you can perform fine-grained access control logic against your resources with Mapping Templates in AWS AppSync.
Q. Can I make my data real-time with AWS AppSync?

Yes. Subscriptions are supported with AWS AppSync against any of the data sources, so that when a mutation occurs, the results can be passed down to clients subscribing to the event stream immediately using either MQTT over WebSockets or pure WebSockets.
Q. How can I do complex queries with AWS AppSync? 

The data sources available to AWS AppSync allow you to take full advantage of capabilities provided by Amazon DynamoDB, Amazon Elasticsearch Service, and AWS Lambda when using GraphQL. Features such as indexing and conditional checks, along with Mapping Templates, return comprehensive results from DynamoDB. Use cases such as fuzzy searches, geo searches and more that Amazon Elasticsearch Service offers are available to your application. Finally, Lambda can be used for serial or batched requests to return data from other sources such as Amazon Aurora.
Q. What AWS Regions are available for AWS AppSync?

AWS AppSync is available in different regions around the globe, please refer to the AWS Regions table for more details.
Q. Can I import existing Amazon DynamoDB tables? 

AWS AppSync can automatically generate a GraphQL schema from an existing DynamoDB table, including the inference of your table???s key schema and indexes. Once the import is complete GraphQL queries, mutations, and subscriptions can be used with zero coding. AppSync will also ???auto-map??? non-key attributes from your GraphQL types to DynamoDB attributes.
Q. Can AWS AppSync create a database for me? 

Customers can create a GraphQL schema, either by hand or using the console, and AWS AppSync can automatically provision Amazon DynamoDB tables and appropriate indexes for you. Additionally, it will connect the data sources to "GraphQL resolvers" allowing you to just focus on your application code and data structures.
Q. What clients can I use to connect my application to my AppSync API?

You can use any HTTP or GraphQL client to connect to a GraphQL API on AppSync. We do recommend using the Amplify clients which are optimized to connect to the AppSync backend. There are some options depending on your application's use case:

For DynamoDB data sources, use the DataStore category in the Amplify client. It provides the best developer experience and built-in conflict detection and resolution.
For non-DynamoDB data sources in scenarios where you have no offline requirements, use the API (GraphQL) category in the Amplify client.
For non-DynamoDB data sources in scenarios where you have offline requirements, use the AppSync SDK.