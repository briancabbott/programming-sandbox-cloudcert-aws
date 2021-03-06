Overview
Q: What is AWS Step Functions?

AWS Step Functions is a fully managed service that makes it easy to coordinate the components of distributed applications and microservices using visual workflows. Building applications from individual components that each perform a discrete function lets you scale easily and change applications quickly. Step Functions is a reliable way to coordinate components and step through the functions of your application. Step Functions provides a graphical console to arrange and visualize the components of your application as a series of steps. This makes it simple to build and run multi-step applications. Step Functions automatically triggers and tracks each step, and retries when there are errors, so your application executes in order and as expected. Step Functions logs the state of each step, so when things do go wrong, you can diagnose and debug problems quickly. You can change and add steps without even writing code, so you can easily evolve your application and innovate faster.

Q: What are the benefits of designing my application using orchestration?

Breaking an application into service components (or steps) ensures that the failure of one component does not bring the whole system down, that each component scales independently, and that components may be updated without requiring the entire system to be redeployed after each change. The coordination of service components involves managing execution dependencies, scheduling, and concurrency in accordance with the logical flow of the application. In such an application, developers may use service orchestration to do this and to handle failures.

Q: What are some common AWS Step Functions use cases?

AWS Step Functions helps with any computational problem or business process that can be subdivided into a series of steps. It’s also useful for creating end-to-end workflows to manage jobs with interdependencies. Common use cases include:

Data processing: consolidate data from multiple databases into unified reports, refine and reduce large data sets into useful formats, or coordinate multi-step analytics and machine learning workflows
DevOps and IT automation: build tools for continuous integration and continuous deployment, or create event-driven applications that automatically respond to changes in infrastructure
E-commerce: automate mission-critical business processes, such as order fulfillment and inventory tracking
Web applications: implement robust user registration processes and sign-on authentication
For more details, explore AWS Step Functions use cases and customer testimonials.

Q: How does AWS Step Functions work?

Using AWS Step Functions, you define state machines that describe your workflow as a series of steps, their relationships, and their inputs and outputs. State machines contain a number of states, each of which represents an individual step in a workflow diagram. States can perform work, make choices, pass parameters, initiate parallel execution, manage timeouts, or terminate your workflow with a success or failure. The visual console automatically graphs each state in the order of execution, making it easy to design multi-step applications. The console highlights the real-time status of each step and provides a detailed history of every execution. For more information, see How Step Functions Works in the AWS Step Functions Developer Guide.

Q: How does AWS Step Functions connect to my resources?

You can configure your state machines to perform work by using activity tasks and service tasks. Activity tasks let you assign a specific step in your workflow to code running somewhere else (known as an activity worker). An activity worker can be any application that can make an HTTP connection, hosted anywhere. For example, activity workers can run on an Amazon EC2 instance, on a mobile device, or on an on-premises server. The activity worker polls Step Functions for work, takes any inputs from Step Functions, performs the work using your code, and returns results. Since activity workers request work, it is easy to use workers that are deployed behind a firewall.

Service tasks let you connect a step in your workflow to a supported AWS service. Step Functions pushes requests to other services so they can perform actions for your workflow, waits for the service task to complete, and then continues to the next step.

An AWS Step Functions state machine can contain combinations of activity tasks and service tasks. AWS Step Functions applications can also combine activity workers running in a data center with service tasks that run in the cloud. The workers in the data center continue to run as usual, along with any cloud-based service tasks.

Q: How do I get started with AWS Step Functions?

There are a number of ways you can get started with AWS Step Functions:

Explore sample projects in the Step Functions console
Read through the AWS Step Functions Developer Guide
Try our 10-minute Tutorials
Q: What language does AWS Step Functions use?

AWS Step Functions state machines are defined in JSON using the declarative Amazon States Language. To create an activity worker, you may use any programming language, as long as you can communicate with AWS Step Functions using web service APIs. For convenience, you may use an AWS SDK in the language of your choosing. AWS Lambda supports code written in Node.js (JavaScript), Python, Golang (Go), and C# (using the .NET Core runtime and other languages). For more information on the Lambda programming model, see the AWS Lambda Developer Guide.

Q: My workflow has some of the properties of Standard Workflows and some properties of Express Workflows. How do I get the best of both?

You can compose the two workflow types: Express Workflows can run as a child workflow of Standard Workflows. The Express Workflow is invoked from a Task state in the parent orchestration workflow and succeeds or fails as a whole from the parent’s perspective. It is subject to the parent’s retry policy for that Task. You can also call Express Workflows from within an Express Workflow, so long as all workflows do not exceed the duration limit of the parent. You might choose to factor your workflows this way if your use case has a combination of long-running or exactly-once, and short-lived high-rate steps. 

Comparisons
Q: When should I use AWS Step Functions vs. Amazon SQS?

You should consider AWS Step Functions when you need to coordinate service components in the development of highly scalable and auditable applications. You should consider using Amazon Simple Queue Service (Amazon SQS), when you need a reliable, highly scalable, hosted queue for sending, storing, and receiving messages between services. Step Functions keeps track of all tasks and events in an application. Amazon SQS requires you to implement your own application-level tracking, especially if your application uses multiple queues. The Step Functions Console and visibility APIs provide an application-centric view that lets you search for executions, drill down into an execution’s details, and administer executions. Amazon SQS requires implementing such additional functionality. Step Functions offers several features that facilitate application development, such as passing data between tasks and flexibility in distributing tasks. Amazon SQS requires you to implement some application-level functionality. While you can use Amazon SQS to build basic workflows to coordinate your distributed application, you can get this facility out-of-the-box with Step Functions, alongside other application-level capabilities.

Q: When should I use AWS Step Functions vs. Amazon Simple Workflow Service (SWF)?

You should consider using AWS Step Functions for all your new applications, since it provides a more productive and agile approach to coordinating application components using visual workflows. If you require external signals to intervene in your processes, or you would like to launch child processes that return a result to a parent, then you should consider Amazon Simple Workflow Service (Amazon SWF). With Amazon SWF, instead of writing state machines in declarative JSON, you write a decider program to separate activity steps from decision steps. This provides you complete control over your orchestration logic, but increases the complexity of developing applications. You may write decider programs in the programming language of your choice, or you may use the Flow framework to use programming constructs that structure asynchronous interactions for you. 

Q: When should I use Express Workflows vs. Standard Workflows?

You should use Express Workflows for workloads with high event rates and short durations. Express Workflows support event rates of more than 100,000 per second. Express Workflows have a maximum duration of five minutes. Express Workflows guarantee “at least once” execution of each workflow step. Failed workflows must be re-run from the beginning. Express Workflows support all service integrations. Express Workflows do not support activities, Job-run (.sync), and Callback patterns.

Standard Workflows on AWS Step Functions are more suitable for long-running, durable, and auditable workflows where repeating workflow steps is expensive (e.g., restarting a long-running media transcode) or harmful (e.g., charging a credit card twice). Example workloads include training and deploying machine learning models, report generation, billing, credit card processing, and ordering and fulfillment processes. Standard Workflows guarantee exactly once execution of each workflow step, with a maximum duration of one year. These workflows track and store detailed step-by-step information about each workflow that you may inspect during and after the workflow execution. Standard Workflows support all service integrations, activities, and design patterns.

Q: When should I use AWS Step Functions vs AWS CodePipeline?

You should consider using AWS CodePipeline when you are automating the release of software or infrastructure changes and want to leverage integrations with CI/CD services such as CodeBuild, CodeDeploy, and 3rd party CI/CD solutions as part of your release workflow. Inspired by Amazon’s deployment practices, only one instance of each pipeline exists and each is composed of sequential stages. These stages serve as a locking mechanism to ensure that only a single execution is flowing through a critical section of the pipeline at any given time. CodePipeline’s support for manual approvals holds a release within stage and allows manual testing while prior stages continue their execution. The stage-based model also lets you pause all releases without generating extensive release queue. CodePipeline intelligently-releases the most recent software changes so you can avoid wasting time on outdated releases.

By comparison, Step Functions natively supports multiple instances of a state machine which execute concurrently. This capability lends itself to supporting teams of developers performing integrations by building and testing their changes at the same time. However, managing deployments requires custom-solutions to control the order of deployments. You should consider AWS Step Functions when you need to create continuous integration workflows using patterns such as error-handling, parallelization, and branching. Step Functions supports service integration with AWS CodeBuild, Amazon ECS, Amazon EMR, AWS Glue, and other services. If your workflow requires you to build software changes or execute data-processing applications, you should consider using Step Functions with AWS CodeBuild, Amazon ECS, Amazon EMR, and AWS Glue service integrations.
Integration
Q: How does AWS Step Functions connect and coordinate other AWS services?

Workflows that you create with AWS Step Functions can connect and coordinate other AWS services using service tasks. For example, you can:

Invoke an AWS Lambda function
Run an Amazon Elastic Container Service or AWS Fargate task
Get an existing item from an Amazon DynamoDB table or put a new item into a DynamoDB table
Submit an AWS Batch job and wait for it to complete
Publish a message to an Amazon SNS topic
Send a message to an Amazon SQS queue
Start an AWS Glue job run
Create an Amazon SageMaker job to train a machine learning model or batch transform a data set
To learn more about using Step Functions to connect to other AWS services, see the Step Functions Developer Guide. You can also create tasks in your state machines that run applications, see the FAQ in the Overview section, How does AWS Step Functions connect to my resources?

Q: How does AWS Step Functions work with Amazon API Gateway?

You can associate your Step Functions APIs with Amazon API Gateway so that these APIs invoke your state machines when an HTTPS request is sent to an API method that you define. You can use an Amazon API Gateway API to start Step Functions state machines that coordinate the components of a distributed backend application, and integrate human activity tasks into the steps of your application such as approval requests and responses. You can also make serverless asynchronous calls to the APIs of services that your application uses. For more information, try our tutorial, Creating a Step Functions API Using API Gateway. 

Q: How does logging and monitoring work for AWS Step Functions?

AWS Step Functions sends metrics to Amazon CloudWatch and AWS CloudTrail for application monitoring. Amazon CloudWatch collects and track metrics, sets alarms, and automatically reacts to changes in AWS Step Functions. AWS CloudTrail captures all API calls for Step Functions as events, including calls from the Step Functions console and from code calls to the Step Functions APIs. Step Functions also supports Amazon CloudWatch Events managed rules for each integrated service in your workflow, and will create and manage CloudWatch Events rules in your AWS account as needed. For more information, see Monitoring and Logging in the AWS Step Functions Developer Guide.

Q: What happens if my Express Workflow fails due to exhausted retries or an unmanaged exception?

By default, Express Workflows report all outcomes to CloudWatch Logs including workflow input, output, and completed steps. You may select different levels of logging to only log errors, and you can choose to not log input and output. Workflows that exhaust retries or have an unmanaged exception should be re-run from the start. 

Security
Q: Can I access Step Functions from resources behind my Amazon VPC without connecting to the internet?

Step Functions also supports VPC Endpoints (VPCE) using AWS PrivateLink. You can access Step Functions from VPC-enabled AWS Lambda functions and other AWS services without traversing the public internet. For more information, refer the Amazon Virtual Private Cloud Endpoints for AWS Step Functions in the AWS Step Functions Developer Guide.

Compliance
Q: What are the compliance standards supported by Step Functions?

AWS Step Functions conforms to HIPAA, FedRAMP, SOC, GDPR, and other common compliance standards. See AWS Cloud Security site to get a detailed list of supported compliance standards.