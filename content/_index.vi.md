---
title : "CI/CD trên EKS"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---

# CI/CD trên EKS với CodePipeline và GitHub

- Amazon Elastic Kubernetes Service (Amazon EKS) là một dịch vụ container orchestration được quản lý bởi AWS giúp chúng ta để tạo, quản lý, khởi chạy và thay đổi quy mô các ứng dụng Kubernetes trong môi trường AWS hoặc cả môi trường on-premise.

- AWS CodePipeline là dịch vụ phân phối liên tục giúp bạn tự động hóa các deployment pipeline giúp cho việc cập nhật phiên bản mới của ứng dụng hoặc hạ tầng một cách ổn định. CodePipeline tự động hóa việc xây dựng, thử nghiệm và triển khai các giai đoạn của quá trình deploy của bạn mỗi khi có sự thay đổi mã, dựa trên mô hình deploy mà bạn xác định. Bạn có thể tích hợp AWS CodePipeline với các dịch vụ của bên thứ ba như **GitHub** hoặc với plugin tùy chỉnh của riêng bạn. Với AWS CodePipeline, bạn chỉ phải trả tiền cho những gì bạn sử dụng. Bạn không phải trả tiền trước hay thực hiện cam kết dài hạn.

- Trong bài thực hành này, chúng ta sẽ tạo một EKS Cluster và tiến hành triển khai một pipeline để tự động deploy lên môi trường production mỗi khi có thay đổi về code bằng dịch vụ AWS CodePipeline.
