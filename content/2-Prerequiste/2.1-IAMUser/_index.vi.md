---
title : "Tạo IAM User"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.1 </b> "
---

#### Tạo IAM User

1. Truy cập vào trang [AWS Console](https://aws.amazon.com/console/)

- Tìm **IAM**
- Chọn **IAM**

![Create IAM User](/images/2-Prerequiste/2.1-IAMUser/0001-createiamuser.png)

2. Trong giao diện **IAM**

- Chọn **User**
- Chọn **Add users**

![Create IAM User](/images/2-Prerequiste/2.1-IAMUser/0002-createiamuser.png)

3. Trong bước **Add user**

- Nhập **User name**, nhập ```aws-eks```
- Chọn **Access key - Programmatic access**
- Chọn **Password - AWS Management Console access**
- Chọn **Custom password**
- Chọn **Show password**
- Bỏ chọn **User must create a new password at next sign-in**
- Chọn **Next:Permissions**

![Create IAM User](/images/2-Prerequiste/2.1-IAMUser/0003-createiamuser.png)

4. Trong bước tiếp theo của **Add user**

- Chọn **Attach existing policies directly**
- Chọn **AdministratorAccess**
- Chọn **Next:Tags**

![Create IAM User](/images/2-Prerequiste/2.1-IAMUser/0004-createiamuser.png)

5. Trong bước **Add tags**
- Nhập **Key**: ```Name```
- Nhập **Value**: ```Admin user```


![Create IAM User](/images/2-Prerequiste/2.1-IAMUser/0005-createiamuser.png)

6. Kiểm tra lại và chọn **Create user** 

![Create IAM User](/images/2-Prerequiste/2.1-IAMUser/0006-createiamuser.png)

7. Sau khi **Add user** thành công

- Xem thông tin user đã tạo
- Chọn **Download.csv** để tải thông tin về **Access key ID** và **Serect access key**
- Sau đó, chọn **Close**

![Create IAM User](/images/2-Prerequiste/2.1-IAMUser/0007-createiamuser.png)


8. Xem thông tin tạo user thành công

![Create IAM User](/images/2-Prerequiste/2.1-IAMUser/0008-createiamuser.png)