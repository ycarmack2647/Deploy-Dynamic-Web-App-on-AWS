Dynamic Web App on AWS
Overview

This project demonstrates the setup and deployment of a dynamic web application hosted on AWS, utilizing multiple AWS services for robust, scalable, and secure operation. This application is built with EC2, RDS, S3, and more, configured for high availability and fault tolerance across multiple availability zones.
Architecture

    VPC Configuration: Configured with public and private subnets across two availability zones.
    Internet Gateway: Allows connectivity between the VPC and the internet.
    Security Groups: Acts as a network firewall for managing traffic.
    EC2 Instances: Hosted within private subnets for enhanced security.
    Application Load Balancer (ALB): Distributes incoming web traffic across multiple EC2 instances.
    Auto Scaling: Manages the number of EC2 instances dynamically based on traffic.
    RDS MySQL: Provides a managed relational database service for storing application data.
    S3: Used for storing static content and deployment artifacts.
    Route 53: Manages DNS for the application's domain.
    SNS: Notification service for operational alerts.

Pre-requisites

    AWS account
    Basic understanding of AWS services
    Linux command line

Installation Steps

    Setup VPC and Subnets:
        Ensure that the VPC spans two availability zones with public and private subnets.
    Deploy Internet Gateway:
        Attach the internet gateway to your VPC.
    Security Groups Configuration:
        Properly configure security groups to manage allowed inbound and outbound traffic.
    Launch EC2 Instances:
        Use the provided AMI or your custom AMI to launch EC2 instances in the private subnets.
    Configure Load Balancer:
        Setup an Application Load Balancer in the public subnet.
    Setup Auto Scaling:
        Configure the Auto Scaling Group to manage the EC2 instances.

Deployment Scripts

bash

#!/bin/bash
# Update packages and install Apache, PHP, and MySQL
sudo yum update -y
sudo yum install -y httpd
sudo systemctl enable httpd
sudo systemctl start httpd

# Additional commands are provided in the repository for setting up the environment.

Configuring the Application

    Database Configuration: Set up MySQL on RDS and configure your application to connect to it.
    S3 Integration: Utilize S3 for storing deployment artifacts and static content.
    Environment Setup: Use the provided scripts to configure your EC2 instances and deploy your application code.

Maintaining the Application

    Monitor application performance and adjust Auto Scaling policies as necessary.
    Keep security groups and route tables up to date to ensure secure and efficient network traffic.

Contributing

Contributions to this project are welcome. Please fork the repository and submit a pull request.
