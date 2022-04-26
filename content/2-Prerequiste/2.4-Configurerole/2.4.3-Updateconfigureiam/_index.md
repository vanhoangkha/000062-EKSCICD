---
title : "Update Cloud9 Configuration"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.4.3 </b> "
---

#### Update Cloud9 configuration

{{%notice tip%}}
Cloud9 will manage IAM credentials automatically. This default configuration is currently not compatible with EKS authentication via IAM, we will need to disable this feature and use the IAM Role.
{{%/notice%}}


1. In the **AWS Cloud9** interface

- Select **AWS Cloud9**
- Select **Preferences**

![Update configure role](/images/2-Prerequiste/2.4-Configurerole/2.4.3-Updateconfigureiam/0001-updateconfigureiam.png)

2. In **AWS Cloud9** interface

- Select **AWS SETTINGS**
- Uncheck **AWS managed temporary credentials**

![Update configure role](/images/2-Prerequiste/2.4-Configurerole/2.4.3-Updateconfigureiam/0002-updateconfigureiam.png)

3. To ensure that temporary credentials are not saved in Cloud9, we will delete all existing credentials with the command below.
  
```
rm -vf ${HOME}/.aws/credentials
```

![Update configure role](/images/2-Prerequiste/2.4-Configurerole/2.4.3-Updateconfigureiam/0003-updateconfigureiam.png)

4. Next we will configure the aws cli to use the current Region.

```
export ACCOUNT_ID=$(aws sts get-caller-identity --output text --query Account)
export AWS_REGION=$(curl -s 169.254.169.254/latest/dynamic/instance-identity/document | jq -r '.region')
export AZS=($(aws ec2 describe-availability-zones --query 'AvailabilityZones[].ZoneName' --output text --region $AWS_REGION))

```

![Update configure role](/images/2-Prerequiste/2.4-Configurerole/2.4.3-Updateconfigureiam/0004-updateconfigureiam.png)

5. Check that AWS_REGION has been set to the correct current Region.

```
test -n "$AWS_REGION" && echo AWS_REGION is "$AWS_REGION" || echo AWS_REGION is not set

```

![Update configure role](/images/2-Prerequiste/2.4-Configurerole/2.4.3-Updateconfigureiam/0005-updateconfigureiam.png)

6. Next we will save the configuration information to bash_profile

```
echo "export ACCOUNT_ID=${ACCOUNT_ID}" | tee -a ~/.bash_profile
echo "export AWS_REGION=${AWS_REGION}" | tee -a ~/.bash_profile
echo "export AZS=(${AZS[@]})" | tee -a ~/.bash_profile
aws configure set default.region ${AWS_REGION}
aws configure get default.region

```

![Update configure role](/images/2-Prerequiste/2.4-Configurerole/2.4.3-Updateconfigureiam/0006-updateconfigureiam.png)

7. Check IAM Role
- We will use the command to check if the Cloud9 IDE is using the IAM Role correctly.

```
aws sts get-caller-identity --query Arn | grep eksworkshop-admin -q && echo "IAM role valid" || echo "IAM role NOT valid"

```

![Update configure role](/images/2-Prerequiste/2.4-Configurerole/2.4.3-Updateconfigureiam/0007-updateconfigureiam.png)