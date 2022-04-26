---
title : "Create IAM User"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---

#### Create IAM User

1. Go to the [AWS Console page](https://aws.amazon.com/console/)

- Find **IAM**
- Select **IAM**

![Create IAM User](/images/2-Prerequiste/2.1-IAMUser/0001-createiamuser.png)

2. In the **IAM** interface

- Select **User**
- Select **Add users**

![Create IAM User](/images/2-Prerequiste/2.1-IAMUser/0002-createiamuser.png)

3. In **Add user** step

- Enter **User name**, enter ```aws-eks```
- Select **Access key - Programmatic access**
- Select **Password - AWS Management Console access**
- Select **Custom password**
- Select **Show password**
- Uncheck **User must create a new password at next sign-in**
- Select **Next:Permissions**

![Create IAM User](/images/2-Prerequiste/2.1-IAMUser/0003-createiamuser.png)

4. In the next step of **Add user**

- Select **Attach existing policies directly**
- Select **AdministratorAccess**
- Select **Next:Tags**

![Create IAM User](/images/2-Prerequiste/2.1-IAMUser/0004-createiamuser.png)

5. In **Add tags** step
- Enter **Key**: ```Name```
- Enter **Value**: ```Admin user```


![Create IAM User](/images/2-Prerequiste/2.1-IAMUser/0005-createiamuser.png)

6. Check again and select **Create user**

![Create IAM User](/images/2-Prerequiste/2.1-IAMUser/0006-createiamuser.png)

7. After **Add user** is successful

- View created user information
- Select **Download.csv** to download information about **Access key ID** and **Secure access key**
- Then select **Close**

![Create IAM User](/images/2-Prerequiste/2.1-IAMUser/0007-createiamuser.png)


8. View successful user creation information

![Create IAM User](/images/2-Prerequiste/2.1-IAMUser/0008-createiamuser.png)