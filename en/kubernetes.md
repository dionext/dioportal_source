---
title: "Kubernetes"
description: ""
keywords: ""
lang: "en"
permalink: "kubernetes"
aliases:
  - "kubernetes"
---

# Kubernetes

## Overview

[https://kubernetes.io/](https://kubernetes.io/)

Kubernetes is an open-source container orchestration system for automating software deployment, scaling, and management. Originally designed by Google, the project is now maintained by a worldwide community of contributors, and the trademark is held by the Cloud Native Computing Foundation. [https://en.wikipedia.org/wiki/Kubernetes](https://en.wikipedia.org/wiki/Kubernetes)

## Commands

kubectl cluster-info

kubectl get nodes  
kubectl get nodes --output wide  
kubectl --kubeconfig \[USER\_CLUSTER\_KUBECONFIG\] get nodes --output wide

kubectl get all

kubectl get pods  
kubectl get replicasets  
kubectl get services  
kubectl get secrets

kubectl get ingress -o wide (дает ingress сервисы )

kubectl get svc --all-namespaces kubectl get services --all-namespaces (сервисы во всех неймспесах)

kubectl get endpoints  
kubectl get events  
kubectl get storageclasses

```
kubectl config view
```

## Clearing

kubectl delete pod pod-nginx

kubectl delete pod --all

kubectl get all

kubectl delete \[deploy/simple-deployment\] \[svc/simple-service\]

All

kubectl delete deployment --all

kubectl delete service --all

kubectl delete daemonsets,replicasets,services,deployments,pods,rc --all

kubectl delete ingress --all

kubectl delete namespace k8sdemo-app

kubectl delete -f file.yaml

[https://github.com/kubernetes/kubernetes/issues/60807](https://github.com/kubernetes/kubernetes/issues/60807)

```
kubectl get namespace "stucked-namespace" -o json \
            | tr -d "\n" | sed "s/\"finalizers\": \[[^]]\+\]/\"finalizers\": []/" \
            | kubectl replace --raw /api/v1/namespaces/stucked-namespace/finalize -f -
```

kubectl get namespace "ingress-controller" -o json | tr -d "\\n" | sed "s/\\"finalizers\\": \\\[\[^\]\]\\+\\\]/\\"finalizers\\": \[\]/" | kubectl replace --raw /api/v1/namespaces/ingress-controller/finalize -f -

kubectl get namespace "cattle-system" -o json | tr -d "\\n" | sed "s/\\"finalizers\\": \\\[\[^\]\]\\+\\\]/\\"finalizers\\": \[\]/" | kubectl replace --raw /api/v1/namespaces/cattle-system/finalize -f -

## Installation and management

### Windows Docker Desktop

[WSL - the Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/)

[https://kubernetes.io/blog/2020/05/21/wsl-docker-kubernetes-on-the-windows-desktop/](https://kubernetes.io/blog/2020/05/21/wsl-docker-kubernetes-on-the-windows-desktop/)

[https://docs.microsoft.com/en-us/windows/wsl/install-win10](https://docs.microsoft.com/en-us/windows/wsl/install-win10)

[https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/quick-start/quick-create-virtual-machine](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/quick-start/quick-create-virtual-machine)

(PowerShell admin mode)

```
PS C:\WINDOWS\system32> minikube delete 
PS C:\WINDOWS\system32> kubectl config use-context minikube
PS C:\WINDOWS\system32> minikube start --vm-driver=hyperv
```

minikube status

If you have enough CPU and RAM resources, you can easily have both minikube and docker-for-desktop on the same machine and switch between them by selecting context, for example: [https://codefresh.io/kubernetes-tutorial/local-kubernetes-windows-minikube-vs-docker-desktop/#:~:text=Docker-for-windows uses Type,while Minikube supports both hypervisors.\&text=If you are running virtual,you enable type-1 hypervisors](https://codefresh.io/kubernetes-tutorial/local-kubernetes-windows-minikube-vs-docker-desktop/#:~:text=Docker%2Dfor%2Dwindows%20uses%20Type,while%20Minikube%20supports%20both%20hypervisors.&text=If%20you%20are%20running%20virtual,you%20enable%20type%2D1%20hypervisors).

```
> kubectl config get-contexts
> kubectl config use-context docker-for-desktop
```

[https://www.assistanz.com/installing-minikube-on-windows-10-home-edition-using-virtualbox/](https://www.assistanz.com/installing-minikube-on-windows-10-home-edition-using-virtualbox/)
minikube start

minikube version

minikube status

minikube docker-env

### Linux

[https://kubernetes.io/docs/tasks/tools/install-kubectl/](https://kubernetes.io/docs/tasks/tools/install-kubectl/)

### Helm

[https://helm.sh/docs/intro/install/](https://helm.sh/docs/intro/install/)

[https://helm.sh/docs/faq/](https://helm.sh/docs/faq/)

### Rancher

[https://www.youtube.com/watch?v=LaAnOxy4efc](https://www.youtube.com/watch?v=LaAnOxy4efc)

[https://rancher.com/docs/rancher/v2.x/en/installation/other-installation-methods/single-node-docker/advanced/](https://rancher.com/docs/rancher/v2.x/en/installation/other-installation-methods/single-node-docker/advanced/)

```
2.4
```

```
docker run -d --restart=unless-stopped \
  -p 80:80 -p 443:443 --name rancher \
  -v /mnt/devops/rancher:/var/lib/rancher \
  rancher/rancher:v2.4-head 
```

System requirements: 1CPU/4RAM - 2CPU/4RAM

```
2.5
```

```
docker run -d --restart=unless-stopped \
  -p 80:80 -p 443:443 --name rancher \
  -v /mnt/devops/rancher:/var/lib/rancher \
  --privileged \
  rancher/rancher:latest
```

## References
