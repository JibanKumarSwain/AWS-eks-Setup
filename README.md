# AWS-eksctl


## AMAZON ELASTIC KUBERNETES SERVICE (EKS) NOTES

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

* Go to the AWS IAM console.

* Create a new IAM user named "eks-admin."

* Attach the "AdministratorAccess" policy to this user.

2. Create Security Credentials:

* After creating the user, generate an Access Key and Secret Access 
Key for this user.
# 4) Launch AWS instance and get access to the instance
# 5) Configure AWS CLI:
# 6) Configure the AWS CLI with the Access Key and Secret Access Key from 



# step 2:

curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

sudo apt install unzip

unzip awscliv2.zip

sudo ./aws/install -i /usr/local/aws-cli -b /usr/local/bin --update

$Error <If you're encountering an error at this stage, it may indicate an installation issue on your system, potentially related to the unzip package. To resolve this, you can install the unzip package using the command 'sudo apt-get install unzip">

## AMAZON ELASTIC KUBERNETES SERVICE (EKS) NOTES

# 7) Kubernetes tools setup:
aws configure

   # aws configure
 Install kubectl:
curl -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.28.3/2023-11-14/bin/linux/amd64/kubectl

chmod +x ./kubectl

sudo mv ./kubectl /usr/local/bin

kubectl version --short –client

# we can use this link for Documention(https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html)

 Install eksctl:
curl --silent --location 
"https://github.com/weaveworks/eksctl/releases/latest/download/
eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp

sudo mv /tmp/eksctl /usr/local/bin

eksctl version

# 8) EKS Cluster Setup:

 Use eksctl to create the EKS cluster

# NOTE: Make sure to replace <cluster-name> and <region> with your desired values

eksctl create cluster --name <cluster-name> --region <region> --node-type 
t2.micro --nodes-min 2 --nodes-max 2

 Update your kubeconfig to connect to the newly created EKS cluster:

# 9) Verify Nodes:

kubectl get nodes

# AMAZON ELASTIC KUBERNETES SERVICE (EKS) NOTES

Basic to Advanced EKS Commands 

1. Get Cluster Information

aws eks describe-cluster --name <cluster-name> --region <region>

2. List Worker Nodes

kubectl get nodes

3. Deploy an application

kubectl apply -f <yaml-file>

4. Scale a Deployment

 kubectl scale deployment < deployment-name> --replicas=<number>
 
5. View Pods in a Namespace

kubectl get pods -n <namespace>

6. Check Cluster Events

kubectl get events

7. Create a Persistent Volume

kubectl apply -f <pv-definition.yaml>

8. Apply a Rolling Update

kubectl set image deployment/< deployment-name> <container-name>=<new-image>

9. Enable Autoscaling

kubectl autoscale deployment < deployment-name> --min=3 --max=5

10. Delete the cluster
eksctl delete cluster --name <cluster-name> --region <region-name>



