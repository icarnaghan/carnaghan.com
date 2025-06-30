---
author: "icarnaghan"
title: "CKA Study Notes - kubectl Basics"
date: 2025-06-23
categories: 
  - "coding"
tags: 
  - "cka"
  - "kubernetes"
  - "devops"
  - "kubectl"
---

I've recently started studying for the Certified Kubernetes Administrator (CKA) exam and as such I'm capturing some of my study notes here. When you're first diving into Kubernetes, the command-line tool kubectl becomes your new best friend. But like any new tool, remembering the right commands can be challengins, especially when you're trying to troubleshoot or quickly inspect your cluster.

This is my own quick-reference guide for working with kubectl, with just enough commentary to help it stick. If you're interested in learning more I would recommend visiting the [Official Kubernetes Documentation site](https://kubernetes.io/docs/home/), which covers everything you need.

## A Quick Note on `kubectl` Conventions

There are two main ways to interact with Kubernetes using `kubectl`:

- **Imperative commands** – You tell Kubernetes *what to do right now*. Example:
```
kubectl run mypod --image=nginx
```

- **Declarative configuration** – You define what the desired state should be in a YAML file, then apply it:

```
kubectl apply -f pod.yaml
```

In general, imperative is useful for quick experiments or ad-hoc changes, while declarative is preferred for production environments where consistency, version control, and repeatability matter. 

> For examples declarative yaml  for creating pods, see https://kubernetes.io/docs/concepts/workloads/pods/.

### Cluster Overview
```
kubectl get all                         # Show all running resources in the current namespace
```

Use this when you just want a quick snapshot of what’s happening in your cluster.

### Pods Basics
```
kubectl get pods                        # List all pods
kubectl get pods -o wide                # Include more info (IP, node, etc.)
kubectl run mypod --image=nginx         # Create a pod with the nginx image
kubectl run mypod --image=nginx \
  --dry-run=client -o yaml              # Generate YAML without creating the pod
kubectl apply -f pod-definition.yaml    # Apply configuration from a YAML file
kubectl describe pod mypod              # Detailed info about a specific pod
```

Essential for inspecting and managing your pods manually or through definitions.

### ReplicaSets (rs)

```
kubectl create -f replicaset-definition.yml        # Create a ReplicaSet from file
kubectl get rs                                     # List all ReplicaSets
kubectl delete rs myapp-replicaset                 # Delete a specific ReplicaSet
kubectl replace -f replicaset-definition.yml       # Replace existing ReplicaSet
kubectl scale --replicas=6 -f replicaset-definition.yml  # Scale up/down
kubectl explain replicaset                         # Get documentation on fields
kubectl edit rs myapp-replicaset                   # Edit a ReplicaSet in your editor
```

ReplicaSets ensure high availability by keeping a set number of pod replicas running.

### Namespaces

```
kubectl get pods --namespace=dev                          # View pods in a specific namespace
kubectl get pods --all-namespaces                         # View all pods across all namespaces
kubectl config set-context $(kubectl config current-context) --namespace=dev
                                                          # Set the default namespace for current context
```

Namespaces are a great way to organize resources, especially in multi-team or multi-project clusters.

## Final Thoughts

One take away I've quickly realized is that learning kubectl is all about repetition. The best way to learn is by starting to use these commands regularly in your projects. Over time, they’ll become second nature.
