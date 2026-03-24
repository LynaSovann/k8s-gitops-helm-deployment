# AWS EKS (Elastic Kubernetes Service)

## Table of Contents

- [What is EKS](#what-is-eks)
- [Why EKS](#why-eks)

## What is EKS?

Amazon EKS (Elastic Kubernetes Service) is a managed Kubernetes service where AWS handles the **control plane**.

AWS manages:

- Kubernetes API Server
- Scheduler
- Controller Manager
- etcd
- Scaling and backups

## Why EKS?

- Simplifies Kubernetes operations
- Reduce security and maintenance overhead
- Integrates with AWS services (S3, IAM, Secrets Manager, Load Balancers...)

## Work Node Options

EKS does **node fully manage worker nodes**, but provides 3 options:

1. Self-Managed Nodes

- Manually provision EC2 instances
- Install:
  - Kubelet
  - Kube-proxy
  - Container runtime
- Responsible for updates and security

2. Managed Node Groups

- AWS manages EC2 lifecycle
- Uses EKS-optimized AMIs
- Auto Scaling included
- Easy create/update/delete

3. Fargate (Serverless)

- No EC2 management
- Runs pods on demand
- Auto-selects compute resources
- Pay only for usage

## Create EKS Cluster

Basic configuration includes:

- Cluster name & Kubernetes version
- IAM role
- VPC & subnets
- Security Groups
- Storage & Secrets

## Create Worker Nodes

- Create node group
- Select instance type
- Set min/max/desired capacity
- Attach to EKS cluster

## Connect to Cluster

```bash
aws eks update-kubeconfig --region <region> --name <cluster-name>
kubectl get nodes
```
