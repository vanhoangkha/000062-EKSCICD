---
title : "Test CI/CD"
date : "`r Sys.Date()`"
weight : 7
chapter : false
pre : " <b>4.7 </b> "
---

#### Test CI/CD pipeline

1. Go to your **GitHub** https://github.com/{GITHUB_ACCOUNT}/000062-websource

 
- Select the fork repository
- Open the file **index.htlm**, select the edit icon
- Editing the code
- Then, select Commit changes

![Check CICD](/images/10-Checkcicd/0002-checkcicd.png)

2. After pushing the code, **CodePipeline** will be triggered to execute **CodeBuild**.

- Go to the admin page **CodePipeline** and you will see the status of the pipeline is **In Progress**
- Pipele's has 2 stages:
  - **Source**
  - Pull source from GitHub
  - Pack source for stage build
  - **Build**
  - Create **Docker image** from **source**
  - Push the image to **ECR repository**
  - Deploy application updates to **EKS cluster**

![Check CICD](/images/10-Checkcicd/0003-checkcicd.png)


3. Deploy application updates to EKS cluster Wait about 5-10 minutes for the build process to complete and switch to **Success** state.

![Check CICD](/images/10-Checkcicd/0003-checkcicd.png)

4. Go to the website URL to see the changes.

- At this time, the title of the website has changed to **AWS First Cloud Journey**

![Check CICD](/images/10-Checkcicd/0004-checkcicd.png)

Congratulations on completing the lab.