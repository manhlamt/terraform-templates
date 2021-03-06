# Terraform template for AWS Elastic Load Balancer and Auto Scaling Group
You need to check and change the vars.tf as your need.

Elastic Load Balancing automatically distributes your incoming application traffic across multiple targets, such as EC2 instances. It monitors the health of registered targets and routes traffic only to the healthy targets. Elastic Load Balancing supports two types of load balancers: Application Load Balancers and Classic Load Balancers.

## Prerequisites
- Apply 01_vpc first
- AWS account
- AWS IAM access key
- AWS IAM secret key
- AWS region

## Installing
Terraform must first be installed on your machine
https://www.terraform.io/intro/getting-started/install.html

## How it works
```
terraform init          # Initialize the Terraform configuration
terraform plan          # See the resources which will be created
terraform apply         # Create the resources defined in all .tf files
terraform show          # Show the resources
terraform plan -destroy # See what will be removed
terraform destroy       # Remove the resources
```

## The below items will be created:
- Multi spot EC2 instances (root volume size is 30GB) in private subnets
- 1 Elastic Load Balancer
- 1 Launch Configuration
- 1 Auto Scaling Group