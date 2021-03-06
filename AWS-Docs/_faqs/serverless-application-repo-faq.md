GENERAL
What are serverless applications?

Serverless applications eliminate the need to provision, deploy, or manage servers or other infrastructure. They come with built-in high availability and they scale continuously and automatically. You can use one of the many fully managed AWS services to build and run serverless applications, including AWS Lambda for compute, Amazon API Gateway for APIs, and Amazon DynamoDB for databases.

Show less
What is the AWS Serverless Application Repository?

The AWS Serverless Application Repository offers a growing collection of serverless applications published by AWS and other AWS partners and developers. The Serverless Application Repository makes it easy to deploy applications for common use cases like web and mobile back-ends, stream processing, machine learning, and more, so you can quickly get started with the AWS Serverless platform.

Show less
In which regions is the AWS Serverless Application Repository available?

It is currently available in the following regions: US East (Ohio), US East (N. Virginia), US West (N. California), US West (Oregon), Asia Pacific (Tokyo), Asia Pacific (Seoul), Asia Pacific (Mumbai), Asia Pacific (Singapore), Asia Pacific (Sydney), Canada (Central), EU (Frankfurt), EU (Ireland), EU (London), and South America (São Paulo).
Show less
What kinds of applications are available in the AWS Serverless Application Repository?

The AWS Serverless Application Repository includes applications for Alexa Skills, chatbots, data processing, IoT, real time stream processing, web and mobile back-ends, social media trend analysis, image resizing, and more from publishers on AWS.
Show less
Does it cost anything to use the AWS Serverless Application Repository?

There is no charge to browse applications, deploy applications, or publish applications in the AWS Serverless Application Repository. Standard AWS charges apply to the resources used by the applications you deploy.
Show less
How are applications in the AWS Serverless Application Repository licensed?

Applications provided by AWS are available under the MIT open source license, while applications publicly provided by others can be made available under one or more open source license(s) approved by the Open Source Initiative (OSI). You can find licensing details by navigating to the licensing tab of an application on the AWS website.
Show less
Are applications in the AWS Serverless Application Repository verified by AWS?

All applications published by AWS are vetted for license adherence and code quality. Applications published by third parties are validated for correct use of permissions to ensure that consumers know which resources can be modified or accessed by an application. You can review those details, along with the number of times an application has been deployed by AWS customers, prior to using an application.
Show less
Can I use the AWS Serverless Application Repository in combination with GitHub?

Yes. The AWS Serverless Application Repository enables developers to publish serverless applications developed in a GitHub repository. Using AWS CodePipeline to link a GitHub source with the AWS Serverless Application Repository can make the publishing process even easier, and the process can be set up in minutes.
Show less
DEPLOYING APPLICATIONS
How do I manage serverless applications deployed to my account?

Serverless applications are deployed as AWS CloudFormation stacks, which make it easy for you to manage an application as a single unit. Each resource is tagged with the application’s uniquely identifiable Amazon Resource Name (ARN), which helps you locate the resources using the AWS Tag Editor console. You can also use existing AWS and third-party tools to manage each resource separately.

Show less
PUBLISHING APPLICATIONS
How do I publish a serverless application to the AWS Serverless Application Repository?

To publish a serverless application, describe the application using the AWS Serverless Application Model (SAM) format, package it using the AWS CLI, and publish it using the AWS Management Console, AWS CLI, or AWS SDKs. You must have a valid AWS account, and you will be required to provide a name, description, source code link, and a LICENSE.txt for your application. Applications that are intended to be made available to any AWS customer must be published in either the US East (N. Virginia) or US East (Ohio) regions.
Show less
Who can deploy the applications I publish to the AWS Serverless Application Repository?

Publishers control who can find and deploy their applications in the Repository. You can limit access to your team (a group under the same AWS account), share an application with other accounts, or make it publicly available to any AWS customer. To learn more about the permissions and visibility of applications you publish, review our Resource-Based Policies documentation.
Show less
Can I charge a fee for serverless applications I publish?

If you would like to charge a fee for the use of a serverless application, you can integrate AWS Lambda behind Amazon API Gateway, and then sell the API as a SaaS product through the AWS Marketplace. To learn more, review the steps to list on AWS Marketplace and how to monetize your API using API Gateway.

Show less
USING NESTED APPLICATIONS
What is a nested application?
A nested serverless application is a component that is deployed as part of another serverless application. As serverless architectures grow, common patterns emerge in which the same components are defined in multiple application templates. You can now separate out common patterns as dedicated applications and then nest them as part of new or existing application templates.
Show less
How are nested applications deployed?
Nested applications are deployed as AWS CloudFormation nested stacks.
Show less
How do I include a nested application in my SAM template?

Use the AWS:Serverless:Application resource type to add applications that you have developed locally or that have been shared with you via the Serverless Application Repository. You can define inputs for the nested application or reference outputs using simple AWS SAM syntax. For more details, see our documentation.
Show less
How do I handle resource name conflicts when nesting applications?

Specify a unique name for each nested application in your SAM template. Resources created by the nested application will be scoped to the application's unique name.
Show less
How do I package a nested application?

Use the SAM CLI sam package command to package your nested application. Publish your packaged application to the Serverless Application Repository using APIs or the AWS SDK. You can use the SAM CLI sam deploy command to deploy your application immediately.
Show less
Can I package a hierarchy of nested applications using SAM CLI?

Yes. The SAM CLI sam package command will recursively package a hierarchy of nested applications. You can have a maximum of 199 applications nested in a single top-level application template.
Show less
Consuming Nested Applications

How do I manage serverless applications deployed to my account?

Serverless applications are deployed as AWS CloudFormation stacks, which make it easy for you to manage an application as a single unit. Each resource is tagged with the application’s uniquely identifiable Amazon Resource Name (ARN), which helps you locate the resources using the AWS Tag Editor console. You can also use existing AWS and third-party tools to manage each resource separately.

Show less
How do I nest applications shared with me via the Serverless Application Repository?
Configure the AWS:Serverless:Application SAM resource with the application ARN and any necessary input parameters required by the application. For more details, see our documentation.
Show less
Q: How do I package a nested app that I used from the Serverless Application Repository?

Nested applications from the Serverless Application Repository are already packaged and ready for you to use. You can use the existing SAM CLI sam package command to ensure that nested applications are still available to you before you deploy the application in your account.

Show less
What happens if an application that I nested is no longer available?

Applications that you nest which get deleted or that you no longer have access to will have no impact on the existing deployments of your application. You will be required to update your application if you attempt to deploy it with dependencies that no longer exist.
Show less
How can I tell if an application contains other nested applications?

Applications that contain one or more nested applications use CAPABILITY_AUTO_EXPAND.
Show less
Publishing Nested Applications

Can I publish nested applications to the Serverless Application Repository?

Yes. You can publish nested applications to the Serverless Application Repository just like you publish stand-alone applications today. Use the AWS console, AWS CLI, SAM CLI, or Serverless Application Repository APIs to publish nested applications.
Show less
Sharing Nested Applications

How do I share an application that contains nested applications?

Serverless applications follow the same model used by Lambda functions today. Access to serverless applications in the Serverless Application Repository can be controlled using AWS IAM resource-based policies. You can use policies to keep your application private, grant cross-account access, or make it publicly available.

Show less
How does sharing work when there is a hierarchy of nested applications?

With a hierarchy of nested applications, each nested application has to be made available to the AWS account with whom you are sharing the top-level application.
Show less
SHARING APPLICATIONS
Can I share applications with all accounts that belong to an AWS Organization?
Yes. You can now share application with all accounts that belong to an AWS Organization. Serverless apps follow the same model used by Lambda functions today. Access to serverless applications in the AWS Serverless Application Repository can be controlled using AWS IAM resource-based policies. You can use policies to keep your app private, grant cross-account access, grant organization access or make it available publicly. To learn more about resource-based policies for serverless applications, see here.
Show less
How do I update resource-based policies to share an app with an AWS organization?
To get started, find the application in the AWS Serverless Application Repository console, click on the ‘Share’ tab and then click on ‘Create Statement’. Here you can add the AWS Organization principal to grant the organization with access to the app. You can also use the AWS Serverless Application Repository APIs to update resource-based policies to share apps across an organization. For more details on resource based polices, see our documentation here.
Show less
Can I share an application with multiple AWS Organizations?
No. You can share an application only with accounts that belong to the same AWS Organization as your account.
Show less
Can I share an application with a particular organizational unit within my organization?
Sharing of applications within an organizational unit isn’t supported. You can use policies to keep your app private, grant cross-account access, grant organization access or make it available publicly.
Show less
How do I share an application with specific accounts in an organization?
To provide access to your application for certain accounts in an organization, simply update the resource-based policy to include AWS accounts along with the AWS organization ID with whom you would like to share the application.
Show less
Can I update permissions for an organization to only view an application?
Yes. You can set actions on your resource-based policy which can restrict the type of operations someone can take on an application that you have shared. Updating actions for a resource-based policy is supported through the AWS Serverless Application Repository APIs and console. For more details on actions you can set for resource-based polices, see our documentation here.
Show less
USER TERMS
1. Publishers, who are AWS customers, may submit their AWS serverless applications and components (“AWS Serverless Applications”) to be made available through the AWS Serverless Application repository (“Repository”) either privately, across specified AWS accounts or to all AWS customers using the Repository pursuant to the Repository console publication process. AWS Serverless Applications to be made available either privately or across specified AWS accounts may be in binary or source code form; AWS Serverless Applications made available to all AWS customers may be in binary or source code form, and must include sufficient details to enable the user access to the source code.

2. Publishers must have all licenses and necessary permissions or rights to submit their AWS Serverless Applications to the Repository. Publisher must submit to the Repository, along with its AWS Serverless Application, the terms of the AWS Serverless Application’s license(s), including any open source license attribution requirements. Publisher is responsible for reviewing, evaluating and testing any AWS Serverless Application before submitting it to the Repository.

3. Publisher hereby grants AWS and its affiliates the rights to reproduce, distribute, display publicly or within specified AWS accounts (as applicable), perform, transmit, use and otherwise digitally make available (via all means of online and electronic distribution) its AWS Serverless Applications in the Repository.

4. Publisher represents and warrants it has all rights to submit its AWS Serverless Application to the Repository, has all rights to allow downloading of its AWS Serverless Application from the Repository and has provided all required attributions. Publisher will not submit AWS Serverless Applications with malware, malicious or other harmful content with the intent or purpose to harm others. AWS may remove and take down any AWS Serverless Application in the sole discretion of AWS for this or other reasons.

5. AWS customers will comply with the license(s) (including any attribution or other requirements) for any AWS Serverless Application they download.

6. Any AWS customer who creates a derivative work of any AWS Serverless Application is responsible for determining whether it has the appropriate rights under the AWS Serverless Application’s license(s) to do so and must comply with any attribution or other requirements.

7. Any Publisher’s AWS Serverless Application license or other agreement is solely between the Publisher and AWS customers. Neither AWS nor any of its affiliates are a party to that license or other agreement and none of them will have any liability or obligations under that license or other agreement. AWS is not responsible and has no liability for ensuring that Publishers or AWS customers comply with licensing (including attribution) or other requirements.

8. AWS Serverless Applications and any other third-party materials available in the Repository are “Repository Content.” THE Repository Content IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL PUBLISHERS, COPYRIGHT HOLDERS, AWS OR ITS AFFILIATES BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE Repository Content OR THE USE OR OTHER DEALINGS IN THE Repository Content.

9. Publishers and AWS customers acknowledge they will comply with all of these terms in their use of the Repository and these terms may be updated by AWS from time to time.