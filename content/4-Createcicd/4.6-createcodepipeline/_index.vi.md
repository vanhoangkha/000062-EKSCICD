---
title : "Tạo một pipeline"
date :  "`r Sys.Date()`" 
weight : 6
chapter : false
pre : " <b> 4.6 </b> "
---

#### Tạo một CI/CD pipeline với CodePipeline

1. Chúng ta sẽ tạo CodePipeline sử dụng công cụ AWS CloudFormation.

- Chọn Download [CloudFormation template file](https://raw.githubusercontent.com/First-Cloud-Journey/000062-EKSCICD/main/code_pipeline_fcj.yml)


![Create Code Pipeline](/images/9-Createcodepipeline/0001-Createcodepipeline.png)


2. Trong giao diện [AWS Console](https://aws.amazon.com/console/)

- Tìm **CloudFormation**
- Chọn **CloudFormation**

![Create Code Pipeline](/images/9-Createcodepipeline/00013-Createcodepipeline.png)

3. Trong giao diện **CloudFormation**

- Chọn **Stacks**
- Chọn **Create stack**
- Chọn **With new resources (standard)**

![Create Code Pipeline](/images/9-Createcodepipeline/0002-Createcodepipeline.png)

4. Trong giao diện **Create stack**

- Chọn **Template is ready**
- Chọn **Upload a template file**
- Chọn **Choose file**
- Chọn **CloudFormation template file** đã tải về. Ví dụ ```code_pipeline_fcj.yml```
- Chọn **Next** 

![Create Code Pipeline](/images/9-Createcodepipeline/0003-Createcodepipeline.png)

5. Phần **Stack name**, nhập ```Eks-stack``` 

![Create Code Pipeline](/images/9-Createcodepipeline/0004-Createcodepipeline.png)

6. Tiếp theo, điền thông tin các mục sau:

- **User name**, nhập tên **Github Account**
- Nhập **Access token** đã tạo
- Nhập tên **Repository**
- Nhập **Branch**
- Nhập tên **EksCluster**
- Nhập **EksDeployment**
- Nhập **EksNamespace**
- Chọn **Next**


![Create Code Pipeline](/images/9-Createcodepipeline/0005-Createcodepipeline.png)

7. Kéo xuống cuối trang và chọn **Next** 


![Create Code Pipeline](/images/9-Createcodepipeline/0006-Createcodepipeline.png)

8. Kéo xuống cuối trang và chọn **Create stack**

![Create Code Pipeline](/images/9-Createcodepipeline/0007-Createcodepipeline.png)

9. Hoàn thành tạo stack

![Create Code Pipeline](/images/9-Createcodepipeline/0008-Createcodepipeline.png)


10. Trong giao diện [AWS Console](https://aws.amazon.com/console/)

- Tìm **CodePipeline**
- Chọn **CodePipeline**

![Create Code Pipeline](/images/9-Createcodepipeline/00012-Createcodepipeline.png)


10. Xem quá trình CI/CD và chọn **details** để xem chi tiết quá trình build

![Create Code Pipeline](/images/9-Createcodepipeline/0009-Createcodepipeline.png)

11. Quá trình CI/CD hoàn thành
 
![Create Code Pipeline](/images/9-Createcodepipeline/00010-Createcodepipeline.png)

12. Xem lại chi tiết quá trình build bằng cách chọn **details**

![Create Code Pipeline](/images/9-Createcodepipeline/00011-Createcodepipeline.png)