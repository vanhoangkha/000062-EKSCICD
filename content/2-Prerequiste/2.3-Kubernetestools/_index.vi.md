---
title : "Cài đặt Kubernetes Tool"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 2.3 </b> "
---

#### Cài đặt Kubernetes Tool

1. Copy và Paste đoạn lệnh dưới đây vào **Terminal của Cloud9 Workspace** để cài đặt **kubectl**.

```
sudo curl --silent --location -o /usr/local/bin/kubectl \
   https://amazon-eks.s3.us-west-2.amazonaws.com/1.17.11/2020-09-18/bin/linux/amd64/kubectl

sudo chmod +x /usr/local/bin/kubectl
```

![Install Kubernetes Tool](/images/2-Prerequiste/2.3-Kubernetestools/0001-kubernetestools.png)


2. Copy và Paste đoạn lệnh dưới đây vào **Terminal của Cloud9 Workspace** để cập nhật **awscli**.

```
sudo pip install --upgrade awscli && hash -r
```

![Install Kubernetes Tool](/images/2-Prerequiste/2.3-Kubernetestools/0002-kubernetestools.png)


3. Copy và Paste đoạn lệnh dưới đây vào **Terminal của Cloud9 Workspace** để cài đặt các công cụ hỗ trợ xử lý text trên dòng lệnh.

```
sudo yum -y install jq gettext bash-completion moreutils

```

![Install Kubernetes Tool](/images/2-Prerequiste/2.3-Kubernetestools/0003-kubernetestools.png)


4. Ta xem **jq** giống như sed cho dữ liệu JSON - bạn có thể sử dụng nó để cắt và lọc cũng như ánh xạ và chuyển đổi dữ liệu có cấu trúc với cùng một cách dễ dàng giống như sed, awk, grep.

```
echo 'yq() {
  docker run --rm -i -v "${PWD}":/workdir mikefarah/yq "$@"
}' | tee -a ~/.bashrc && source ~/.bashrc

```

![Install Kubernetes Tool](/images/2-Prerequiste/2.3-Kubernetestools/0004-kubernetestools.png)

5. Kiểm tra các công cụ đã được cài đặt bằng cách chạy lệnh dưới đây.

```
for command in kubectl jq envsubst aws
  do
    which $command &>/dev/null && echo "$command in path" || echo "$command NOT FOUND"
  done

```

![Install Kubernetes Tool](/images/2-Prerequiste/2.3-Kubernetestools/0005-kubernetestools.png)

6. Bật tính năng tự động hoàn tất cho công cụ kubectl bằng cách chạy lệnh dưới đây:

```
kubectl completion bash >>  ~/.bash_completion
. /etc/profile.d/bash_completion.sh
. ~/.bash_completion
```

![Install Kubernetes Tool](/images/2-Prerequiste/2.3-Kubernetestools/0006-kubernetestools.png)

7. Thiết lập phiên bản 2.2.0 khi sử dụng AWS Load Balancer Controller

```
echo 'export LBC_VERSION="v2.2.0"' >>  ~/.bash_profile
.  ~/.bash_profile

```

![Install Kubernetes Tool](/images/2-Prerequiste/2.3-Kubernetestools/0007-kubernetestools.png)
