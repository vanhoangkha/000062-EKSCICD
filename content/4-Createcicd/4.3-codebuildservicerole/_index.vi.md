---
title : "Tạo service role cho dịch vụ CodeBuild"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 4.3 </b> "
---

#### Tạo service role cho dịch vụ CodeBuild

1. CodeBuild cần phải có IAM roles để build docker, push image và tương tác với EKS cluster bằng command kubectl. 

- Hãy tải các **file policy json**, tạo các **role eks-CodePipelineServiceRole** và thêm **inline policy** từ **terminal Cloud9** như sau:

```
wget https://raw.githubusercontent.com/minhtri2582/server-samples/master/aws-journey/cbAssumeRolePolicyDocument.json
aws iam create-role --role-name eks-CodeBuildServiceRole --assume-role-policy-document file://cbAssumeRolePolicyDocument.json
wget https://raw.githubusercontent.com/minhtri2582/server-samples/master/aws-journey/cbPolicyDocument.json
aws iam put-role-policy --role-name eks-CodeBuildServiceRole --policy-name codebuild-access --policy-document file://cbPolicyDocument.json
```

![Create Code Build Service Role](/images/7-Createcicd/7.3-codebuildservicerole/0001-CodeBuildServiceRole.png)

2. Chúng ta kiểm tra role đã tạo, ta thực hiện:

- Truy cập vào trang [AWS Console](https://aws.amazon.com/console/)

- Tìm **IAM**
- Chọn **IAM**

![Create Code Build Service Role](/images/7-Createcicd/7.3-codebuildservicerole/0002-CodeBuildServiceRole.png)

3. Trong giao diện **IAM**

- Chọn **Role**
- Tìm ```eks-Code```
- Xem 2 Role vừa tạo

![Create Code Build Service Role](/images/7-Createcicd/7.3-codebuildservicerole/0003-CodeBuildServiceRole.png)