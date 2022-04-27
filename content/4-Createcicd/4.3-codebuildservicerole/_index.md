---
title : "Create service role for CodeBuild service"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 4.3 </b> "
---

#### Create service role for CodeBuild service

1. CodeBuild requires IAM roles to build docker, push images, and interact with the EKS cluster using the kubectl command.

- Let's create **role eks-CodePipelineServiceRole** and add **inline policy** from **terminal Cloud9**

```
wget https://raw.githubusercontent.com/minhtri2582/server-samples/master/aws-journey/cbAssumeRolePolicyDocument.json
aws iam create-role --role-name eks-CodeBuildServiceRole --assume-role-policy-document file://cbAssumeRolePolicyDocument.json
wget https://raw.githubusercontent.com/minhtri2582/server-samples/master/aws-journey/cbPolicyDocument.json
aws iam put-role-policy --role-name eks-CodeBuildServiceRole --policy-name codebuild-access --policy-document file://cbPolicyDocument.json
```
![Create Code Build Service Role](/images/7-Createcicd/7.3-codebuildservicerole/0001-CodeBuildServiceRole.png)

2. We check the created role, we do:

- Go to the [AWS Console](https://aws.amazon.com/console/)

- Find **IAM**
- Select **IAM**

![Create Code Build Service Role](/images/7-Createcicd/7.3-codebuildservicerole/0004-CodeBuildServiceRole.png)

3. In the **IAM** interface

- Select **Role**
- Find ```eks-Code```
- View the 2 Roles just created

![Create Code Build Service Role](/images/7-Createcicd/7.3-codebuildservicerole/0005-CodeBuildServiceRole.png)