AWS EKS CLUSTER

set up and deploy a scalable Kubernetes cluster on AWS using EKS, allowing for the efficient deployment of containerized applications.

**1. Create a VPC Along with Subnet, Route Table, and Internet Gateway**
Begin by creating a custom Virtual Private Cloud (VPC).
Set up subnets, route tables, and internet gateways for network traffic management within the VPC.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/doe9lmfbsxvn4sostlhl.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/8uziumwfa82aduuga97o.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/6w8iqmwulhevrtajt7hu.png)


**2. Create IAM Roles**
Create two IAM roles:
One for the EKS cluster.
Another for EC2 nodes (worker nodes).

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/s0nifna48dac4x4i6bj6.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/c1i8kuyqmrpyj4sutvox.png)

**3. Create the EKS Cluster**
Navigate to the EKS dashboard and create a cluster.
Assign the name and role to the cluster, and AWS will provision it automatically.
Under network settings, select private subnets and keep other settings at default.
Once created, the EKS cluster will be running, and you can observe the creation of the two pods.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/3vxvzmn9uuz2uwb2uz6t.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ul0ziznzdgo1luhk8j1l.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/mozryep974ug0c0m7dfy.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/57q7kidtbhlcl8b5s3su.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ub7m24swnisg5if4fpf1.png)


**4. Create a Node Group**
Create a node group for the cluster.
Select the instance type (e.g., t2.micro) and configure the scaling parameters (e.g., desired size: 1, minimum size: 1, maximum size: 1).
After successful creation, three worker pods will be available.


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/6w7jg4lljvshbntr5hqw.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1mrw8nmag956rvhhybpl.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/st43sk60e4f2g7yx1yhq.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/699mczh8q0bzqd2ily3p.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/w3sagtfppgq1072nhtva.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/oje2jzg5srxm1nq3n3zl.png)



**5. Install AWS CLI and Minikube**
Download AWS CLI and Minikube.
Check their versions and configure AWS CLI using your access keys.
Update the EKS cluster and deploy the necessary configurations using deployment.yaml.
Verify that pods are running and the deployment is created (e.g., deployment-2048).


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/gvgqb5wopyyn726vspmr.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/off1s27w2g30a2pleevz.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hdiqwzu31la0eis8ne6d.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/70jniu29hl012rsggwg3.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/9mr6ygqqriai5ulga7g4.png)




**6. Manage Tags**
Edit public subnets and add tags.
Assign an Elastic Load Balancer (ELB) role by adding relevant tags.
Copy the cluster URL for future use.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/irblcdwgi9tfkrs9m4jv.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/moyk1scaf9whnrkjgeaa.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/w0jtvlisbwwnx0cx5rkg.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/frgb5o6psu0zisz219gu.png)


**7. Configure IAM Identity Provider**
Go to the IAM Identity Provider section in the AWS Management Console.
Paste the cluster URL and set the audience to sts.amazon.com.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/x91yxopofa88iakt7ene.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/20jwh6ntsj286nsep95k.png)



**8. Create Policies Through JSON**
Create a policy via a JSON file for the Load Balancer Controller.
Name the policy and modify the custom trust policy by adding the necessary account and role details.
Attach the generated ARN URL to the service YAML file and apply the ingress.yaml to complete the setup.


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/v02we5osdjg41od3u0z8.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/7flgquzbitfmtdnab6r6.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/a2hglqap3xpzqywf0m5c.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/0fxyv5o70p91z60fnmk6.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/en569s0f2j916rh8yu16.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/4qhmyzcz8vfcwch9sh8g.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/gbvpv7t13uk6te1p804h.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hza6edys5m9s05kocr0h.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hs5bf3obnlyr80a51k0g.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/tyunygip2a7ma67iqxrl.png)



**9. Set Up the Load Balancer**
Once the load balancer is created, copy its DNS name.
Open a browser and paste the DNS name to confirm that your application (e.g., a sample 2048 game) has been successfully deployed.


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/z1me02p2zdgrdqvt1iw3.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/aau55t5kd9224m4jbptd.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/dp9cigqktcvvjni523q3.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/86csfct695kppad5k2qr.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/50u2p1wli9ss24iohy0f.png)








