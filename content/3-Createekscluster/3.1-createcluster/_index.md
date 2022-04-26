---
title : "Create EKS Cluster"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---

#### Create EKS Cluster

1. To create an EKS cluster, we will first have to generate an SSH key to be able to access the EC2 Node in the Cluster as needed:

```
aws ec2 create-key-pair --key-name k8s-demo --query 'KeyMaterial' --output text> k8s-demo.pem
```

![Create EKS Cluster](/images/4-Createekscluster/0001-createekscluster.png)

2. In the **AWS Console** interface

- Find **EC2**
- Select **EC2**

![Create EKS Cluster](/images/4-Createekscluster/0002-createekscluster.png)

3. In the **EC2** interface

- Select **Key Pair**
- See **Key Pair** just created

![Create EKS Cluster](/images/4-Createekscluster/0003-createekscluster.png)

4. To create EKS Cluster and EC2 Nodes we use the following command:

```
eksctl create cluster --name k8s-demo --region ap-southeast-1 --nodegroup-name k8s-demo --nodes 2 --ssh-access --ssh-public-key k8s-demo --managed
```

- When you run this command, eksctl will use AWS CloudFormation to create the necessary infrastructure and setup the Master Node (Control Plane).

![Create EKS Cluster](/images/4-Createekscluster/0004-createekscluster.png)

5. Interface after creating EKS Cluster

![Create EKS Cluster](/images/4-Createekscluster/0005-createekscluster.png)