---
title : "Tạo service role cho dịch vụ CodePipeline"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 4.2 </b> "
---

#### Tạo service role cho dịch vụ CodePipeline

1. **CodePileline** cần phải có IAM roles để **build docker**, **push image** và tương tác với **EKS cluster** bằng command **kubectl**. 

2. Hãy tải các file policy json, tạo các **role eks-CodePipelineServiceRole** và thêm inline policy từ terminal
như sau:

```
wget https://raw.githubusercontent.com/First-Cloud-Journey/000062-EKSCICD/main/codepipeline/cpAssumeRolePolicyDocument.json
aws iam create-role --role-name eks-CodePipelineServiceRole --assume-role-policy-document file://cpAssumeRolePolicyDocument.json
wget https://raw.githubusercontent.com/First-Cloud-Journey/000062-EKSCICD/main/codepipeline/cpPolicyDocument.json
aws iam put-role-policy --role-name eks-CodePipelineServiceRole --policy-name codepipeline-access --policy-document file://cpPolicyDocument.json
```
![Tạo service role cho dịch vụ CodePipelin](/images/7-Createcicd/7.2-codepipelineservicerole/0001-createcodepipelineservicerole.png)
