# AWS-Multi-Zone-Deployment-with-Terraform

This project demonstrates how to set up a highly available, load-balanced infrastructure for web applications on AWS using Terraform. By the end of this project, you will have created a Virtual Private Cloud (VPC), deployed two EC2 instances in different availability zones, set up a load balancer, and configured an S3 bucket for storage. This infrastructure is designed to improve the scalability and resilience of the application.

## Table of Contents
Overview
Architecture
Prerequisites
Getting Started
Project Structure
Usage
Cleanup


## Overview
In this project, we use Terraform as our Infrastructure as Code (IaC) tool to automate the deployment of AWS resources. The setup includes:
* A VPC with public subnets in multiple availability zones
* Two EC2 instances, each deployed in a different availability zone
* An Application Load Balancer to distribute traffic between the instances
* An Amazon S3 bucket for storing static assets or data
This configuration enhances application availability and reliability.

## Architecture

![image](https://github.com/user-attachments/assets/2992f944-5dd4-4723-91b8-907f5d3cb79d)

### Key Components
* VPC: Defines the network for our resources, ensuring a secure environment for the application.
* Subnets: Public subnets in different availability zones for improved fault tolerance.
* EC2 Instances: Hosts for the web application, deployed across multiple zones.
* Load Balancer: Distributes incoming traffic across the EC2 instances for load balancing.
* S3 Bucket: Provides object storage for static content or data required by the application.

## Prerequisites
* AWS Account: An AWS account with sufficient permissions to create resources.
* Terraform: Install Terraform to run the scripts.
* AWS CLI: Install and configure AWS CLI for access credentials.

### Terraform Setup
Configure your AWS credentials using the AWS CLI:
  - aws configure
Verify your Terraform installation:
  - terraform -v

## Getting Started
1. Clone the Repository: 
  - https://github.com/niral261/AWS-Multi-Zone-Deployment-with-Terraform.git
  - cd high-availability-aws-terraform
2. Initialize Terraform:
  - terraform init
3. Plan the Infrastructure Generate an execution plan to review what resources Terraform will create:
  - terraform plan
4. Deploy the Infrastructure Apply the Terraform configuration to set up resources on AWS:
  - terraform apply
Type yes when prompted to confirm.
5. Access the Load Balancer After the deployment, Terraform will output the DNS name of the load balancer. You can use this URL to access the web application.

## Project Structure
.
├── main.tf               # Main Terraform configuration file
├── variables.tf          # Input variables for AWS settings and resources
├── outputs.tf            # Output values such as Load Balancer DNS
├── provider.tf           # AWS provider configuration
├── modules/              # Optional directory for custom modules
└── README.md             # Project documentation

## Usage
* Application Access: Use the load balancer's DNS name to access the web application.
* Scaling: Adjust the instance count or add more availability zones in main.tf as needed.
* Logging and Monitoring: Enable CloudWatch monitoring (optional) for better insights.

## Cleanup
To delete all resources created by this project, run:
  - terraform destroy
Type yes to confirm. This will remove all infrastructure created by Terraform, including EC2 instances, subnets, the load balancer, and the S3 bucket.
