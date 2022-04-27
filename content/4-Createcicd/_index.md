---
title : "Create CI/CD"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

### Overview

- In the next steps, we will create a Deployment Pipeline using AWS CodePipeline and integrate with the third party tool GitHub. When we change the code on GitHub, our Pipeline will be activated and deploy the new version of the application to the web application we already run on the EKS Cluster.


### Content

1. [Create S3 bucket](4.1-creates3bucket/)
2. [Create CodePipeline Service Role](4.2-codepipelineservicerole/)
3. [Create Code Buid Service Role](4.3-codebuildservicerole/)
4. [Allow role eks-CodeBuildServiceRole permissions in RBAC of EKS cluster](4.4-rbac/)
5. [Forke source code](4.5-forksourcecode/)
6. [Generate CodePipeline](4.6-createcodepipeline/)
7. [CI/CD Check](4.7-checkcicd/)