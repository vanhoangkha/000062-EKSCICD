---
title : "Create S3 bucket"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 4.1 </b> "
---

#### Create S3 bucket

1. Create this **Bucket** for **CodeBuild** to save **artifact** (generate **build.json** file after each build). We use the following command:

```
ACCOUNT_ID=$(aws sts get-caller-identity | jq -r '.Account')
aws s3 mb s3://eks-${ACCOUNT_ID}-codepipeline-artifacts
```

![Create S3 Bucket](/images/7-Createcicd/7.1-creates3bucket/0001-creates3bucket.png)

2. In the [AWS Console] interface(https://aws.amazon.com/console/)

- Find **S3**
- Select **S3**


![Create S3 Bucket](/images/7-Createcicd/7.1-creates3bucket/0002-creates3bucket.png)

3. In the **S3** interface

- Select **S3**
- Select **Bucket**
- View created **bucket artifact**

![Create S3 Bucket](/images/7-Createcicd/7.1-creates3bucket/0003-creates3bucket.png)