*Dynamic Website on AWS - DevOps Project*
This repository contains the infrastructure setup and deployment scripts for hosting a dynamic website on AWS. The project leverages several AWS services to ensure availability, scalability, security, and fault tolerance. The website is hosted using EC2 instances, an Application Load Balancer, Auto Scaling Groups, and other essential components. Below is an overview of the architecture and the services used.

*Architecture Overview*
VPC: A Virtual Private Cloud was configured with both public and private subnets, spanning across two Availability Zones for high availability and fault tolerance.

Internet Gateway: Deployed to enable internet connectivity for instances within the VPC.

Security Groups: Configured to act as a network firewall for controlling traffic into and out of the instances.

Availability Zones: Two Availability Zones were utilized to ensure reliability and fault tolerance for the web application.

Public Subnets: Hosted the NAT Gateway and Application Load Balancer, ensuring the necessary infrastructure was accessible from the internet.

EC2 Instance Connect Endpoint: Used for secure connections to EC2 instances in both public and private subnets.

Private Subnets: The EC2 instances hosting the website were deployed in private subnets to enhance security.

NAT Gateway: Allowed instances within private subnets (application and data layers) to access the internet for necessary updates and patches.

EC2 Instances: The website was hosted on multiple EC2 instances.

Application Load Balancer: Deployed to distribute incoming traffic evenly across the EC2 instances, ensuring efficient load distribution.

Auto Scaling Group: Automatically scaled the number of EC2 instances up or down based on traffic demands, ensuring that the website remains available and responsive.

SSL/TLS Certificates: Used AWS Certificate Manager to secure communications between the load balancer and the web servers.

Simple Notification Service (SNS): Configured to send alerts and notifications about events in the Auto Scaling Group.

Route 53: Managed domain name registration and DNS records, ensuring proper routing of traffic to the website.

S3 Bucket: Used to store application code and configuration files.

Deployment Overview
VPC and Subnets: The project begins by creating a VPC with both public and private subnets across two Availability Zones.

Internet Gateway and NAT Gateway: Configured to provide internet connectivity for instances in public subnets and allow private subnet instances to access the internet via the NAT Gateway.

EC2 Instances and Auto Scaling: Web servers were deployed on EC2 instances within private subnets. Auto Scaling ensured that instances scaled based on incoming traffic demands.

Load Balancing: The Application Load Balancer distributed traffic across EC2 instances within the Auto Scaling Group for optimal performance.

Security: AWS Security Groups were used to control inbound and outbound traffic to EC2 instances, and SSL/TLS certificates were applied to secure the website.

Monitoring and Notifications: SNS provided notifications related to Auto Scaling activities.

Domain Name and DNS: Route 53 was used to manage the website’s domain name and DNS settings.

Resources
VPC: Virtual Private Cloud (with public/private subnets)
EC2 Instances: Web servers (in private subnets)
Internet Gateway: For public internet connectivity
NAT Gateway: For internet access from private subnets
Security Groups: Network security settings
Auto Scaling Group: Automatic scaling of EC2 instances
Application Load Balancer: Traffic distribution across EC2 instances
Certificate Manager: For managing SSL/TLS certificates
SNS: Simple Notification Service for alerts
Route 53: Domain name registration and DNS routing
S3: Storage for application code
How to Use
Clone this repository:

bash
Copy code
git clone https://github.com/yourusername/your-repo-name.git
Navigate to the directory:

bash
Copy code
cd your-repo-name
Follow the instructions in the deployment.md file for setting up the infrastructure and deploying the website on AWS.
