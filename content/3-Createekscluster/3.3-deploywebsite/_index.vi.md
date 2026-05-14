---
title : "Triển khai ứng dụng"
date: 2024-01-01
weight : 3
chapter : false
pre : " <b> 3.3 </b> "
---

#### Triển khai ứng dụng lên EKS cluster

1. Deploy một static Website vào EKS Cluster mình vừa tạo. Để deploy, đầu tiên chúng ta sẽ chạy command sau:

```
kubectl create deployment fcj-workshop --image=awsfcj/000062
```

![Deploywebsite](/images/6-Deploywebsite/0001-deploywebsite.png)

{{% notice info %}}
**awsfcj/00062** là image được build sẵn để sử dụng trong bài lab này 
 {{% /notice %}}

![Deploywebsite](/images/6-Deploywebsite/0006-deploywebsite.png)

2. Để có thể truy cập Website từ bên ngoài EKS cluster, chúng ta sẽ phải deploy một LoadBalancer Service vào cluster bằng command sau:

```
kubectl expose deployments/fcj-workshop --type=LoadBalancer --port=80
```

![Deploywebsite](/images/6-Deploywebsite/0002-deploywebsite.png)

3. Để xem thông tin về LoadBalancer trên, mình sẽ chạy command sau:
   
```
kubectl get svc
```

![Deploywebsite](/images/6-Deploywebsite/0003-deploywebsite.png)

4. Copy link trong **EXTERNAL-IP** vào trình duyệt sẽ truy cập được website

![Deploywebsite](/images/6-Deploywebsite/0004-deploywebsite.png)


5. Truy cập vào website

![Deploywebsite](/images/6-Deploywebsite/0004-deploywebsite.png)