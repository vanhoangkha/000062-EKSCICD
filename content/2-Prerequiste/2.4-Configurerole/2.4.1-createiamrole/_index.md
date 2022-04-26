---
title : "Create IAM role"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.4.1 </b> "
---

#### Create IAM role

1. In **Workspace AWS Cloud9**

- Select **AWS Cloud9**
- Select **Go To Your Dashboard**

![Create Role](/images/2-Prerequiste/2.4-Configurerole/2.4.1-createiamrole/0001-createiamrole.png)

2. In the **AWS Console** interface

- Find **IAM**
- Select **IAM**

![Create Role](/images/2-Prerequiste/2.4-Configurerole/2.4.1-createiamrole/0002-createiamrole.png)

3. In the **IAM** interface

- Select **Role**
- Select **Create role**

![Create Role](/images/2-Prerequiste/2.4-Configurerole/2.4.1-createiamrole/0003-createiamrole.png)

4. In **Select trusted entity** step

- Select **AWS service**
- Select **EC2**
- Select **Next**

![Create Role](/images/2-Prerequiste/2.4-Configurerole/2.4.1-createiamrole/0004-createiamrole.png)

5. In **Add permission** step
- Find **AdministratorAccess**
- Select **AdministratorAccess**
- Select **Next**


![Create Role](/images/2-Prerequiste/2.4-Configurerole/2.4.1-createiamrole/0005-createiamrole.png)

6. In step **Name, review and create**

- Enter **Role name**:```eksworkshop-admin```

![Create Role](/images/2-Prerequiste/2.4-Configurerole/2.4.1-createiamrole/0006-createiamrole.png)

7. Select **Create role**

![Create Role](/images/2-Prerequiste/2.4-Configurerole/2.4.1-createiamrole/0007-createiamrole.png)

8. Create a successful role

![Create Role](/images/2-Prerequiste/2.4-Configurerole/2.4.1-createiamrole/0008-createiamrole.png)