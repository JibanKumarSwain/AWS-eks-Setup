# AWS-eksctl

##AMAZON ELASTIC KUBERNETES SERVICE (EKS) NOTES
# What is Amazon EKS?

 Amazon Elastic Kubernetes Service (EKS) is a managed Kubernetes service provided 
by AWS. It makes it easy to deploy, manage, and scale containerized applications 
using Kubernetes.

## Benefits of Amazon EKS 

Scalability: EKS allows you to scale your applications effortlessly as your 
requirements change.

High Availability: It offers a highly available and reliable environment for your 
applications.

Easy Management: AWS manages the control plane, so you can focus on your 
applications


 
## AMAZON ELASTIC KUBERNETES SERVICE (EKS) NOTES

# Setting up Amazon EKS:

# 1) Create an AWS Account

 If you haven't already, sign up for an AWS free tier account.

# 2) Install AWS CLI

 Install and configure the AWS Command Line Interface (CLI) on your 
local.
COMMANDS:

# 3) Create an IAM Role for EKS
 Create an IAM role with the necessary permissions for EKS.
STEPS:
1. Create an IAM User:
o Go to the AWS IAM console.
o Create a new IAM user named "eks-admin."
o Attach the "AdministratorAccess" policy to this user.
2. Create Security Credentials:
o After creating the user, generate an Access Key and Secret Access 
Key for this user.
4) Launch AWS instance and get access to the instance
5) Configure AWS CLI:
6) Configure the AWS CLI with the Access Key and Secret Access Key from 

# step 2:

curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

sudo apt install unzip

unzip awscliv2.zip

sudo ./aws/install -i /usr/local/aws-cli -b /usr/local/bin --updat
