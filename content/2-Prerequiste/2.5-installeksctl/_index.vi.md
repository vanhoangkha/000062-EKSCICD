---
title : "Cài đặt eksctl"
date: 2024-01-01
weight : 5 
chapter : false
pre : " <b> 2.5 </b> "
---

#### Cài đặt eksctl

1. Trong phần này chúng ta sẽ thực hiện cài đặt công cụ **eksctl** vào **Cloud9 Workspace**.

- Chạy câu lệnh để tải về công cụ **eksctl**.

```
curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp

sudo mv -v /tmp/eksctl /usr/local/bin
```

![Create Eksctl](/images/3-Createeksctl/0001-installeksctl.png)

2. Kiểm tra eksctl hoạt động hay không bằng câu lệnh dưới đây.

```
eksctl version
```

![Create Eksctl](/images/3-Createeksctl/0002-installeksctl.png)

3. Kích hoạt tính năng bash-completion của eksctl

```
eksctl completion bash >> ~/.bash_completion
. /etc/profile.d/bash_completion.sh
. ~/.bash_completion
```

![Create Eksctl](/images/3-Createeksctl/0003-installeksctl.png)

{{% notice note %}}
Thông tin cài đặt **Eksctl** xem thêm tại [Eksctl](https://docs.aws.amazon.com/eks/latest/userguide/eksctl.html)
{{% /notice %}}