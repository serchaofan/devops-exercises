# AWS

#### Global Infrastructure

<details>
<summary>Explain the following

- Availability zone
- Region
- Edge location</summary><br><b>
  AWS regions are data centers hosted across different geographical locations worldwide, each region is completely independent of one another.<br>

Within each region, there are multiple isolated locations known as Availability Zones. Multiple availability zones ensure high availability in case one of them goes down.<br>

Edge locations are basically content delivery network which caches data and insures lower latency and faster delivery to the users in any location. They are located in major cities in the world.
</b></details>

#### IAM

<details>
<summary>What is IAM? What are some of its features?</summary><br><b>
</b></details>

<details>
<summary>True or False? IAM configuration is defined globally and not per region</summary><br><b>

True
</b></details>

<details>
<summary>What are Roles?</summary><br><b>

A way for allowing a service of AWS to use another service of AWS. You assign roles to AWS resources.
</b></details>

<details>
<summary>What are Policies?</summary><br><b>

Policies documents used to give permissions as to what a user, group or role are able to do. Their format is JSON.
</b></details>

#### S3

<details>
<summary>Explain what is S3 and what is it used for</summary><br>
<b>
S3 stands for 3 S, Simple Storage Service.
S3 is a object storage service which is fast, scalable and durable. S3 enables customers to upload, download or store any file or object that is up to 5 TB in size. While having a maximum size of 5 GB per file (multipart upload if more than 5 GB in size).
</b>
</details>

<details>
<summary>What is a bucket?</summary><br><b>
An S3 bucket is a resource which is similar to folders in a file system and allows storing objects, which consist of data and its  meta data.
</b></details>

<details>
<summary>True or False? A bucket name must be globally unique</summary><br><b>
True
</b></details>

<details>
<summary>What objects in S3 consists of?
  * Another way to ask it: explain key, value, version id and meta data in context of objects</summary><br><b>
</b></details>

<details>
<summary>Explain data consistency</summary><br><b>
</b></details>

<details>
<summary>Can you host dynamic websites on S3?. What about static websites?</summary><br><b>
</b></details>

<details>
<summary>What security measures have you taken in context of S3?</summary><br><b>
</b></details>

<details>
<summary>What is a storage class? What storage classes are you familiar with?</summary><br><b>
</b></details>

#### EC2

<details>
<summary>What is EC2? What is it used for?</summary><br><b>
</b></details>

<details>
<summary>What EC2 pricing models are there?</summary><br><b>
</b></details>

<details>
<summary>How to increase RAM for a given EC2 instance?</summary><br><b>

Stop the instance, the type of the instance to match the desired RAM and start the instance.
</b></details>

<details>
<summary>What is an AMI?</summary><br><b>
</b></details>

<details>
<summary>How many storage options are there for EC2 Instances?</summary><br><b>
</b></details>

<details>
<summary>What happens when an EC2 instance is stopped or terminated?</summary><br><b>
</b></details>

<details>
<summary>What are Security Groups?</summary><br><b>
</b></details>

<details>
<summary>How to migrate an instance to another availability zone?</summary><br><b>
</b></details>

<details>
<summary>What are spot instances?</summary><br><b>
</b></details>

#### CloudFormation

<details>
<summary>Explain what is CloudFormation</summary><br><b>
</b></details>

#### Costs

<details>
<summary>Are you familiar with Cost Explorer tool? Have you used it? What for exactly?</summary><br><b>
</b></details>

#### CloudFront

<details>
<summary>Explain what is CloudFront and what is it used for</summary><br><b>
</b></details>

<details>
<summary>Explain the following

- Origin
- Edge location
- Distribution
  </summary><br><b>
  </b></details>

<details>
<summary>What delivery methods available for the user with CDN?</summary><br><b>
</b></details>

<details>
<summary>True or False?. Objects are cached for the life of TTL</summary><br><b>

True
</b></details>

<details>
<summary>What is AWS Snowball?</summary><br><b>

A transport solution which was designed for transferring large amounts of data (petabyte-scale) into and out the AWS cloud.
</b></details>

##### Load Balancers

<details>
<summary>What types of load balancers are supported in EC2 and what are they used for?</summary><br><b>

- Application LB - layer 7 traffic
- Network LB - ultra-high performances or static IP address
- Classic LB - low costs, good for test or dev environments
  </b></details>

##### AWS Security

<details>
<summary>What is the shared responsibility model? In other words, what AWS is responsible for and what the user is responsible for in regards to Security?</summary><br><b>
</b></details>

<details>
<summary>What is the AWS compliance program?</summary><br><b>
</b></details>

<details>
<summary>Explain what each of the following services is used for

- AWS Inspector
- AWS Artifact
- AWS Shield</summary><br><b>
  </b></details>

<details>
<summary>What is AWS WAF? Give an example of how it can used and describe what resources or services you can use it with</summary><br><b>
</b></details>

<details>
<summary>What AWS VPN is used for?</summary><br><b>
</b></details>

<details>
<summary>What is the difference between Site-to-Site VPN and Client VPN?</summary><br><b>
</b></details>
<details>
<summary>True or False? AWS Inspector can perform both network and host assessments</summary><br><b>

True
</b></details>

#### AWS Databases

<details>
<summary>What is Amazon RDS?</summary><br><b>
</b></details>

<details>
<summary>What are some features or benefits of using RDS?</summary><br><b>

1. Multi AZ - great for Disaster Recovery
2. Read Replicas - for better performances
   </b></details>

<details>
<summary>What is AWS Redshift and how its different than RDS?</summary><br><b>
</b></details>

<details>
<summary>What do you if you suspect AWS Redshift performs slowly?</summary><br><b>

- You can confirm your suspicion by going to AWS Redshift console and see running queries graph. This should tell you if there are any long-running queries.
- If confirmed, you can query for running queries and cancel the irrelevant queries
- Check for connection leaks (query for running connections and include their IP)
- Check for table locks and kill irrelevant locking sessions
  </b></details>

<details>
<summary>What is EBS?</summary><br><b>
</b></details>

<details>
<summary>What is Amazon ElastiCache? For what cases it used?</summary><br><b>

Amazon Elasticache is a fully managed Redis or Memcached in-memory data store.  
It's great for use cases like two-tier web applications where the most frequently accesses data is stored in ElastiCache so response time is optimal.
</b></details>

<details>
<summary>What is Amazon Aurora</summary><br><b>

A MySQL & Postgresql based relational database.
Great for use cases like two-tier web applications that has a MySQL or Postgresql database layer and you need automated backups for your application.
</b></details>

<details>
<summary>What "AWS Database Migration Service" is used for?</summary><br><b>
</b></details>

#### AWS Networking

<details>
<summary>What is VPC?</summary><br><b>
</b></details>

<details>
<summary>What is an Elastic IP address?</summary><br><b>
</b></details>

<details>
<summary>Explain Security Groups and Network ACLs</summary><br><b>
</b></details>

#### Identify the service or tool

<details>
<summary>What would you use for easily creating similar AWS environments/resources for different customers?</summary><br><b>

CloudFormation
</b></details>

<details>
<summary>Using which service, can you add user sign-up, sign-in and access control to mobile and web apps?</summary><br><b>

Cognito
</b></details>

<details>
<summary>Which service would you use for building a website or web application?</summary><br><b>

Lightsail
</b></details>

<details>
<summary>Which tool would you use for choosing between Reserved instances or On-Demand instances?</summary><br><b>

Cost Explorer
</b></details>

<details>
<summary>What would you use to check how many unassociated Elastic IP address you have?</summary><br><b>

Trusted Advisor
</b></details>

<details>
<summary>What service allows you to transfer large amounts (Petabytes) of data in and out of the AWS cloud?</summary><br><b>

AWS Snowball
</b></details>

<details>
<summary>What provides a virtual network dedicated to your AWS account?</summary><br><b>

VPC
</b></details>

<details>
<summary>What you would use for having automated backups for an application that has MySQL database layer?</summary><br><b>

Amazon Aurora
</b></details>

<details>
<summary>What would you use to migrate on-premise Oracle database to AWS?</summary><br><b>

AWS Database Migration Service
</b></details>

<details>
<summary>What would you use to check why certain EC2 instances were terminated?</summary><br><b>

AWS CloudTrail
</b></details>

#### AWS Misc

<details>
<summary>Explain what are the following services and give an use case example for each one them:

- CloudTrail
- CloudWatch
- CloudSearch</summary><br><b>
  </b></details>

<details>
<summary>Explain what is AWS Lambda</summary><br><b>
</b></details>
