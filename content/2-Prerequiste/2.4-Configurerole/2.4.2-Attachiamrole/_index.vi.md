---
title : "Gán IAM role"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2.4.2 </b> "
---
#### Gán IAM role vào Cloud9

1. Trong giao diện **AWS Cloud9**

- Chọn biểu tượng **R**
- Chọn **Manage EC2 Instance**

![Attach role](/images/2-Prerequiste/2.4-Configurerole/2.4.2-Attachiamrole/0001-attachiamrole.png)

2. Trong giao diện **EC2**

- Chọn **Instance**
- Chọn aws-cloud9 instance

![Attach role](/images/2-Prerequiste/2.4-Configurerole/2.4.2-Attachiamrole/0002-attachiamrole.png)

3. Trong giao diện **Instance**

- Chọn **Actions**
- Chọn **Security**
- Chọn **Modify IAM role**

![Attach role](/images/2-Prerequiste/2.4-Configurerole/2.4.2-Attachiamrole/0003-attachiamrole.png)

4. Trong giao diện **Modify IAM role**

- Chọn ```eksworkshop-admin```
- Chọn **Save**

![Attach role](/images/2-Prerequiste/2.4-Configurerole/2.4.2-Attachiamrole/0004-attachiamrole.png)

5. Gán role thành công

![Attach role](/images/2-Prerequiste/2.4-Configurerole/2.4.2-Attachiamrole/0005-attachiamrole.png)