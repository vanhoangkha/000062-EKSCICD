---
title : "Deploying the application"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3.3 </b> "
---

#### Deploy application to EKS cluster

1. Deploy a static Website to the EKS Cluster you just created. To deploy, we will first run the following command:

```
kubectl create deployment fcj-workshop --image=awsfcj/000062
```

![Deploywebsite](/images/6-Deploywebsite/0001-deploywebsite.png)

{{% notice info %}}
**awsfcj/00062** is a pre-built image to use in this lab
 {{% /notice %}}

![Deploywebsite](/images/6-Deploywebsite/0006-deploywebsite.png)

2. To be able to access the Website from outside the EKS cluster, we will have to deploy a LoadBalancer Service to the cluster with the following command:

```
kubectl expose deployments/fcj-workshop --type=LoadBalancer --port=80
```

![Deploywebsite](/images/6-Deploywebsite/0002-deploywebsite.png)

3. To view information about LoadBalancer above, I will run the following command:
   
```
kubectl get svc
```

![Deploywebsite](/images/6-Deploywebsite/0003-deploywebsite.png)

4. Copy the link in **EXTERNAL-IP** into the browser to access the website

![Deploywebsite](/images/6-Deploywebsite/0004-deploywebsite.png)


5. Visit the website

![Deploywebsite](/images/6-Deploywebsite/0004-deploywebsite.png)