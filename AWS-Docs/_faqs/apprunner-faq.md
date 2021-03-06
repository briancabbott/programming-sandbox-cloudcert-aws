General
Q: Why should I use AWS App Runner?
A: AWS App Runner is the easiest way to run your web application (including API services, backend web services, and websites) on AWS. With App Runner, there is no infrastructure or container orchestration required. You can go from an existing container image, container registry, source code repository, or existing CI/CD workflow to a fully running containerized web application on AWS in minutes. 

App Runner seamlessly integrates with your development workflow to provide the right level of automation to deploy your code or container image without the need for you to understand, provision, scale, or manage any AWS compute, networking, and routing resources. You get the simplicity to run thousands of applications that automatically scale based on your traffic needs. Your applications also run on infrastructure that is maintained and operated by AWS, providing security and compliance best practices such as automated security patches and encryption.

Q: How do I get started with AWS App Runner?
A: You can deploy an AWS App Runner application on AWS by going to the App Runner console or using the AWS CLI and creating an App Runner application. When creating the App Runner application, you can provide a container image, connect your container registry, or connect your source code repository, and enter any optional build and start commands. App Runner will automatically create the service with a corresponding secure URL.

Q: Can I still use AWS App Runner if I don’t use containers?
A: Yes. AWS App Runner supports automatically building a container image on curated App Runner platforms that contain supported runtimes and frameworks. When you associate your existing source code repository and optionally provide App Runner with your runtime build and start commands, App Runner automatically containerizes your web application and provides a running web application. 
Q: Can I migrate from AWS App Runner to Amazon Elastic Container Service (Amazon ECS), Amazon Elastic Kubernetes Service (Amazon EKS), or another AWS service if I need more flexibility?
A: Yes. You can use the same container image deployed to App Runner on Amazon ECS or Amazon EKS. This gives you the flexibility to move to different services as your needs change. You can deploy your code or containers directly to the new AWS service you choose using the tools and onboarding workflow provided by that service. 
Developers
Q: What type of applications can I run on AWS App Runner?
A: AWS App Runner supports full stack development, including both frontend and backend web applications that use HTTP and HTTPS protocols. These applications include API services, backend web services, and websites. App Runner supports container images as well as runtimes and web frameworks including Node.js and Python. 

Q: What type of deployment options do I have with AWS App Runner? 
A: AWS App Runner supports multiple deployment options including the ability to immediately deploy a container image using the App Runner console or AWS CLI. If you have an existing CI/CD workflow that uses AWS CodePipeline, Jenkins, Travis CI, CircleCI, or another CI/CD toolchain, you can easily add App Runner as your deployment target using the App Runner API or AWS CLI. If you want App Runner to automatically provide continuous deployment for you, you can easily connect to your existing container registry or source code repository and App Runner will automatically provide a continuous deployment pipeline for you. 

With App Runner, you can have a unique application for each of your container images or source code branches with separate environment variables, deployment types (such as a development application or production application), and build and start commands. Once deployed, you get all the benefits of running your web application on App Runner including default security, automatic scaling, and monitoring.

Q: How does AWS App Runner scale applications to varying demand?
A: AWS App Runner monitors the number of concurrent requests sent to your application and automatically adds additional instances based on request volume. If your application receives no incoming requests, App Runner will scale the containers down to a provisioned instance, a cpu throttled instance ready that is ready to serve incoming requests within milliseconds. You can also optionally configure the number of concurrent requests sent to an instance in the autoscaling settings of your application.

Q: Can I use my own domain name with web applications I’m running on AWS App Runner?
A: Simply add your custom domain to your AWS App Runner application using the App Runner console or AWS CLI. After you add your custom domain name, App Runner provides instructions to help you update your DNS records with your DNS provider. App Runner supports custom sub domains (www.example.com), custom root domains (example.com), and wildcard domain (*.example.com). 

Q: What if my application needs access to storage, database, or caching services?
A: AWS App Runner does not restrict your ability to connect an application to other storage, database, or application integration services. Customers can easily configure their applications or containers with the necessary code and connection instructions, and their application is able to communicate with these external services over the network securely.

Q: How can I view the logs of my application running on AWS App Runner?
A: AWS App Runner fully integrates with Amazon CloudWatch Logs and provides you with runtime logs and deployment logs aggregated from the output streams of all of the system components, web frameworks, runtimes, build and deployment commands, and application/web servers. App Runner aggregates these into a single comprehensive channel available through the App Runner console, CloudWatch console, and AWS CLI. 
Q: Can I run web applications on AWS App Runner and persistent applications on AWS Fargate with an orchestrator?
A: Yes. If you need to run other applications such as content management systems that need a persistent file system or machine learning jobs, you can use AWS Fargate with an orchestrator that is capable of multiple resources such as graphics acceleration or persistent volumes. If you are using the Copilot CLI, you can continue to use the tool as it has support for both App Runner and ECS/Fargate. You can also use Amazon CloudWatch as your single pane of glass to monitor applications running across App Runner, Amazon ECS tasks running on Fargate, and Amazon EKS pods running on Fargate.

Q: Is AWS App Runner supported by Copilot?
A: AWS Copilot is a command line interface (CLI) that enables customers to quickly launch and easily manage containerized applications on AWS. You can use Copilot to quickly get up and running on AWS App Runner. You can also use Copilot as your standard CLI to operate across AppRunner and/or ECS/Fargate.
Pricing and Billing
Q: How am I charged for AWS App Runner?
A: You are charged for the compute and memory resources used by your application. You can also pay for additional App Runner features like building your deployment from source code or automating your deployments. For information, see our pricing page.

Q: What are AWS App Runner budget controls?
A: You can set a maximum limit on the number of active container instances your application uses so that costs do not exceed your budget.