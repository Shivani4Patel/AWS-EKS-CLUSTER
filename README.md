# AWS-EKS-CLUSTER

AWS EKS CLUSTER
#
aws
#
eks
#
awschallenge
#
kubernetes
set up and deploy a scalable Kubernetes cluster on AWS using EKS, allowing for the efficient deployment of containerized applications.

1. Create a VPC Along with Subnet, Route Table, and Internet Gateway
Begin by creating a custom Virtual Private Cloud (VPC).
Set up subnets, route tables, and internet gateways for network traffic management within the VPC.

Image description

Image description

Image description

2. Create IAM Roles
Create two IAM roles:
One for the EKS cluster.
Another for EC2 nodes (worker nodes).

Image description

Image description

**

Create the EKS Cluster** Navigate to the EKS dashboard and create a cluster. Assign the name and role to the cluster, and AWS will provision it automatically. Under network settings, select private subnets and keep other settings at default. Once created, the EKS cluster will be running, and you can observe the creation of the two pods.
Image description

Image description

Image description

Image description

Image description

**

Create a Node Group** Create a node group for the cluster. Select the instance type (e.g., t2.micro) and configure the scaling parameters (e.g., desired size: 1, minimum size: 1, maximum size: 1). After successful creation, three worker pods will be available.
Image description

Image description

Image description

Image description

Image description

Image description

5. Install AWS CLI and Minikube
Download AWS CLI and Minikube.
Check their versions and configure AWS CLI using your access keys.
Update the EKS cluster and deploy the necessary configurations using deployment.yaml.
Verify that pods are running and the deployment is created (e.g., deployment-2048).

Image description

Image description

Image description

Image description

Image description

6. Manage Tags
Edit public subnets and add tags.
Assign an Elastic Load Balancer (ELB) role by adding relevant tags.
Copy the cluster URL for future use.

Image description

Image description

Image description

Image description

**

Configure IAM Identity Provider** Go to the IAM Identity Provider section in the AWS Management Console. Paste the cluster URL and set the audience to sts.amazon.com.
Image description

Image description

8. Create Policies Through JSON
Create a policy via a JSON file for the Load Balancer Controller.
Name the policy and modify the custom trust policy by adding the necessary account and role details.
Attach the generated ARN URL to the service YAML file and apply the ingress.yaml to complete the setup.

Image description

Image description

Image description

Image description

Image description

Image description

Image description

Image description

Image description

Image description

9. Set Up the Load Balancer
Once the load balancer is created, copy its DNS name.
Open a browser and paste the DNS name to confirm that your application (e.g., a sample 2048 game) has been successfully deployed.

Image description

Image description

Image description

Image description

Image description

Top comments (0)

