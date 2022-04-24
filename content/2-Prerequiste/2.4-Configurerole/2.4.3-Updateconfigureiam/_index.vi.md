---
title : "Cập nhật cấu hình Cloud9"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 2.4.3 </b> "
---

#### Cập nhật cấu hình Cloud9

{{%notice tip%}}
Cloud9 sẽ quản lý thông tin chứng thực IAM một cách tự động. Cấu hình mặc định này hiện tại không tương thích với chứng thực EKS thông qua IAM, chúng ta sẽ cần phải vô hiệu hóa tính năng này và sử dụng IAM Role.
{{%/notice%}}




1. Trong giao diện **AWS Cloud9**

- Chọn **AWS Cloud9**
- Chọn **Preferences**

![Update configure role](/images/2-Prerequiste/2.4-Configurerole/2.4.3-Updateconfigureiam/0001-updateconfigureiam.png)

2. Trong giao diện **AWS Cloud9**

- Chọn **AWS SETTINGS**
- Bỏ chọn **AWS managed temporary credentials**

![Update configure role](/images/2-Prerequiste/2.4-Configurerole/2.4.3-Updateconfigureiam/0002-updateconfigureiam.png)

3. Để đảm bảo các thông tin chứng thực tạm không được lưu lại trong Cloud9, chúng ta sẽ xóa tất cả những thông tin chứng thực đang tồn tại bằng câu lệnh dưới đây.
  
```
rm -vf ${HOME}/.aws/credentials
```

![Update configure role](/images/2-Prerequiste/2.4-Configurerole/2.4.3-Updateconfigureiam/0003-updateconfigureiam.png)


4. Tiếp theo chúng ta sẽ cấu hình aws cli sử dụng Region hiện tại.

```
export ACCOUNT_ID=$(aws sts get-caller-identity --output text --query Account)
export AWS_REGION=$(curl -s 169.254.169.254/latest/dynamic/instance-identity/document | jq -r '.region')
export AZS=($(aws ec2 describe-availability-zones --query 'AvailabilityZones[].ZoneName' --output text --region $AWS_REGION))

```

![Update configure role](/images/2-Prerequiste/2.4-Configurerole/2.4.3-Updateconfigureiam/0004-updateconfigureiam.png)

5. Kiểm tra xem AWS_REGION đã được thiết lập đúng Region hiện tại chưa.

```
test -n "$AWS_REGION" && echo AWS_REGION is "$AWS_REGION" || echo AWS_REGION is not set

```

![Update configure role](/images/2-Prerequiste/2.4-Configurerole/2.4.3-Updateconfigureiam/0005-updateconfigureiam.png)

6. Tiếp theo chúng ta sẽ lưu các thông tin cấu hình vào bash_profile

```
echo "export ACCOUNT_ID=${ACCOUNT_ID}" | tee -a ~/.bash_profile
echo "export AWS_REGION=${AWS_REGION}" | tee -a ~/.bash_profile
echo "export AZS=(${AZS[@]})" | tee -a ~/.bash_profile
aws configure set default.region ${AWS_REGION}
aws configure get default.region

```

![Update configure role](/images/2-Prerequiste/2.4-Configurerole/2.4.3-Updateconfigureiam/0006-updateconfigureiam.png)

7. Kiểm tra IAM Role
- Chúng ta sẽ sử dụng câu lệnh để kiểm tra Cloud9 IDE đang sử dụng IAM Role có chính xác không.

```
aws sts get-caller-identity --query Arn | grep eksworkshop-admin -q && echo "IAM role valid" || echo "IAM role NOT valid"

```

![Update configure role](/images/2-Prerequiste/2.4-Configurerole/2.4.3-Updateconfigureiam/0007-updateconfigureiam.png)