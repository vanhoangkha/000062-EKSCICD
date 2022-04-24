---
title : "Tạo EKS Cluster"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 3.1 </b> "
---

#### Tạo EKS Cluster

1. Để tạo EKS cluster, trước tiên chúng ta sẽ phải tạo SSH key để có thể access vào EC2 Node trong Cluster khi cần thiết:

```
aws ec2 create-key-pair --key-name k8s-demo --query 'KeyMaterial' --output text> k8s-demo.pem
```

![Create EKS Cluster](/images/4-Createekscluster/0001-createekscluster.png)

2. Trong giao diện **AWS Console**

- Tìm **EC2**
- Chọn **EC2**

![Create EKS Cluster](/images/4-Createekscluster/0002-createekscluster.png)

3.  Trong giao diện **EC2**

- Chọn **Key Pair**
- Xem **Key Pair** vừa tạo

![Create EKS Cluster](/images/4-Createekscluster/0003-createekscluster.png)

4. Để tạo EKS Cluster và các EC2 Node chúng ta sử dụng command sau:

```
eksctl create cluster --name k8s-demo --region ap-southeast-1 --nodegroup-name k8s-demo --nodes 2 --ssh-access --ssh-public-key k8s-demo --managed
```

- Khi bạn chạy command này, thì eksctl sẽ sử dụng AWS CloudFormation để tạo các infrastructure cần thiết và setup Master Node (Control Plane).

![Create EKS Cluster](/images/4-Createekscluster/0004-createekscluster.png)

5. Giao diện sau khi tạo EKS Cluster

![Create EKS Cluster](/images/4-Createekscluster/0005-createekscluster.png)