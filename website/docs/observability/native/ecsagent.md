---
title: "Enabling the CloudWatch agent"
sidebar_position: 10
description: "Install the ECS Agent via the EKS cluster add-on"
---

::required-time

We will enable the CloudWatch agent in our EKS cluster by adding the Amazon CloudWatch Observability add-on. This addon will gather the OTEL metrics being published by the services in our application.


First, we will setup the necessary permissions by attaching the AWS managed IAM policy called "CloudWatchAgentServerPolicy" to your worker nodes. in this workshop, our nodegroup runs with the following IAM role "eks-workshop-cluster-managed-ondemand." To attach the role to the IAM role for our node group, we enter the following command:

```bash
$ aws iam attach-role-policy \
--role-name eks-workshop-cluster-managed-ondemand \
--policy-arn arn:aws:iam::aws:policy/CloudWatchAgentServerPolicy 
```

Next we will create the add-on in the EKS cluster:

```bash
$ aws eks create-addon --cluster-name eks-workshop --addon-name amazon-cloudwatch-observability
```

Click the following button to view the add-on in the console (Scroll down to see the Amazon Observability Addon).


<ConsoleButton url="https://console.aws.amazon.com/eks/home#/clusters/watchapp-lab?selectedTab=cluster-add-ons-tab" service="aps" label="Open EKS Addons console"/>