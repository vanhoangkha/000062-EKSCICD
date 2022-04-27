---
title : "Clean up resources"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 5. </b> "
---

#### Clear stack using AWS CloudFormation console

1. Open the [AWS CloudFormation](https://console.aws.amazon.com/cloudformation) console

2. In the **Stack** page of **AWS CloudFormation**, select the **Stack** that you want to delete
3. Select **Delete**
4. Select **Delete stack**


#### Delete Repository

1. Open the [Amazon ECR console](https://console.aws.amazon.com/ecr/repositories)

2. On the navigation bar, select **Region** containing the repository to be deleted
3. Select **Repository**
4. In the **Repository** page, select **Private**
5. Select **Repository** to delete and select **Delete**
6. Verify delete **Repository** and select **Delete**


#### Delete EKSCluster

1. Open [Amazon EKS console](https://console.aws.amazon.com/eks/home#/clusters) page

2. Select the cluster to delete and select **Delete**
3. Verify cluster deletion and select **Delete**

#### Delete an AWS Cloud9 environment using the AWS Cloud9 console

1. Select **AWS Cloud9** and select **Go TO Your Dashboard**
2. Select the environment to delete and select **Delete**
3. Verify the deletion of the environment by entering ``Delete`` and selecting **Delete**. The environment will be deleted after a few minutes.