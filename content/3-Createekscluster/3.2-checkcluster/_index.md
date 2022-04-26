---
title : "Test EKS Cluster"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---

#### Check EKS Cluster

1. In the [AWS Console] interface(https://aws.amazon.com/console/)

- Find **CloudFormation**
- Select **CloudFormation**

![Create EKS Cluster](/images/5-Checkekscluster/0005-createekscluster.png)

2. In the **CloudFormation** interface
- Select **Stack**
- View created stacks


![Create EKS Cluster](/images/5-Checkekscluster/0006-createekscluster.png)

3. Run the command to check the nodes created

```
kubectl get nodes
```


![Create EKS Cluster](/images/5-Checkekscluster/0007-createekscluster.png)

4. In the [AWS Console] interface(https://aws.amazon.com/console/)

- Find **EKS**
- Select **EKS**

![Create EKS Cluster](/images/5-Checkekscluster/0008-createekscluster.png)

5. In the **EKS** interface

- Select **Cluster**
- View the created cluster

![Create EKS Cluster](/images/5-Checkekscluster/0009-createekscluster.png)

6. In the [AWS Console] interface(https://aws.amazon.com/console/)

- Find **EC2**
- Select **EC2**

![Create EKS Cluster](/images/5-Checkekscluster/00010-createekscluster.png)

7. In the **EC2** interface

- Select **Instances**
- View created instances

![Create EKS Cluster](/images/5-Checkekscluster/00011-createekscluster.png)