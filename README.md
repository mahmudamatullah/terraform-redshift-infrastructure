# Amazon Redshift Infrastructure Provisioning (Terraform)
![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=flat&logo=amazon-aws&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-%235835CC.svg?style=flat&logo=terraform&logoColor=white)

## Overview

This project provisions a fully configured Amazon Redshift environment using Terraform, including custom networking components such as a VPC, subnets, route tables, and security groups.
The goal is to demonstrate how to build a data warehouse infrastructure from the ground up using Infrastructure as Code (IaC), without manual configuration in the AWS console.

## Infrastructure / Architecture
All resources are provisioned using Terraform and include:
- Custom VPC with DNS support enabled
- Public subnets across multiple availability zones
- Internet Gateway for external access
- Route tables and subnet associations
- Security group with PostgreSQL (port 5432) access
- Redshift-compatible networking setup

> The infrastructure is designed to support a Redshift cluster deployment with proper network isolation and connectivity.

## Key Components
🔹 VPC
  - CIDR block: 10.1.0.0/16
  - DNS support and hostnames enabled
🔹 Subnets
  - Two subnets across different availability zones
  - Enables high availability and proper cluster placement
🔹 Networking
  - Internet Gateway attached to VPC
  - Public route table allowing outbound internet access
🔹 Security Group
  - Inbound access on port 5432 (PostgreSQL/Redshift)
  - Open outbound traffic

## Tech Stack
- Terraform (Infrastructure as Code)
- AWS VPC (networking)
- AWS Redshift (network-ready setup)
- Security Groups & Routing

## How to Run
1. Prerequisites
  - AWS account
  - Terraform installed
- AWS credentials configured locally
  
2. Initialize Terraform
`terraform init`

3. Apply Infrastructure
`terraform apply`

4. Verify Resources
Check AWS Console for:
  - VPC
  - Subnets
  - Route tables
  - Security groups

## Key Features
- Fully reproducible infrastructure using Terraform
- Custom VPC and subnet design
- Multi-AZ subnet configuration
- Network setup aligned for Redshift deployment
- No manual AWS console configuration required
  
## Future Improvements
- Add Redshift cluster resource provisioning
- Restrict security group access (avoid 0.0.0.0/0)
- Introduce private subnets for better security
- Add IAM roles for Redshift access to S3
- Implement Terraform modules for reusability
