### A company needs to store large video files that are accessed frequently for the first few days after upload but are rarely accessed after that. Which storage solution is most cost-effective while maintaining high availability?

A) Amazon S3 Standard<br>
B) Amazon S3 Standard-Infrequent Access<br>
C) Amazon S3 Intelligent-Tiering<br>
D) Amazon S3 Glacier<be>

<details>
  <summary><i>Reveal answer</i></summary>
  
**The correct answer is C) Amazon S3 Intelligent-Tiering**

Explanation:
S3 Intelligent-Tiering is ideal for this scenario because:
- It automatically moves objects between access tiers based on usage patterns
- Files that are frequently accessed stay in the frequent access tier
- Files that become infrequent are automatically moved to the infrequent access tier
- This happens without performance impact or operational overhead
- It's specifically designed for workloads with changing access patterns
</details>

---

### A company is running a web application that processes sensitive payment information. Which TWO security measures should they implement to protect data in transit? (Select TWO)

A) Enable SSL/TLS termination on the Application Load Balancer<br>
B) Create a customer master key (CMK) in AWS KMS<br>
C) Configure SSL/TLS certificates on EC2 instances<br>
D) Enable default encryption on S3 buckets<br>
E) Use AWS Shield Standard

<details>
  <summary><i>Reveal answer</i></summary>
  
**The correct answers are A and C:**
- Enable SSL/TLS termination on the Application Load Balancer
- Configure SSL/TLS certificates on EC2 instances

Explanation:
To protect data in transit, you need end-to-end encryption:
- SSL/TLS termination at the ALB (answer A) encrypts traffic between clients and the load balancer
- SSL/TLS certificates on EC2 (answer C) encrypts traffic between the load balancer and the instances
</details>

---

### A solutions architect needs to ensure that all new EBS volumes created in the account are automatically encrypted. Which approach requires the LEAST operational overhead?

A) Create an AWS Lambda function triggered by CloudWatch Events<br>
B) Enable EBS encryption by default in the region<br>
C) Create an AWS Config rule<br>
D) Use AWS CloudTrail to monitor volume creation

<details>
  <summary><i>Reveal answer</i></summary>
  
**The correct answer is B) Enable EBS encryption by default in the region**

Explanation:
- This is a simple account-level setting that requires no additional maintenance
- Once enabled, all new EBS volumes are automatically encrypted
- It applies to all volume types and snapshots
- No need to write code or create additional resources
- It can be enabled with a single API call or console click

The other options would be more complex:
- Lambda function (A) would require code maintenance and error handling
- AWS Config rule (C) would only detect non-compliance, not prevent it
- CloudTrail (D) would only provide logging, not enforcement
</details>

---

### A company has a three-tier web application that needs to scale based on demand. The application servers need to scale faster than the database tier. Which combination of AWS services should they use?

A) EC2 Auto Scaling group with Application Load Balancer and RDS Multi-AZ<br>
B) EC2 Auto Scaling group with Application Load Balancer and RDS Read Replicas<br>
C) EC2 Auto Scaling group with Network Load Balancer and RDS Multi-AZ<br>
D) EC2 Auto Scaling group with Network Load Balancer and Aurora Auto Scaling

<details>
  <summary><i>Reveal answer</i></summary>
  
**The correct answer is B) EC2 Auto Scaling group with Application Load Balancer and RDS Read Replicas**

Explanation:
- Application Load Balancer works best for HTTP/HTTPS traffic
- EC2 Auto Scaling group allows the application tier to scale quickly based on demand
- RDS Read Replicas provide read scaling for the database tier
- This combination allows for independent scaling of both tiers

The other options are less suitable because:
- RDS Multi-AZ (A, C) provides high availability but not scalability
- Network Load Balancer (C, D) is better suited for TCP/UDP traffic
- Aurora Auto Scaling (D) would work but is more expensive and may be overkill
</details>

---

### A company has compliance requirements to encrypt all data at rest. They use an S3 bucket for storing application data. Which methods can be used to ensure all objects uploaded to the bucket are encrypted? (Select TWO)

A) Enable default encryption on the S3 bucket<br>
B) Create a bucket policy that denies PutObject requests without encryption headers<br>
C) Enable versioning on the S3 bucket<br>
D) Enable MFA Delete on the S3 bucket<br>
E) Configure a lifecycle policy

<details>
  <summary><i>Reveal answer</i></summary>
  
**The correct answers are A and B:**
- Enable default encryption on the S3 bucket
- Create a bucket policy that denies PutObject requests without encryption headers

Explanation:
- Default encryption (A) ensures objects are encrypted if no encryption parameters are specified
- A bucket policy (B) enforces encryption by denying uploads that don't specify encryption
- Using both provides defense in depth by having multiple controls

The other options don't help with encryption:
- Versioning (C) maintains multiple versions of objects
- MFA Delete (D) adds deletion protection
- Lifecycle policies (E) manage object transitions and expiration
</details>

---

### A company needs to run a batch processing workload that can be interrupted and resumed without issues. The workload needs to be cost-effective and complete within 24 hours. Which EC2 instance purchasing option should they choose?

A) On-Demand Instances<br>
B) Reserved Instances<br>
C) Spot Instances<br>
D) Dedicated Hosts<be>

<details>
  <summary><i>Reveal answer</i></summary>
  
**The correct answer is C) Spot Instances**

Explanation:
- Spot Instances are the most cost-effective option (up to 90% cheaper than On-Demand)
- Since the workload can be interrupted and resumed, it's perfect for Spot Instances
- The 24-hour completion window allows for potential interruptions
- Batch processing is an ideal use case for Spot Instances
</details>

---

### A solutions architect needs to design a solution for storing session state for a web application. The solution must be highly available and provide sub-millisecond latency. Which service should they use?

A) Amazon DynamoDB<br>
B) Amazon ElastiCache for Redis<br>
C) Amazon RDS Multi-AZ<br>
D) Amazon S3<be>

<details>
  <summary><i>Reveal answer</i></summary>
  
**The correct answer is B) Amazon ElastiCache for Redis**

Explanation:
- ElastiCache for Redis is an in-memory data store with sub-millisecond latency
- It provides high availability through Multi-AZ replication
- Redis is particularly well-suited for session management
- It includes built-in support for common session management patterns

The other options are less suitable because:
- DynamoDB (A) has millisecond latency, not sub-millisecond
- RDS Multi-AZ (C) is too slow for session state management
- S3 (D) has too high latency for session management
</details>

---

### A company wants to migrate its on-premises application to AWS. The application requires shared file storage that can be mounted on multiple EC2 instances concurrently. Which storage solution should they use?

A) Amazon EBS<br>
B) Amazon S3<br>
C) Amazon EFS<br>
D) Instance Store

<details>
  <summary><i>Reveal answer</i></summary>
  
**The correct answer is C) Amazon EFS**

Explanation:
- EFS provides scalable file storage in the AWS Cloud
- It supports thousands of concurrent NFS connections
- Multiple EC2 instances can read and write simultaneously
- It's a fully managed service that automatically scales

The other options are not suitable because:
- EBS volumes (A) can only be attached to one EC2 instance at a time
- S3 (B) is object storage and cannot be mounted as a file system
- Instance Store (D) is temporary storage tied to a single instance
</details>

---

### A company needs to design a disaster recovery solution for its application. They require a Recovery Time Objective (RTO) of less than 10 minutes and a Recovery Point Objective (RPO) of less than 1 minute. Which disaster recovery strategy should they implement?

A) Backup and Restore<br>
B) Pilot Light<br>
C) Warm Standby<br>
D) Multi-Site Active/Active

<details>
  <summary><i>Reveal answer</i></summary>
  
**The correct answer is D) Multi-Site Active/Active**

Explanation:
- An RTO of less than 10 minutes and an RPO of less than 1 minute requires an always-on solution
- Multi-Site Active/Active provides:
  - Near-zero RTO (immediate failover)
  - Near-zero RPO (continuous replication)
  - No downtime during failover
  - Traffic distribution across multiple regions
</details>

---

### A company runs a critical application that must be highly available. Which combination of AWS services should they use to monitor the application and receive notifications when issues occur? (Select TWO)

A) Amazon CloudWatch for metrics and alarms<br>
B) AWS CloudTrail for API logging<br>
C) Amazon SNS for notifications<br>
D) Amazon SQS for message queuing<br>
E) AWS Config for resource tracking

<details>
  <summary><i>Reveal answer</i></summary>
  
**The correct answers are A and C:**
- Amazon CloudWatch for metrics and alarms
- Amazon SNS for notifications

Explanation:
- CloudWatch (A) monitors applications and infrastructure metrics
- SNS (C) delivers notifications via multiple protocols (email, SMS, etc.)
- Together they create a complete monitoring and alerting solution

The other options are less suitable because:
- CloudTrail (B) is for API activity auditing
- SQS (D) is for application message queuing
- AWS Config (E) tracks resource configuration changes
</details>

---

### A company stores sensitive data in an S3 bucket. They need to ensure that objects are encrypted with keys managed by their organization. Which encryption solution should they use?

A) Server-Side Encryption with S3 managed keys (SSE-S3)<br>
B) Server-Side Encryption with KMS keys stored in AWS KMS (SSE-KMS)<br>
C) Server-Side Encryption with Customer Provided Keys (SSE-C)<br>
D) Client-Side Encryption with keys managed by the customer

<details>
  <summary><i>Reveal answer</i></summary>
  
**The correct answer is B) Server-Side Encryption with KMS keys stored in AWS KMS (SSE-KMS)**

Explanation:
- SSE-KMS provides control over the encryption keys while leveraging AWS services
- It allows the organization to manage their keys in AWS KMS
- Provides an audit trail of key usage through CloudTrail
- Enables permission control for key usage


The other options:
- SSE-S3 (A) uses keys managed by AWS, not the organization
- SSE-C (C) requires sending keys with each request, adding complexity
- Client-Side Encryption:
  - While this provides maximum control, it's more complex to manage
  - Requires significant development effort
  - Places encryption burden on the application
  - May impact performance
</details>

---

### A company runs a web application that needs to store session data with automatic scaling and high availability. The data must persist after instance termination. Which solution should they use?

A) Store session data on EBS volumes<br>
B) Store session data in DynamoDB<br>
C) Store session data on instance store volumes<br>
D) Store session data on EFS<be>

<details>
  <summary><i>Reveal answer</i></summary>
  
**The correct answer is B) Store session data in DynamoDB**

Explanation:
- DynamoDB provides automatic scaling
- Offers consistent single-digit millisecond latency
- Data persists independently of EC2 instances
- Fully managed with high availability across multiple AZs
- No maintenance required

The other options are less suitable because:
- EBS volumes (A) can only attach to one EC2 instance at a time
- Instance store volumes (C) are temporary and data is lost on instance termination
- EFS (D) while persistent and shared, has higher latency and is more suitable for file storage
</details>

---

### A company needs to analyze large amounts of data stored in S3 using SQL queries. They want the most cost-effective solution that doesn't require managing servers. Which service should they use?

A) Amazon RDS<br>
B) Amazon Redshift<br>
C) Amazon Athena<br>
D) Amazon EMR<be>

<details>
  <summary><i>Reveal answer</i></summary>
  
**The correct answer is C) Amazon Athena**

Explanation:
- Athena is serverless - no infrastructure to manage
- Pay only for the queries you run
- Directly queries data in S3 using standard SQL
- No need to load or transform data
- Most cost-effective for ad-hoc queries on S3 data

The other options:
- RDS (A) is a relational database service, not designed for large-scale data analysis
- EMR (D) is more complex and expensive for simple SQL queries on S3 data
- Amazon Redshift would not be the best choice because:
  - Requires cluster provisioning and management
  - Has fixed costs even when not in use
  - Better suited for complex queries on structured data warehouses
  - Requires data loading before querying
</details>

---

### A solutions architect needs to connect multiple VPCs across different AWS regions for a global application. The solution must provide the highest available bandwidth with consistent latency. Which service should they use?

A) VPC Peering<br>
B) AWS Transit Gateway<br>
C) AWS Direct Connect<br>
D) AWS Transit Gateway Inter-Region Peering

<details>
  <summary><i>Reveal answer</i></summary>
  
**The correct answer is D) AWS Transit Gateway Inter-Region Peering**

Explanation:
- Transit Gateway Inter-Region Peering is specifically designed for connecting VPCs across regions
- Uses AWS global network backbone for consistent latency
- Provides high bandwidth and encrypted communication
- Centrally manages routing between regions
- Scales easily as you add more VPCs

The other options:
- Transit Gateway (B) alone is regional and can't connect cross-region VPCs
- Direct Connect (C) is for connecting on-premises networks to AWS, not VPC-to-VPC connectivity
- VPC Peering (A) would not be the best choice because:
  - While VPC Peering can work across regions, it creates a mesh topology
  - Becomes complex to manage as the number of VPCs increases
  - Requires managing multiple peering connections
  - Doesn't provide the same level of routing control as Transit Gateway
</details>

---

### A company needs to set up a hybrid cloud architecture where they can access their AWS VPC resources from their on-premises network securely. Which TWO services can provide this connectivity? (Select TWO)

A) AWS Direct Connect<br>
B) Amazon API Gateway<br>
C) AWS Site-to-Site VPN<br>
D) AWS ClientVPN<br>
E) AWS Global Accelerator

<details>
  <summary><i>Reveal answer</i></summary>
  
**The correct answers are A and C:**
- AWS Direct Connect
- AWS Site-to-Site VPN

Explanation:
- Direct Connect provides dedicated private network connectivity
  - Lower latency and consistent network performance
  - Not dependent on internet connectivity
  - Higher security and bandwidth

- Site-to-Site VPN provides secure IPSec connections over the internet
  - Quick to set up
  - Lower cost than Direct Connect
  - Encrypted connection

The other options are not suitable for hybrid connectivity because:
- API Gateway (B) is for managing APIs, not network connectivity
- ClientVPN (D) is for individual user remote access
- Global Accelerator (E) improves availability and performance but doesn't provide private connectivity
</details>
---

### A company runs a web application that needs to accommodate rapidly changing workloads. During peak hours, the application receives 10 times more traffic than during off-peak hours. Which of the following would help manage costs while ensuring performance? (Select TWO)

A) Use Reserved Instances for the baseline capacity<br>
B) Use On-Demand Instances for all servers<br>
C) Use Spot Instances for the baseline capacity<br>
D) Use Auto Scaling groups with target-tracking policies<br>
E) Use dedicated hosts for all instances

<details>
  <summary><i>Reveal answer</i></summary>
  
**The correct answers are A and D:**
- Use Reserved Instances for the baseline capacity
- Use Auto Scaling groups with target-tracking policies

Explanation:
- Reserved Instances (A) provide significant cost savings for baseline capacity
  - Best for predictable minimum load
  - Up to 72% cheaper than On-Demand

- Target tracking scaling policies (D) automatically adjust capacity
  - Scales based on metrics like CPU utilization or request count
  - Maintains target performance during peak times
  - Only pays for additional capacity when needed

The other options are less suitable because:
- On-Demand Instances (B) for all servers would be more expensive
- Spot Instances (C) aren't reliable enough for baseline capacity
- Dedicated Hosts (E) would significantly increase costs
</details>

---

### A company has a VPC with both public and private subnets. The instances in the private subnet need to download software updates from the internet, but should not be directly accessible from the internet. Which combination of resources should be used?

A) Internet Gateway and Route Table<br>
B) NAT Gateway and Route Table<br>
C) VPC Endpoint and Security Group<br>
D) VPC Peering and Network ACL

<details>
  <summary><i>Reveal answer</i></summary>
  
**The correct answer is B) NAT Gateway and Route Table**

Explanation:
- NAT Gateway allows instances in private subnets to access the internet
- Traffic flows: Private Instance → NAT Gateway → Internet Gateway → Internet
- NAT Gateway must be placed in a public subnet
- The private subnet's route table needs a route to the NAT Gateway for internet-bound traffic (0.0.0.0/0)
- Provides one-way access (outbound only)

The other options wouldn't work because:
- Internet Gateway (A) would make the instances directly accessible from the internet
- VPC Endpoint (C) is for accessing AWS services, not the internet
- VPC Peering (D) is for connecting VPCs, not accessing the internet
</details>

---

### A company has a Lambda function that processes images. Some images can take up to 15 minutes to process. Which solution would help handle these long-running tasks?

A) Increase the Lambda timeout to 15 minutes<br>
B) Use Step Functions to orchestrate multiple Lambda functions<br>
C) Enable Lambda Provisioned Concurrency<br>
D) Configure Lambda with higher memory allocation

<details>
  <summary><i>Reveal answer</i></summary>

**The correct answer is B) Use Step Functions to orchestrate multiple Lambda functions**

Explanation:
- Lambda has a maximum timeout of 15 minutes
- Step Functions can:
  - Break down long-running processes into smaller steps
  - Handle timeouts and retries
  - Maintain state between executions
  - Run workflows that last up to 1 year

The other options wouldn't solve the problem:
- (A) wouldn't work because Lambda functions cannot run longer than 15 minutes
- Provisioned Concurrency (C) improves cold start times but doesn't extend runtime
- Higher memory (D) might speed up execution but won't extend the 15-minute limit
</details>

---

### A company needs to host a web application that stores user session data. The application must be highly available and maintain session data if an instance fails. Which combination should they use?

A) Application Load Balancer with sticky sessions<br>
B) Network Load Balancer with sticky sessions and ElastiCache<br>
C) Application Load Balancer with ElastiCache<br>
D) Network Load Balancer with shared EBS volume

<details>
  <summary><i>Reveal answer</i></summary> 

**The correct answer is C) Application Load Balancer with ElastiCache**

Explanation:
- Application Load Balancer (ALB) provides layer 7 load balancing
- ElastiCache provides in-memory session storage that's:
  - Highly available
  - Accessible from all instances
  - Sub-millisecond latency
  - Automatically scalable

The other options are less suitable because:
- Sticky sessions (A) don't protect against instance failures
- Network Load Balancer (B, D) is Layer 4 and not ideal for web applications
- Shared EBS volume (D) can only attach to one instance at a time
</details>

---

### A company runs a data processing application that operates on highly sensitive data. They need to ensure the encryption keys are stored in a FIPS 140-2 Level 3 validated hardware security module (HSM). Which service should they use?

A) AWS KMS<br>
B) CloudHSM<br>
C) Secrets Manager<br>
D) Systems Manager Parameter Store<br>

<details>
  <summary><i>Reveal answer</i></summary> 

**The correct answer is B) CloudHSM**

Explanation:
- AWS CloudHSM provides dedicated Hardware Security Modules (HSMs)
- It's the only AWS service that offers FIPS 140-2 Level 3 validated HSMs
- Gives you single-tenant access to the physical HSM device
- You have complete control over encryption keys

The other options don't meet the FIPS 140-2 Level 3 requirement:
- AWS KMS (A) is FIPS 140-2 Level 2 validated
- Secrets Manager (C) uses KMS for encryption
- Parameter Store (D) also uses KMS for encryption when using SecureString

This is a technical question about a specific compliance requirement. It's good to remember that CloudHSM is always the answer when you see requirements for:
- FIPS 140-2 Level 3
- Dedicated HSM hardware
- Complete control over key management
</details>

---

### A company needs to implement a solution for their website that can survive the failure of an entire AWS region. Which combination of services should they use? (Select TWO)

A) Route 53 with health checks<br>
B) Application Load Balancer<br>
C) Multi-region Active-Active deployment<br>
D) CloudFront with S3 bucket<br>
E) Single region with multiple Availability Zones

<details>
  <summary><i>Reveal answer</i></summary>

**The correct answers are A and C:**
- Route 53 with health checks
- Multi-region Active-Active deployment

Explanation:
- Route 53 with health checks can:
  - Monitor endpoint health
  - Automatically route traffic away from failed regions
  - Provide global DNS resolution
  - Support various routing policies

- Multi-region Active-Active deployment:
  - Runs the application simultaneously in multiple regions
  - Provides true region-level disaster recovery
  - Allows for serving users from the closest region
  - Enables business continuity during regional failures

The other options don't provide region-level failure protection:
- Application Load Balancer (B) is regional, not global
- CloudFront with S3 (D) is good for static content but not complete applications
- Multiple AZs (E) only protect against AZ failures within a region
</details>

---
