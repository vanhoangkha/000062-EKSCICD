---
title : "Tạo CI/CD"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

### Tổng quan

- Trong các bước tiếp theo, chúng ta sẽ tạo một Deployment Pipeline bằng AWS CodePipeline và tích hợp với công cụ third party là GitHub. Khi chúng ta thay đổi code trên GitHub, Pipeline của chúng ta sẽ được kích hoạt và deploy phiên bản ứng dụng mới lên ứng dụng web chúng ta đã chạy trên EKS Cluster.

![CI/CD on EKS with CodePipeline and GitHub](/images/architecture.png)


### Nội dung

1. [Tạo S3 bucket](4.1-creates3bucket/)
2. [Tạo CodePipeline Service Role](4.2-codepipelineservicerole/)
3. [Tạo Code Buid Service Role](4.3-codebuildservicerole/)
4. [Cho phép role eks-CodeBuildServiceRole quyền trong RBAC của EKS cluster](4.4-rbac/)
5. [Forke source code](4.5-forksourcecode/)
6. [Tạo CodePipeline](4.6-createcodepipeline/)
7. [Kiểm tra CI/CD](4.7-checkcicd/)