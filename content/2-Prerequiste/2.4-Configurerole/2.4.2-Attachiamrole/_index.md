---
title : "Assign IAM role"
date: 2024-01-01
weight : 2
chapter : false
pre : " <b> 2.4.2 </b> "
---
#### Assign IAM role to Cloud9

1. In the **AWS Cloud9** interface

- Select the **R** icon
- Select **Manage EC2 Instance**

![Attach role](/images/2-Prerequiste/2.4-Configurerole/2.4.2-Attachiamrole/0001-attachiamrole.png)

2. In **EC2** interface

- Select **Instance**
- Select aws-cloud9 instance

![Attach role](/images/2-Prerequiste/2.4-Configurerole/2.4.2-Attachiamrole/0002-attachiamrole.png)

3. In the **Instance** interface

- Select **Actions**
- Select **Security**
- Select **Modify IAM role**

![Attach role](/images/2-Prerequiste/2.4-Configurerole/2.4.2-Attachiamrole/0003-attachiamrole.png)

4. In the **Modify IAM role** interface

- Select ```eksworkshop-admin```
- Select **Save**

![Attach role](/images/2-Prerequiste/2.4-Configurerole/2.4.2-Attachiamrole/0004-attachiamrole.png)

5. Successful role assignment

![Attach role](/images/2-Prerequiste/2.4-Configurerole/2.4.2-Attachiamrole/0005-attachiamrole.png)