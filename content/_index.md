---
title : "CI/CD on EKS"
date : "`r Sys.Date()`"
weight : 1
chapter : false
---

# CI/CD on EKS with CodePipeline and GitHub

- Amazon Elastic Kubernetes Service (Amazon EKS) is an AWS-managed container orchestration service that helps us to create, manage, launch, and scale Kubernetes applications in an AWS environment or on-- premise.

- AWS CodePipeline is a continuous delivery service that helps you automate deployment pipelines to keep your application or infrastructure up to date with new versions in a consistent manner. CodePipeline automates the build, test, and deployment phases of your deployment each time there is a code change, based on the deployment model you define. You can integrate AWS CodePipeline with third-party services such as **GitHub** or with your own custom plugin. With AWS CodePipeline, you only pay for what you use. You don't have to pay upfront or make a long-term commitment.

In this exercise, we will create an EKS Cluster and deploy a pipeline to automatically deploy to production every time there is a code change using the AWS CodePipeline service.