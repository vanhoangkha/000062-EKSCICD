---
title : "Tạo Cloud9 Workspace"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2.2 </b> "
---

{{% notice info %}}
Quá trình khởi tạo môi trường trên Cloud9 mất khoảng thời gian 5 phút
{{% /notice %}}

#### Tạo Cloud9 Workspace

1. Truy cập vào [AWS Console](https://aws.amazon.com/console/)

- Tìm **Cloud9**
- Chọn **Cloud9**

![Create workspace](/images/2-Prerequiste/2.2-CreateWorkspace/0001-createworkspace.png)

2.  Trong giao diện **Cloud9**

- Chọn **Create environment**

![Create workspace](/images/2-Prerequiste/2.2-CreateWorkspace/0002-createworkspace.png)

3. Trong bước **Name environment**

- Nhập **Name**: ```eksworkshop```
- Chọn **Next step**
![Create workspace](/images/2-Prerequiste/2.2-CreateWorkspace/0003-createworkspace.png)

4. Trong bước **Configure settings**

- Chọn **Create a new EC2 instance for environment (direct access)**
- Chọn **Instance type**, chọn **t3.small (2 GiB RAM + 1 vCPU)**
- Chọn **Platform**, chọn **Amazon Linux 2 (recommended)**

![Create workspace](/images/2-Prerequiste/2.2-CreateWorkspace/0004-createworkspace.png)

5.  Chọn **Next step**

![Create workspace](/images/2-Prerequiste/2.2-CreateWorkspace/0005-createworkspace.png)

6. Kiểm tra lại và chọn **Create environment**

![Create workspace](/images/2-Prerequiste/2.2-CreateWorkspace/0006-createworkspace.png)

7. Giao diện sau khi tạo môi trường 

![Create workspace](/images/2-Prerequiste/2.2-CreateWorkspace/0007-createworkspace.png)

8. Trong giao diện môi trường vừa khởi tạo

- Chọn **Window**
- Chọn **New Terminal**

![Create workspace](/images/2-Prerequiste/2.2-CreateWorkspace/0008-createworkspace.png)

9. Chạy đoạn script sau đây để tăng dung lượng Cloud9 Workspace lên 30 GB.
- Copy đoạn lệnh sau và paste vào giao diện terminal trên workspace của bạn.
- Sau khi thực thi các lệnh xong, Cloud 9 Workspace sẽ restart lại.

```
pip3 install --user --upgrade boto3
export instance_id=$(curl -s http://169.254.169.254/latest/meta-data/instance-id)
python -c "import boto3
import os
from botocore.exceptions import ClientError 
ec2 = boto3.client('ec2')
volume_info = ec2.describe_volumes(
    Filters=[
        {
            'Name': 'attachment.instance-id',
            'Values': [
                os.getenv('instance_id')
            ]
        }
    ]
)
volume_id = volume_info['Volumes'][0]['VolumeId']
try:
    resize = ec2.modify_volume(    
            VolumeId=volume_id,    
            Size=30
    )
    print(resize)
except ClientError as e:
    if e.response['Error']['Code'] == 'InvalidParameterValue':
        print('ERROR MESSAGE: {}'.format(e))"
if [ $? -eq 0 ]; then
    sudo reboot
fi
```
- Giao diện khi chạy lệnh

![Create workspace](/images/2-Prerequiste/2.2-CreateWorkspace/0009-createworkspace.png)

{{% notice note %}}
Môi trường sẽ được restart khi chạy lệnh trên
{{% /notice %}}

10.  Hoàn thành khởi tạo **Cloud9 Workspace**

![Create workspace](/images/2-Prerequiste/2.2-CreateWorkspace/00010-createworkspace.png)