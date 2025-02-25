Everything fails all the time, so plan for failure and nothign fails. - werner vogels

Each service is the right service for specific needs.
### Terms

1. client-server model (web brwosers/desktop applications - AWS EC2 instance, a virtual server)
2. On demand delivery, pay-as-you-pricing.
3. Upfront expense and variable expense.
4. go global in minutes, global footprints.
5. economies of scale
6. Multitenancy, hypervisor
7. Scale up (vertical scaling) - adds more resources to a single machine
8. Scale out (horizonata scaling) - add more machines, often using load balancers
9. Compute as a service (CaaS) model.
10. HPC, high performance computing
11. IOPS - Input/Output Operations Per Second
12. suitable workloads - chosing EC2 famliy and pricing wholey based on type of workloads
13. Tightly coupled Architecture also called monolithic approach
14. Lossely Coupled/Decoupled Architecture single failure won't cause cascading failures. also called microservices approach
15. Paylod - data contained within a message
16. severless - you cannot see or access the underlying architecture.
17. High availability and fault tolerance
18. block level storage


### Concepts
1. **you only pay for what you use** servers and resources can be scale in and out dynamically. variable expense


2. **On demand delivery of IT resources over the interent with pay-as-you-go pricing**


3. AWS helps with **undifferentiated heavy lifting of IT**. So, companies can implement innovative solutions while saving on costs.


4. cloud computing deployment models
   1. cloud based deployment - migrate or build new applications in the cloud, low-level infrastructure(require IT staff to manage them) and high-level services (reduce the managememt)
   2. On premises or private cloud deployment - much like legacy IT infrastructure.
   3. Hybrid deployment - integrate cloud based resources with legacy IT applications.
5. more customer a cloud provider has, the more cost-effective it becomes to operate and these savings can be passed on to customers.


6. Amazon Elastic cloud compute services provision Amazon EC2 instances.
   1. Launch (configurations, applications, security settings (network traffics))
   2. connect (several ways)
   3. Use (run commands, intall softwares, add storage..)


7. Amazon EC2 instance families (5 families)
   1. General purposes - balanced
   2. Compute optimized - task requires more cpu power. Gaming servers, HPC, scientific modelig
   3. Memory optimized - cpu -> memory -> storage
   4. Accelerated computing(hardware accelators) - GPUs. Floating point number cal,graphic procesing,data pattern matching
   5. Storage optimized - (IOPS) high performance for locally stored data


8. Amazon EC2 Pricing
   1. On Demand
      1. renting EC2 wihtout interruptions, no commitment and pay after the use. aws provide more flexibilty so more price.
      2. pros
         1. no upfront
         2. irregular workloads that cannot be interrupted
         3. instances run continuously until you stop them
         4. you pay for only the compute time you use
      3. cons
         1. short-term 
         2. pay as you go pricing, more usage time more price 
   
   2. Savings Plans
      1.  a commitment to a consistent amount of usage (measured in $/hour) for a 1 or 3 year term
      2. pros
         1. cost savings over on demand upto 72%
         2. no interruptions
      3. cons
         1. pay all upfront
   3. Reserved Instances
      1. committing to use AWS resources for a 1 or 3-year term, suitable for steady stat workloads
      2. l in yu (aws provide flexible upfront optinos full, parital and no) upto 75% savings all upfront verus on demand
      3. pros
         1. reserved instances
      4. cons
         1. assume workloads runs most of time.
   4. Spot Instances
      1.  allow you to bid on unused EC2 capacity at significantly reduced prices, often up to 90% off compared to On-Demand prices
      2.  prons
          1.  cost savings upto 90%
      3.  cons
          1.  interruptoins
   5. Dedicated hosts 
      1. suitable for following complicance requirements
   
9.  Scalability(ASG) and Elasticity(ELB)
   1.  Scalability involves beginning with only the resources you need and designing your architecture to automatically respond to changing demand by scaling out or in.
   2.  AWS service that provides this functionality for Amazon EC2 instances is Amazon EC2 Auto Scaling.
   3.  Amazon EC2 Auto Scaling enables you to automatically add or remove Amazon EC2 instances in response to changing application demand.
       1.  two approches
           1.  dynamic scaling - responds to changing demands
           2.  predictive scaling - automatically schedules the right number of Amazon EC2 instances based on predicted demand
       2. To scale faster, you can use dynamic scaling and predictive scaling together.
       3. Amazon EC2 Auto Scaling group has
          1. Minimum capacity ( a baseline level of availability and performance for your application)
          2. desired capacity (It actively manages the number of running instances to match the desired capacity, scaling up or down as needed. )
          3. Maximum capacity (maximum no of instances can turn on in auto scaling group)
       4. Elastic Load Balancing (ELB)
          1. ELB is a regional construct, it runs at the regional level rather than on individual EC2 instances.
          2. ELB is not only used for external traffic. traffic -> ELB -> EC2s
          3. ELB also solves Internal traffic frontend backend network traffic chaos.  frontend -> ELB -> EC2s. here ELB is regional, it's a single url the frontend instances uses. ELB uses to decouple frontend and backend.
10. Messaing and Queuing
    1.  Act as a buffer between two application's traffic. help to achieve more reliable architecture (Loosely coupoled architecture) where single failure won't cause cascading failures.
    2.  Amazon Simple Queue service (Amazon SQS) and Amazon simple notification service (Amazon SNS)
        1.  Amazon SQS (mssage queuing service)
            1. Amazon SQS queues where messages are placed until they are processed
            2.  send, store, receive messages betwee software components at any volume
        2. Amazon SNS (publish/subscribe service)
           1. is similar, it is used to send out messages to services but it can also send out notifications to end users. public/subscribe model
           2. Amazon SNS topic: A channel for messages to be delivered.
           3. publish a message to topic channel, it fans out to all subscribers in that channel. subscribers can be endpoints, sqs queues , aws lambda functions, http or https webhooks. additionally, sns can be used to fan out notifications to end users using mobile push, sms and email.
11.  Additional compute Services
     1.  An AWS service for serverless computing is AWS Lambda
         1.  Amazon EC2 services steps are 1. provision instances 2. upload your code 3. continue to manage the instances while your application is running
         2. AWS Lambda takes care of 1. and 2. of Amazon EC2 services.
         3. Amazon EC2 (customers thinks about servers and code) and AWS lambda (customers only thinks about code)
         4. process
            1. upload code to lambda
            2. set your code to trigger from an event source
            3. lambda runs code when triggered
            4. pay only for the compute time.
      2. Container orchestration (ECS and EKS)
         1. Amazon Elastic Container Service (ECS) 
            1. Amazon ECS supports Docker containers
            2. AWS supports the use of open-source Docker Community Edition and subscription-based Docker Enterprise Edition.
            3. With Amazon ECS, you can use API calls to launch and stop Docker-enabled applications.
         2. Amazon Elastic Kubernetes Service (EKS)
            1.  AWS actively works together with the Kubernetes community
      3. AWS Fargate
         1. a serverless compute engine for containers
         2. It works with both Amazon ECS and Amazon EKS. 
         3. AWS Fargate manages your server infrastructure for you.


12. AWS Global Infrastructure
    1.  when determining the right region for your services, data and applications consider the following four business factors.
        1.  Compliance with data governance and legal requirements
        2.  Proximity to your customers
        3.  Available services within a region
        4.  Pricing, vary from region to region
    2. Availability Zones
       1. AZ is a single data center or a group of data center within a region
       2. Region(AZ(datacenter), AZ(*datacenters), AZ(*dtacenters)..)
       3. A Region consists of three or more Availability Zones.
    3. Caching copy of data closer to customers (at Edge Locations) all over the world uses the concept of Content Delivery Network(CDN). CDN a network that delivers edge contents (website asset, images, webpages or videos..) to users based on their geographic location.
       1.  A CDN service by AWS called Amazon CloudFront (ACF). 
       2. An origin is the server from which CloudFront gets your files like s3
       3. ACF runs in Edge locations, Edge locatoin can do more they can run DNS knowns as Amazon Route 53.
    4. What if Enterprise needs to run Amazon services in their own data centers. 
       1. Amazon can help with that called Amazon Outposts.
       2. AWS Outposts is a service that enables you to run infrastructure in a hybrid cloud approach.
       3. Extend AWS infrastructure and services to different locations, including your on-premises data center.
    5. How to provision AWS resources
          1. API to provision, congigure and managle AWS resources
             1. AWS Management console /  the AWS Console mobile application 
                1. browser-based, visual control, to view bills, test env, view monitoring and work with other non-techincal resources
                2. point and click style. humans provisioning the resources manually leaving room for potential errors.
                3. The AWS Management Console includes wizards and workflows that you can use to complete tasks in AWS services.
             2. AWS command line console CLI
                1. by script or program the api calls
                2. make api calls using the terminal on your machine
                3. make actions scriptable and repeatable
                4. can make these script run automatically by triggers or schedule process.
             3. AWS software developement kit SDKs
                1. Interact with AWS resources through various programming languages.
                2. In Python a library calld boto3 helps to interact with amazon services.
             4. various other manage tools
                1. AWS Elastic Beanstalk
                   1. you provide code and configuration settings, and Elastic Beanstalk deploys the resources necessary to perform the following tasks:
                      1. Adjust capacity
                      2. Load balancing
                      3. Automatic scaling
                      4. Application health monitoring
                2. AWS Cloudformation
                   1. Infrastructure as code tool used to define a wide variety of AWS resources.
                   2. Allows you to define and manage infrastructure using JSON or YAML text based document called cloudformation templates.
                   3. cloudformation let's you decide what you want and cloudformation engine worry about how to do it. api calls..
 13. AWS Networking
       1. Private and Public networks
          1. AWS virtual private cloud (VPC) 
             1. services allows us to own our private network in aws.
             2. A networking service that you can use to establish boundaries around your AWS resources
          2. Subnets are chunks of ip addresses in vpc that allow us to group our resource together.
          3. VPC's 
             1. public facing resources:
                1. public traffic -> flows over the internet(high latency & low security) -> Internet Gateway (IGW) -> VPC
             2. Private facing resources:
                1. Private traffic -> virtual private Gateway(VPN, it uses internet to route, high latency and low security) -> Virtual Private Gateway -> VPC
                2. A virtual private gateway enables you to establish a virtual private network (VPN) connection between your VPC and a private network, such as an on-premises data center or internal corporate network.
             3. AWS Direct Connect allows us to establish a completely private, dedicated fiber connection from our data center to AWS.
                1.  Private traffic -> flows through the AWS direct connect (low latency & high security) -> Virtual Private Gateway -> VPC
                2.  The private connection that AWS Direct Connect provides helps you to reduce network costs and increase the amount of bandwidth that can travel through your network.
                3.  benefits of using virtual private gateway with direct connect:
                    1. In case of a Direct Connect failure, having a Virtual Private Gateway allows you to quickly switch to a VPN connection over the internet, ensuring business continuity
                    2. A Direct Connect gateway allows you to connect to multiple VPCs across different AWS regions using a single Direct Connect connection. Each VPC must have a Virtual Private Gateway attached to facilitate this connectivity
          4. It's also important to note that one VPC might have multiple types of gateway attached for multiple types of resources all residing in same VPC, just in different subnets.
          5. Subnet and Network Access control list ACL:
             1. A subnet is a section of a VPC in which you can group resources based on security or operational needs. Subnets can be public or private. 
                1. pulbic subnet
                   1.  contain resources that need to be accessible by the public
                2. private subnet
                   1. contain resources that should be accessible only through your private network, such as a database that contains customers’ personal information and order histories. 
                3. In a VPC, subnets can communicate with each other.
             2. Acesss control list (ACL)
                1. The VPC component that checks packet permissions for subnets is a network access control list (ACL).
                2. Network ACLs perform stateless packet filtering. They remember nothing and check packets that cross the subnet border each way: inbound and outbound. 
                3. By default, your account’s default network ACL allows all inbound and outbound traffic, but you can modify it by adding your own rules.
                4. For custom network ACLs, all inbound and outbound traffic is denied until you add rules to specify which traffic to allow. Additionally, all network ACLs have an explicit deny rule.
                5. After a packet has entered a subnet, it must have its permissions evaluated for resources within the subnet, such as Amazon EC2 instances. 
                6. The VPC component that checks packet permissions for an Amazon EC2 instance is a security group.
             3. Security Groups
                1. A security group is a virtual firewall that controls inbound and outbound traffic for an Amazon EC2 instance.
                2. Security groups perform stateful packet filtering. They remember previous decisions made for incoming packets. Security groups are stateful. This means that they use previous traffic patterns and flows when evaluating new requests for an instance.
                3. By default, a security group denies all inbound traffic and allows all outbound traffic
                4. You can add custom rules to configure which traffic should be allowed; any other traffic would then be denied
             4. Global Network
                1. how customer access the website hosted on AWS
                2. DNS resolution involves a customer DNS resolver communicating with a company DNS server. customer and pc -> customer DNS resolver <-> company DNS server
                   1. Amazon Route 53
                      1. Amazon Route 53(opens in a new tab) is a DNS web service
                      2. Amazon Route 53 connects user requests to infrastructure running in AWS (such as Amazon EC2 instances and load balancers). It can route users to infrastructure outside of AWS.
                      3. Another feature of Route 53 is the ability to manage the DNS records for domain names. You can register new domain names directly in Route 53.
                      4. Route 53 and Amazon CloudFront can work together to deliver content to customers.
                      5. can direct traffic to different end points using different routing policies
                         1. latency based routing
                         2. geolocation DNS
                         3. geoproximity routing
                         4. weighted round robin

14. Storage and databases
    terms: instance store volume, block storage, Amazon Elastic Block storage(EBS), 
    1. Amazon Elastic Block store (EBS) (upto 16TB, ssd by default)
       1. instance store volume is a storage come with the host where EC2 instance running on. starting instance from stopped state, it may run on new host and the stored previous data gets deleted. we can slove this by assigning a seperate block storage to our EC2 instance, in amazon it's called Amazon Elastic Block Storage.
       2. Because EBS volumes are for data that needs to persist, it’s important to back up the data. You can take incremental backups of EBS volumes by creating Amazon EBS snapshots.
       3. An EBS snapshot(opens in a new tab) is an incremental backup. This means that the first backup taken of a volume copies all the data. For subsequent backups, only the blocks of data that have changed since the most recent snapshot are saved. 
    2. Amazon Simple Storage Service (S3) (regional object storage) 11 nines durable. serverless
       1. In object storage, each object consists of data, metadata, and a key.
       2. When a file in object storage is modified, the entire object is updated.
       3. Amazon S3 offers unlimited storage space
       4. The maximum file size for an object in Amazon S3 is 5 TB.
       5. When you upload a file to Amazon S3, you can set permissions to control visibility and access to it. You can also use the Amazon S3 versioning feature to track changes to your objects over time.
   3. File system is a software employed by OS to manage data. when saving file, os handover the task to file system, it stores in storage and keep track of it. Data retrieval, os ask file system to bring up the data, it locate and read the from storage device and loads it into **RAM** for quick access. file system allows us to manage files and dirs, permission and basic operation like copying moving deleting.

                  
   



