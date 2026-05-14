---
title : "Kiểm tra CI/CD"
date: 2024-01-01
weight : 7
chapter : false
pre : " <b> 4.7 </b> "
---

#### Kiểm tra CI/CD pipeline

1. Vào **GitHub** của bạn https://github.com/{GITHUB_ACCOUNT}/000062-websource

 
- Chọn repository đã fork 
- Mở file **index.html**, chọn icon chỉnh sửa
- Chỉnh sửa code trong file **index.html**. Trong bài này chỉnh code phần title **(dòng 48)**chuyển từ **John Doe** thành **AWS First Cloud Journey** 
- Sau đó, chọn **Commit changes**

![Check CICD](/images/10-Checkcicd/0002-checkcicd.png)

2. Sau khi push code, **CodePipeline** sẽ được trigger để thực thi **CodeBuild**. 

- Vào trang quản trị **CodePipeline** sẽ thấy trạng thái của pipeline là **In Progress**
- Pipele của có 2 stage:
  - **Source**
  - Pull source từ GitHub 
  - Đóng gói source cho stage build
  - **Build**
  - Tạo **Docker image** từ **source** 
  - Đẩy image lên **ECR repository**
  - Triển khai cập nhật ứng dụng lên **EKS cluster**

![Check CICD](/images/10-Checkcicd/0003-checkcicd.png)


3. Triển khai cập nhật ứng dụng lên EKS cluster Chờ khoảng 5-10 phút để quá trình build hoàn thành và chuyển sang trạng thái **Succeeded**. 

![Check CICD](/images/10-Checkcicd/0004-checkcicd.png)

4. Vào website URL xem thay đổi. 

- Lúc này title của website đã chuyển thành **AWS First Cloud Journey**

![Check CICD](/images/10-Checkcicd/0005-checkcicd.png)

Chúc mừng bạn đã hoàn thành bài lab. 