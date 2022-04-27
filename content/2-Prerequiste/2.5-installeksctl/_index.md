---
title : "Installing eksctl"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 2.5 </b> "
---

#### Install eksctl

1. In this section we will install the **eksctl** tool into **Cloud9 Workspace**.

- Run the command to download the **eksctl** tool.

```
curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp

sudo mv -v /tmp/eksctl /usr/local/bin
```

![Create Eksctl](/images/3-Createeksctl/0001-installeksctl.png)

2. Check if eksctl works or not with the command below.

```
eksctl version
```

![Create Eksctl](/images/3-Createeksctl/0002-installeksctl.png)

3. Enable bash-completion of eksctl

```
eksctl completion bash >> ~/.bash_completion
. /etc/profile.d/bash_completion.sh
. ~/.bash_completion
```

![Create Eksctl](/images/3-Createeksctl/0003-installeksctl.png)

{{% notice note %}}
Installation information **Eksctl** see more at [Eksctl](https://docs.aws.amazon.com/eks/latest/userguide/eksctl.html)
{{% /notice %}}