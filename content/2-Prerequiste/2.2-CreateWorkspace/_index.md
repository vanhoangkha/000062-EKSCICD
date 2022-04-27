---
title : "Create Cloud9 Workspace"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

{{% notice info %}}
Cloud9 environment initialization takes about 5 minutes
{{% /notice %}}

#### Create Cloud9 Workspace

1. Go to [AWS Console](https://aws.amazon.com/console/)

- Find **Cloud9**
- Select **Cloud9**

![Create workspace](/images/2-Prerequiste/2.2-CreateWorkspace/0001-createworkspace.png)

2. In the **Cloud9** interface

- Select **Create environment**

![Create workspace](/images/2-Prerequiste/2.2-CreateWorkspace/0002-createworkspace.png)

3. In **Name environment** step

- Enter **Name**: ```eksworkshop```
- Select **Next step**
![Create workspace](/images/2-Prerequiste/2.2-CreateWorkspace/0003-createworkspace.png)

4. In **Configure settings** step

- Select **Create a new EC2 instance for environment (direct access)**
- Select **Instance type**, select **t3.small (2 GiB RAM + 1 vCPU)**
- Select **Platform**, select **Amazon Linux 2 (recommended)**

![Create workspace](/images/2-Prerequiste/2.2-CreateWorkspace/0004-createworkspace.png)

5. Select **Next step**

![Create workspace](/images/2-Prerequiste/2.2-CreateWorkspace/0005-createworkspace.png)

6. Check again and select **Create environment**

![Create workspace](/images/2-Prerequiste/2.2-CreateWorkspace/0006-createworkspace.png)

7. Interface after creating the environment

![Create workspace](/images/2-Prerequiste/2.2-CreateWorkspace/0007-createworkspace.png)

8. In the environment interface just initialized

- Select **Window**
- Select **New Terminal**

![Create workspace](/images/2-Prerequiste/2.2-CreateWorkspace/0008-createworkspace.png)

9. Run the following script to increase Cloud9 Workspace capacity to 30 GB.
- Copy the following command and paste it into the terminal interface on your workspace.
- After executing the commands, Cloud 9 Workspace will restart.

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
- Interface when running commands

![Create workspace](/images/2-Prerequiste/2.2-CreateWorkspace/0009-createworkspace.png)

{{% notice note %}}
The environment will be restarted when running the above command
{{% /notice %}}

10. Complete initialization **Cloud9 Workspace**

![Create workspace](/images/2-Prerequiste/2.2-CreateWorkspace/00010-createworkspace.png)