---
title: "Observability with AWS Services"
sidebar_position: 25
sidebar_custom_props: { "module": true }
description: "Build observability capabilities for Amazon Elastic Kubernetes Service around AWS Services."
---

::required-time

:::tip Before you start
Prepare your environment for this section:

```bash timeout=3600 wait=30
$ prepare-environment
```

:::

In this lab, we focus on the using AWS native services to create an observability solution for our application. We will show how the ECS agent can help us gather logs, metrics, and traces. We will then explore how to leverage AWS services to gain insights into our application. 
