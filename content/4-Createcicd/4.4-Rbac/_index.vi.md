---
title : "Cấu hình RBAC"
date: 2024-01-01
weight : 4 
chapter : false
pre : " <b> 4.4 </b> "
---

#### Cấu hình RBAC

1. Để CodeBuild có thể tương tác với EKS, chúng ta sẽ chỉnh sửa **configMap aws-auth**
   
- Từ **terminal Cloud9** mà bạn đã kết nối **EKS cluster**, lấy bản sao **configMap aws-auth** bằng command:

```
kubectl get configmaps aws-auth -n kube-system -o yaml > aws-auth.yaml
```

![RBAC](/images/7-Createcicd/7.4-Rbac/0001-RBAC.png)

2. Mở tập tin **aws-auth.yaml** vừa tạo ở trên, sẽ có nội dung như sau:

```
apiVersion: v1
data:
  mapRoles: |
    - groups:
      - system:bootstrappers
      - system:nodes
      rolearn: arn:aws:iam::451085899692:role/eksctl-k8s-demo-nodegroup-k8s-dem-NodeInstanceRole-LYNRCIX49ZOU
      username: system:node:{{EC2PrivateDNSName}}
kind: ConfigMap
metadata:
  creationTimestamp: "2022-04-26T10:21:52Z"
  managedFields:
  - apiVersion: v1
    fieldsType: FieldsV1
    fieldsV1:
      f:data:
        .: {}
        f:mapRoles: {}
    manager: vpcLambda
    operation: Update
    time: "2022-04-26T10:21:52Z"
  name: aws-auth
  namespace: kube-system
  resourceVersion: "2691"
  uid: a2862e92-4697-4654-bb19-dc28b17dc21b
```


![RBAC](/images/7-Createcicd/7.4-Rbac/0002-RBAC.png)

3. Sửa **file aws-auth.yaml** này, thêm một item trong mảng **data.mapRoles**:

```
- groups:
  - system:masters
  rolearn: arn:aws:iam::{$AWS_ACCOUNT_ID}}:role/eks-CodeBuildServiceRole
  username: codebuild-eks
```

4. Tập tin aws-auth.yaml sau khi thêm role eks-CodeBuildServiceRole có dạng như sau:


{{% notice note %}} 
Xóa dòng metadata.creationTimestamp và metadata.resourceVersion
{{% /notice %}}

```
apiVersion: v1
data:
  mapRoles: |
    - groups:
      - system:bootstrappers
      - system:nodes
      rolearn: arn:aws:iam::451085899692:role/eksctl-k8s-demo-nodegroup-k8s-dem-NodeInstanceRole-LYNRCIX49ZOU
      username: system:node:{{EC2PrivateDNSName}}
    - groups:
      - system:masters
      rolearn: arn:aws:iam::{$AWS_ACCOUNT_ID}}:role/eks-CodeBuildServiceRole
      username: codebuild-eks
kind: ConfigMap
metadata:
  creationTimestamp: "2022-04-26T10:21:52Z"
  managedFields:
  - apiVersion: v1
    fieldsType: FieldsV1
    fieldsV1:
      f:data:
        .: {}
        f:mapRoles: {}
    manager: vpcLambda
    operation: Update
    time: "2022-04-26T10:21:52Z"
  name: aws-auth
  namespace: kube-system
  resourceVersion: "2691"
  uid: a2862e92-4697-4654-bb19-dc28b17dc21b
```

![RBAC](/images/7-Createcicd/7.4-Rbac/0003-RBAC.png)

5. Apply tập tin **aws-auth.yaml** đã thay đổi từ terminal:

```
kubectl apply -f aws-auth.yaml
```

![RBAC](/images/7-Createcicd/7.4-Rbac/0004-RBAC.png)