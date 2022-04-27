---
title : "Introduction"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 1. </b> "
---

### Overview

**Kubernetes (K8s)** is an open source, extensible platform for managing packaged applications and services, facilitating configuration and automating application deployment.

- In this lab, we will create a simple **Kubernetes Cluster** on **AWS EKS (Elastic Kubernetes Service)**. Then I will deploy the site on the cluster and use **AWS CodePipeLine** for automated deployment.

![Elastic Kubernetes Service](/images/1-Introduce/CI_CDwithAWSCodePipeline.png)

### Content

1. [Introduction](../1-introduce/)
2. [Preparation steps](../2-Prerequiste/)
3. [Create EKS cluster](../3-Createekscluster/)
4. [Create Code Pipeline](../4-Createcicd/)
5. [Resource Cleanup](../5-cleanup/)