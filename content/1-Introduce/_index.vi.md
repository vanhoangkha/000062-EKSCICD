---
title : "Giới thiệu"
date: 2024-01-01
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

### Tổng quan

- **Kubernetes (K8s)** là một nền tảng nguồn mở, có thể mở rộng để quản lý các ứng dụng được đóng gói và các service, giúp thuận lợi trong việc cấu hình và tự động hoá việc triển khai ứng dụng

- Trong bài lab này, chúng ta sẽ tạo một **Kubernetes Cluster** đơn giản trên **AWS EKS (Elastic Kubernetes Service)**. Sau đó, mình sẽ triển khai trang web trên cluster và sử dụng **AWS CodePipeLine** để triển khai tự động.

![Elastic Kubernetes Service](/images/1-Introduce/CI_CDwithAWSCodePipeline.png)

### Nội dung

1. [Giới thiệu]()
2. [Các bước chuẩn bị](../2-prerequiste/)
3. [Tạo EKS cluster](../3-createekscluster/)
4. [Tạo Code Pipeline](../4-createcicd/)
5. [Dọn dẹp tài nguyên](../5-cleanup/)
