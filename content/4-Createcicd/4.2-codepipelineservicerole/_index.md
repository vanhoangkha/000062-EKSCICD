---
title : "Create service role for CodePipeline service"
date: 2024-01-01
weight : 2
chapter : false
pre : " <b> 4.2 </b> "
---

#### Create service role for CodePipeline service

1. **CodePileline** requires IAM roles to **build docker**, **push image** and interact with **EKS cluster** using **kubectl** command.

2. Download the json policy files, create **role eks-CodePipelineServiceRole** and add inline policy from terminal
as follows:

```
wget https://raw.githubusercontent.com/First-Cloud-Journey/000062-EKSCICD/main/codepipeline/cpAssumeRolePolicyDocument.json
aws iam create-role --role-name eks-CodePipelineServiceRole --assume-role-policy-document file://cpAssumeRolePolicyDocument.json
wget https://raw.githubusercontent.com/First-Cloud-Journey/000062-EKSCICD/main/codepipeline/cpPolicyDocument.json
aws iam put-role-policy --role-name eks-CodePipelineServiceRole --policy-name codepipeline-access --policy-document file://cpPolicyDocument.json
```
![Create service role for CodePipelin service](/images/7-Createcicd/7.2-codepipelineservicerole/0001-createcodepipelineservicerole.png)