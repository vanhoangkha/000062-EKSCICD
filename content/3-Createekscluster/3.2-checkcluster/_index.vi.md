---
title : "Kiểm tra EKS Cluster"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---

#### Kiểm tra EKS Cluster

1. Trong giao diện [AWS Console](https://aws.amazon.com/console/) 

- Tìm **CloudFormation**
- Chọn **CloudFormation**

![Create EKS Cluster](/images/5-Checkekscluster/0005-createekscluster.png)

2. Trong giao diện **CloudFormation**
- Chọn **Stack**
- Xem các stack đã tạo


![Create EKS Cluster](/images/5-Checkekscluster/0006-createekscluster.png)

3. Chạy câu lệnh để kiểm tra các nodes được tạo

```
kubectl get nodes
```


![Create EKS Cluster](/images/5-Checkekscluster/0007-createekscluster.png)

4. Trong giao diện [AWS Console](https://aws.amazon.com/console/)

- Tìm **EKS**
- Chọn **EKS**

![Create EKS Cluster](/images/5-Checkekscluster/0008-createekscluster.png)

5. Trong giao diện **EKS**

- Chọn **Cluster**
- Xem cluster đã tạo

![Create EKS Cluster](/images/5-Checkekscluster/0009-createekscluster.png)

6.  Trong giao diện [AWS Console](https://aws.amazon.com/console/)

- Tìm **EC2**
- Chọn **EC2**

![Create EKS Cluster](/images/5-Checkekscluster/00010-createekscluster.png)

7. Trong giao diện **EC2**

- Chọn **Instances**
- Xem các instance đã tạo

![Create EKS Cluster](/images/5-Checkekscluster/00011-createekscluster.png)