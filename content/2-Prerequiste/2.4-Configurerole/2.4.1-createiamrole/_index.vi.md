---
title : "Tạo IAM role"
date: 2024-01-01
weight : 1
chapter : false
pre : " <b> 2.4.1 </b> "
---

#### Tạo IAM role

1. Trong **Workspace AWS Cloud9**

- Chọn **AWS Cloud9**
- Chọn **Go To Your Dashboard**

![Create Role](/images/2-Prerequiste/2.4-Configurerole/2.4.1-createiamrole/0001-createiamrole.png)

2. Trong giao diện **AWS Console**

- Tìm **IAM**
- Chọn **IAM**

![Create Role](/images/2-Prerequiste/2.4-Configurerole/2.4.1-createiamrole/0002-createiamrole.png)

3. Trong giao diện **IAM**

- Chọn **Role**
- Chọn **Create role**

![Create Role](/images/2-Prerequiste/2.4-Configurerole/2.4.1-createiamrole/0003-createiamrole.png)

4. Trong bước **Select trusted entity**

- Chọn **AWS service**
- Chọn **EC2**
- Chọn **Next**

![Create Role](/images/2-Prerequiste/2.4-Configurerole/2.4.1-createiamrole/0004-createiamrole.png)

5. Trong bước **Add permission**
- Tìm **AdministratorAccess**
- Chọn **AdministratorAccess**
- Chọn **Next**


![Create Role](/images/2-Prerequiste/2.4-Configurerole/2.4.1-createiamrole/0005-createiamrole.png)

6. Trong bước **Name, review and create**

- Nhập **Role name**:```eksworkshop-admin```

![Create Role](/images/2-Prerequiste/2.4-Configurerole/2.4.1-createiamrole/0006-createiamrole.png)

7. Chọn **Create role** 

![Create Role](/images/2-Prerequiste/2.4-Configurerole/2.4.1-createiamrole/0007-createiamrole.png)

8. Tạo role thành công

![Create Role](/images/2-Prerequiste/2.4-Configurerole/2.4.1-createiamrole/0008-createiamrole.png)