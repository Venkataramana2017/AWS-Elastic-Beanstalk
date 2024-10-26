# AWS-Elastic-Beanstalk

# AWS Resources Needed
Compute Resources:

# Amazon EC2 (Elastic Compute Cloud): For manually managing compute resources or specialized requirements. The existing MongoDB server is already running on an EC2 instance.
Elastic Beanstalk: Currently used to deploy the application server and worker services, which abstracts EC2 but can still use underlying EC2 instances or other compute resources (Elastic Load Balancer, Auto Scaling, etc.).
Alternative Compute: EC2 instances can also be provisioned directly if needed.
AWS Lambda: Serverless compute can be an option for certain backend tasks or functions, especially those triggered by events.
Database:

# Amazon DocumentDB (Optional): If you want a managed service that is compatible with MongoDB, Amazon DocumentDB would replace the current MongoDB running on EC2, offering better scalability, availability, and automated backups.
EC2 for MongoDB: Continue using an EC2 instance with MongoDB installed as in the current setup.
Storage:

# Amazon S3 (Simple Storage Service): Already used for storing uploaded files from users.
S3 Lifecycle Policies: To manage data lifecycle by automatically transitioning objects between storage classes or deleting old objects.
Networking:

# Amazon VPC (Virtual Private Cloud): To securely deploy EC2 instances, Elastic Beanstalk, MongoDB, and other services. The VPC can be configured with subnets (public and private) and security groups for access control.
Elastic Load Balancer (ELB): For distributing traffic across multiple EC2 instances or Beanstalk environments.
Amazon Route 53: For DNS management and domain name routing to your application.
NAT Gateway: If private subnets are used, a NAT gateway may be required to allow internet access for instances running in private subnets.
Logging and Monitoring:

#5.Amazon OpenSearch Service (formerly Elasticsearch): If you wish to migrate from manually configured OpenSearch, AWS provides a managed OpenSearch service for logging and searching logs.
Amazon CloudWatch: For monitoring infrastructure, logging application events, and setting up alarms for system health checks.
'6.AWS X-Ray: For tracing requests through your distributed services.
Security and Access Control:

#7.AWS IAM (Identity and Access Management): For managing access to AWS resources and setting up fine-grained permissions for users, services, and roles.
AWS Secrets Manager or Parameter Store: To securely store and manage sensitive configuration data (e.g., API keys, database credentials).
File Distribution:

#8.Amazon CloudFront: For serving the React front end efficiently with content distribution and caching.
Messaging (Optional):

Amazon SQS (Simple Queue Service): If the worker service or other services require message queuing for background tasks or decoupling services.
Amazon SNS (Simple Notification Service): For sending notifications or alerts within the application or to external systems.
