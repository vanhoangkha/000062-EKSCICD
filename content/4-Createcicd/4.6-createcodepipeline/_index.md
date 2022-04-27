---
title : "Create a pipeline"
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : " <b>4.6 </b> "
---

#### Create a CI/CD pipeline with CodePipeline

1. We will create a CodePipeline using the AWS CloudFormation engine.

- Select Download [CloudFormation template file](https://raw.githubusercontent.com/First-Cloud-Journey/000062-EKSCICD/main/code_pipeline_fcj.yml)


![Create Code Pipeline](/images/9-Createcodepipeline/0001-Createcodepipeline.png)


2. In the [AWS Console](https://aws.amazon.com/console/)

- Find **CloudFormation**
- Select **CloudFormation**

![Create Code Pipeline](/images/9-Createcodepipeline/00013-Createcodepipeline.png)

1. In the **CloudFormation** interface

- Select **Stacks**
- Select **Create stack**
- Select **With new resources (standard)**

![Create Code Pipeline](/images/9-Createcodepipeline/0002-Createcodepipeline.png)

4. In the **Create stack** interface

- Select **Template is ready**
- Select **Upload a template file**
- Select **Choose file**
- Select the downloaded **CloudFormation template file**. Example ```code_pipeline_fcj.yml```
- Select **Next**

![Create Code Pipeline](/images/9-Createcodepipeline/0003-Createcodepipeline.png)

5. In the **Stack name** section, enter ```Eks-stack```

![Create Code Pipeline](/images/9-Createcodepipeline/0004-Createcodepipeline.png)

6. Next, fill in the following information:

- **User name**, enter the name **Github Account**
- Enter **Access token** created
- Enter the name **Repository**
- Enter **Branch**
- Enter the name **EksCluster**
- Enter **EksDeployment**
- Enter **EksNamespace**
- Select **Next**


![Create Code Pipeline](/images/9-Createcodepipeline/0005-Createcodepipeline.png)

7. Scroll to the bottom of the page and select **Next**


![Create Code Pipeline](/images/9-Createcodepipeline/0006-Createcodepipeline.png)

8. Scroll to the bottom of the page and select **Create stack**

![Create Code Pipeline](/images/9-Createcodepipeline/0007-Createcodepipeline.png)

9. Complete stack creation

![Create Code Pipeline](/images/9-Createcodepipeline/0008-Createcodepipeline.png)


10. In the [AWS Console](https://aws.amazon.com/console/)

- Find **CodePipeline**
- Select **CodePipeline**

![Create Code Pipeline](/images/9-Createcodepipeline/00012-Createcodepipeline.png)


11. View CI/CD process and select **details** to view build details

![Create Code Pipeline](/images/9-Createcodepipeline/0009-Createcodepipeline.png)

12. CI/CD process complete
 
![Create Code Pipeline](/images/9-Createcodepipeline/00010-Createcodepipeline.png)

13. Review the details of the build process by selecting **details**

![Create Code Pipeline](/images/9-Createcodepipeline/00011-Createcodepipeline.png)