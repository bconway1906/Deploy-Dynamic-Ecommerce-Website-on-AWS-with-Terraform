# DevOps Project: Hosting a Dynamic Ecommerce Website on AWS with Terraform

<img width="468" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/a51d564c-14ad-4612-9040-0dcdb6990963">

## Overview

This DevOps project aims to host a dynamic ecommerce website on Amazon Web Services (AWS) using Terraform. The project utilizes various AWS services to ensure high availability, scalability, and fault tolerance of the website.

<img width="314" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/cbaeb7fa-064d-4719-ab5b-e318667e1927">

## Detailed Instructions

### Key Pairs

1. **Generate Key Pairs:**
   - Generate SSH key pairs on your local computer using the command: `ssh-keygen -t rsa`.
   - This generates a public and private key pair which will be used for authentication.

2. **GitHub Integration:**
   - Add the public SSH key to your GitHub account to enable seamless authentication when interacting with repositories.
  
   <img width="221" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/16870321-a226-455a-a5f4-e3587909968d">

### GitHub Repository

1. **GitHub Setup:**
   - Sign up for a GitHub account if you haven't already.
   - Create a new repository named "terraform-projects" and select the appropriate .gitignore template for Terraform.
  
    <img width="341" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/3d699dfc-9a7a-461e-a855-8e08aec0f840">

2. **Clone Repository:**
   - Clone the newly created repository to your local machine using the Git command: `git clone <repository_url>`.

### AWS CLI and IAM Setup

1. **AWS CLI Installation:**
   - Install the AWS Command Line Interface (CLI) on your local machine to manage AWS services.

2. **IAM User Creation:**
   - Create an IAM user with administrative access in the AWS Management Console.
   - Generate access keys for programmatic access to AWS services.

3. **AWS CLI Configuration:**
   - Configure the AWS CLI on your local machine using the `aws configure` command with the IAM user's credentials.

### Terraform Initialization

1. **Install Terraform:**
   - Install Terraform on your local machine. On macOS, you can use Homebrew for installation.

2. **Initialize Terraform Project:**
   - Initialize a new Terraform project in your cloned repository using the `terraform init` command.

### S3 Bucket for Terraform State

1. **S3 Bucket Setup:**
   - Create an S3 bucket in AWS to store Terraform state files.
   - Enable versioning on the S3 bucket to track changes over time.

### Locking Terraform State

1. **DynamoDB Setup:**
   - Create a DynamoDB table to lock Terraform state files and prevent concurrent modifications.

### VPC Creation

<img width="287" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/02258041-5f23-40d3-9588-dc0bcaeec53c">

1. **VPC Configuration:**
   - Define the Virtual Private Cloud (VPC) infrastructure, including public and private subnets across multiple availability zones (AZs).

2. **Terraform Execution:**
   - Create VPC resources using Terraform by defining the VPC, subnets, route tables, and associations.
   - Execute `terraform plan` and `terraform apply` to provision resources in the AWS account.

     <img width="319" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/c51973ba-3536-46f5-a5c6-6a7b40fc3711">
     <img width="317" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/5e779e2e-b76d-40c9-912a-0be80f38ffef">
### Nat Gateway

<img width="311" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/d140a394-2995-4b41-bbbe-c150b900f51b">

1. **Nat Gateway Configuration:**
   - Set up Nat Gateways to allow instances in private subnets to access the internet securely.

2. **Execution:**
   - Define Nat Gateway resources in Terraform and associate them with appropriate subnets.
   - Apply changes using `terraform apply`.
  
     <img width="313" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/dabeacaf-ab82-40fe-b252-e7e803964521">

### Security Groups

<img width="286" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/c12e522c-7a0f-48ab-b1d9-56dd9b98d22e">

1. **Security Group Setup:**
   - Create security groups for the Application Load Balancer (ALB), SSH, web servers, and database to control inbound and outbound traffic.

2. **Execution:**
   - Define security group rules in Terraform configuration files.
   - Apply changes using `terraform apply`.

<img width="253" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/a164f6d0-efe2-4dc1-8d7d-1a8db643f7c6">
<img width="341" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/2fa89008-be84-40e5-820a-cf4c80c24867">

### RDS Database

<img width="306" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/e6eeeaf0-64d3-4018-a7af-1ce94717d327">

1. **RDS Configuration:**
   - Define parameters for the RDS database, including instance type, storage, and backup settings.

2. **Execution:**
   - Use Terraform to create the RDS database instance.
   - Apply changes using `terraform apply`.
  
   <img width="382" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/937c295a-9c34-4c0a-804f-71a6a12920f4">

### SSL Certificate

1. **Certificate Creation:**
   - Obtain an SSL certificate from AWS Certificate Manager (ACM) to enable secure communication over HTTPS.
  
   <img width="336" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/e35ba5ad-95cd-450e-80c3-cd14acddb937">

### Application Load Balancer (ALB)

<img width="277" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/b3de776d-13bf-4416-84b9-6c438e4d059d">

1. **ALB Configuration:**
   - Define settings for the Application Load Balancer, including listeners, target groups, and routing rules.

2. **Execution:**
   - Use Terraform to provision the ALB resources.
   - Apply changes using `terraform apply`.
  
   <img width="301" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/b6f8a0ac-1fbb-4898-af13-1d6363002fc0">

### ECS Roles and Tasks

1. **ECS Role Definition:**
   - Create IAM roles for ECS task execution and service deployment.

2. **Task Configuration:**
   - Define ECS tasks and container definitions for the application components.
  
   <img width="302" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/369380e9-0be6-4972-9c47-785e84cd8b4c">

   <img width="310" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/cadcc41b-c2bb-4765-a2b5-691c388a18be">

   <img width="362" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/65f8592e-8b6d-4d9d-84c5-41157db71c0a">

### Auto Scaling Group (ASG)

<img width="289" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/32882e41-dce9-4779-a71d-ed792e7d85e1">

1. **ASG Setup:**
   - Implement an Auto Scaling Group to dynamically manage EC2 instances based on demand.

2. **Execution:**
   - Define ASG parameters and scaling policies in Terraform configuration files.
   - Apply changes using `terraform apply`.
  
   <img width="352" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/599a598f-68d9-4915-94e3-b1ee90a9c945">

### Route 53 and Outputs

1. **Route 53 Configuration:**
   - Set up DNS records in Route 53 for domain resolution.

2. **Output Definition:**
   - Define Terraform outputs to display important resource information after provisioning.
  
   
<img width="369" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/c7da6623-af84-4cb8-89d7-16a01f04668c">

<img width="468" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/c51eaa17-de3a-4c8b-a0d5-79cba6fe9619">

<img width="468" alt="image" src="https://github.com/bconway1906/Deploy-Dynamic-Ecommerce-Website-on-AWS-with-Terraform/assets/148906255/4a3039b4-3bc8-40dd-b670-bf8b81a5ecc7">

### Clean-Up

1. **Resource Deletion:**
   - Use `terraform destroy` to remove all provisioned resources from the AWS environment.

## Conclusion

This detailed guide provides step-by-step instructions for hosting a dynamic ecommerce website on AWS using Terraform. Follow the outlined process to efficiently manage infrastructure resources and ensure the reliability of your application.
