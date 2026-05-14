---
title : "Tạo S3 bucket"
date: 2024-01-01
weight : 1 
chapter : false
pre : " <b> 4.1 </b> "
---

#### Tạo S3 bucket

1. Tạo **Bucket** này cho **CodeBuild** lưu **artifact** (tạo ra tập tin **build.json** sau mỗi lần build). Chúng ta sử dụng lệnh sau: 

```
ACCOUNT_ID=$(aws sts get-caller-identity | jq -r '.Account')
aws s3 mb s3://eks-${ACCOUNT_ID}-codepipeline-artifacts
```

![Create S3 Bucket](/images/7-Createcicd/7.1-creates3bucket/0001-creates3bucket.png)

2. Trong giao diện [AWS Console](https://aws.amazon.com/console/) 

- Tìm **S3**
- Chọn **S3**


![Create S3 Bucket](/images/7-Createcicd/7.1-creates3bucket/0002-creates3bucket.png)

3. Trong giao diện **S3**

- Chọn **S3**
- Chọn **Bucket**
- Xem **bucket  artifact** đã tạo

![Create S3 Bucket](/images/7-Createcicd/7.1-creates3bucket/0003-creates3bucket.png)