AWS Wavelength FAQs
What is Wavelength?

Wavelength combines the high bandwidth and ultra-low latency of 5G networks with AWS compute and storage services to enable developers to innovate and build a whole new class of applications. Wavelength Zones are now generally available in partnership with Verizon in the United States, KDDI in Japan, and SK Telecom in South Korea. Wavelength Zones in Europe with Vodafone will be coming soon.

What is a Wavelength Zone?

Wavelength Zones are AWS infrastructure deployments that embed AWS compute and storage services within telecommunications providersâ€™ datacenters at the edge of the 5G network, so application traffic can reach application servers running in Wavelength Zones without leaving the mobile providersâ€™ network. This prevents the latency that would result from multiple hops to the Internet and enables customers to take full advantage of 5G networks. Wavelength Zones extend AWS to the 5G edge, delivering a consistent developer experience across multiple 5G networks around the world and allowing developers to build the next generation of ultra-low latency applications using the same familiar AWS services, APIs, tools, and functionality they already use today.

Who should use Wavelength?

You should use Wavelength when you need to deploy high performance applications that can be accessed by mobile end-users and devices that require single digit millisecond latency. AWS customers who want to build public applications like game streaming and AR/VR services can use Wavelength to reach end-users with millisecond-level connections, optimizing the user experience and performance of their applications. AWS enterprise customers that build applications to serve their own use-cases such as IoT, live media production, and industrial automation can use Wavelength to deliver low-latency solutions. Customers with edge data processing needs such as image and video recognition, inference, data aggregation, and responsive analytics can use Wavelength to perform low-latency operations and processing right where their data is generated, reducing the need to move large amounts of data to be processed in centralized locations.

Why should I use Wavelength?

Wavelength lets you go from the device on the 5G network to your applicationâ€™s resources on the AWS cloud with the fewest network hops because the compute and storage are hosted directly within the telco providersâ€™ 5G networks. This reduces latency caused by network congestion or longer routes that would be required to access application resources outside of the 5G network, making possible new classes of applications that are both compute-intensive and very sensitive to latency (e.g. a fleet of autonomous cars interacting with road sensors to prevent crashes, or smart industrial robots assessing and reacting to plant conditions in a dangerous manufacturing environment, or retailers serving personalized promotions to shoppersâ€™ mobile phones in real-time as they pass product displays). Wavelength brings the power of the AWS cloud to the network edge to enable latency sensitive use cases that require near real-time responses, and where processing at the network edge can be used to avoid transmitting large volumes of data over the network providerâ€™s infrastructure, and to offload processing from the hardware on mobile devices.

How should I think about when to use AWS Wavelength, AWS Local Zones, or AWS Outposts for applications that require low latency or local data processing?

AWS is helping customers by delivering a consistent experience to support applications with low latency or local data processing requirements wherever they need to be deployed.

AWS Wavelength is designed to deliver ultra-low latency applications to 5G devices by extending AWS infrastructure, services, APIs, and tools to 5G networks. Wavelength embeds storage and compute inside telco providers 5G networks to help developers build new applications for 5G end users that require single-digit millisecond latency, like IoT devices, game streaming, autonomous vehicles, and live media production.

AWS Local Zones are a new type of AWS infrastructure designed to run workloads that require single-digit millisecond latency in more locations , like video rendering and graphics intensive, virtual desktop applications. Not every customer wants to operate their own on-premises data center, while others may be interested in getting rid of their local data center entirely. Local Zones allow customers to gain all the benefits of having compute and storage resources closer to end-users, without the need to own and operate their own data center infrastructure.

AWS Outposts is designed for workloads that need to remain on-premises due to latency requirements, where customers want that workload to run seamlessly with the rest of their other workloads in AWS. AWS Outposts are fully managed and configurable compute and storage racks built with AWS-designed hardware that allow customers to run compute and storage on-premises, while seamlessly connecting to AWSâ€™s broad array of services in the cloud.

What are examples of workloads that take advantage of Wavelength?

Emerging interactive applications like game streaming, live video and event streaming, and machine learning video inference that require compute and storage close to the edge to ensure ultra-low latency for end-users and devices that connect through mobile networks can benefit from AWS Wavelength. In addition, use-cases like industrial automation, smart cities, IoT, and autonomous vehicles that require data processing and retrieval to take place close to the edge to deliver on the application performance requirements can benefit from AWS Wavelength and Wavelength Zones.
How do I get started with Wavelength?

Wavelength Zones are extensions of an AWS Region, allowing you to use the same AWS tools and capabilities you do today, and minimizing the need to rearchitect your application to reduce latency to your end customers. If you have an existing application, all you need to do is select your VPC in the VPC console and choose create a subnet in a Wavelength Zone in the Actions menu. By default, the Carrier Gateway wizard enables Wavelength Zones for all carriers and locations available in the Region, or you can choose specific ones. The wizard assists you with setting up subnets for each Wavelength Zone. You can then launch Amazon EC2 instances in the new subnets and run containerized applications on Amazon ECS and Amazon EKS. If you do not have a VPC, the easiest way to get started is to select the Create VPC wizard in the VPC console.

What AWS services are available in Wavelength?

You can create Amazon EC2 instances, Amazon EBS volumes, and Amazon VPC subnets and carrier gateways in Wavelength Zones. You can also use services that orchestrate or work with EC2, EBS and VPC such as Amazon EC2 Auto Scaling, Amazon EKS clusters, Amazon ECS clusters, Amazon EC2 Systems Manager, Amazon CloudWatch, AWS CloudTrail, and AWS CloudFormation. The services in Wavelength are part of a VPC that is connected over a reliable, high bandwidth connection to an AWS Region for easy access to services including Amazon DynamoDB and Amazon RDS.

Can I reserve capacity for Amazon EC2 in a Wavelength Zone?

You can use On-Demand Capacity Reservations to reserve capacity for your Amazon EC2 instances in a Wavelength Zone.

What pricing models are supported in Wavelength Zones for Amazon EC2?

There are two ways to pay for Amazon EC2 instances in Wavelength Zones: On-Demand and Savings Plans.

What EC2 instance types are available?

Wavelength supports the following instances types for edge workloads: t3.medium, t3.xlarge, and r5.2xlarge for applications that need cost effective general purpose compute; g4dn.2xlarge for applications that need GPUs such as game streaming and ML inference at the edge. All EC2 instances are EBS-based. AMIs and Snapshots of EBS volumes are stored in the parent Region. EC2 Instances are only offered On-Demand; you cannot buy Reserved Instances in a Wavelength Zone.

Can I use Wavelength Zones to deliver applications to 4G/LTE devices?

Yes, applications running on 4G/LTE mobile phones, and devices connected over 4G/LTE networks, can access applications servers on Wavelength Zones and benefit from having the compute infrastructure co-located within the mobile network. 

How do I see my usage in Wavelength Zones?

You can use the AWS Cost Explorer to filter usage by Availability Zone, including Wavelength Zones.

How do I get support for AWS services running in Wavelength?

Create a case with AWS Support to get help with AWS services running in Wavelength Zones.