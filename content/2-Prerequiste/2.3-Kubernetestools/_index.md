---
title : "Installing Kubernetes Tool"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---

#### Install Kubernetes Tool

1. Copy and Paste the command below into **Terminal of Cloud9 Workspace** to install **kubectl**.

```
sudo curl --silent --location -o /usr/local/bin/kubectl \
   https://amazon-eks.s3.us-west-2.amazonaws.com/1.17.11/2020-09-18/bin/linux/amd64/kubectl

sudo chmod +x /usr/local/bin/kubectl
```

![Install Kubernetes Tool](/images/2-Prerequiste/2.3-Kubernetestools/0001-kubernetestools.png)


2. Copy and Paste the command below into **Terminal of Cloud9 Workspace** to update **awscli**.

```
sudo pip install --upgrade awscli && hash -r
```

![Install Kubernetes Tool](/images/2-Prerequiste/2.3-Kubernetestools/0002-kubernetestools.png)


3. Copy and Paste the command below into **Terminal of Cloud9 Workspace** to install tools to support text processing on the command line.

```
sudo yum -y install jq gettext bash-completion moreutils

```

![Install Kubernetes Tool](/images/2-Prerequiste/2.3-Kubernetestools/0003-kubernetestools.png)

4. We consider **jq** like sed for JSON data - you can use it to slice and filter and map and transform structured data with the same ease as sed, awk , grep.

```
echo 'yq() {
  docker run --rm -i -v "${PWD}":/workdir mikefarah/yq "$@"
}' | tee -a ~/.bashrc && source ~/.bashrc

```

![Install Kubernetes Tool](/images/2-Prerequiste/2.3-Kubernetestools/0004-kubernetestools.png)

5. Check the installed tools by running the command below.

```
for command in kubectl jq envsubst aws
  do
    which $command &>/dev/null && echo "$command in path" || echo "$command NOT FOUND"
  done

```

![Install Kubernetes Tool](/images/2-Prerequiste/2.3-Kubernetestools/0005-kubernetestools.png)

6. Enable autocomplete for the kubectl tool by running the command below:

```
kubectl completion bash >> ~/.bash_completion
. /etc/profile.d/bash_completion.sh
. ~/.bash_completion
```

![Install Kubernetes Tool](/images/2-Prerequiste/2.3-Kubernetestools/0006-kubernetestools.png)

7. Set up version 2.2.0 using AWS Load Balancer Controller

```
echo 'export LBC_VERSION="v2.2.0"' >> ~/.bash_profile
. ~/.bash_profile

```

![Install Kubernetes Tool](/images/2-Prerequiste/2.3-Kubernetestools/0007-kubernetestools.png)

{{% notice info %}}
Information on installing **Kubernetes Tool** can be found at [Kubernetes Tool](https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html)
{{% /notice %}}