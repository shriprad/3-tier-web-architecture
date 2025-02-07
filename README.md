Architecture components

The reference architecture illustrates a complete best practice deployment for a WordPress website on AWS.

It starts with edge caching in Amazon CloudFront (1) to cache content close to end users for fasterdelivery.

CloudFront pulls static content from an S3 bucket (2) and dynamic content from an Application Load Balancer (4) in front of the web instances.

The web instances run in an Auto Scaling group of Amazon EC2instances (6).

An ElastiCache cluster (7) caches frequently queried data tospeed up responses.

An Amazon Aurora MySQL instance (8) hosts the WordPress database.

The WordPress EC2 instances access shared WordPress data on an Amazon EFS file system via an EFS Mount Target (9) in each Availability Zone.

An Internet Gateway (3) enables communication between resources in your VPC and the internet.

NAT Gateways (5) in each Availability Zone enable EC2 instances in private subnets (App and Data) to access the internet.
