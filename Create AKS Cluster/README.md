# Setting Up and Exploring Azure AKS Cluster

# Step-01: Introduction
Welcome to the AKS Cluster setup guide! This guide will walk you through creating and exploring an Azure Kubernetes Service (AKS) Cluster. Let's dive in!

# Step-02: Create AKS Cluster
- Basic setup:
  - **Subscription:** Free Trial
  - **Resource Group:** Creat New: aks-rg1
  - **Cluster preset configuration:** Standard
  - **Kubernetes Cluster Name:** aksdemo1
  - **Region:** (US) Central US
  - **Availability zones:** Zones 1, 2, 3
  - **AKS Pricing Tier:** Free
  - **Kubernetes Version:** Select what ever is latest stable version
  - **Automatic upgrade:** Enabled with patch (recommended)
  - **Node Size:** Standard_B2s (Cheapest)
  - **Scale method:** Manual
  - **Node Count range:** 2
  - **Max pods per node:** 30
  - **Access**
  - **Authentication and Authorization:** 	Local accounts with Kubernetes RBAC
  - Rest all leave to defaults
- **Networking**
  - **Network Configuration:** Azure CNI
  - Review all the auto-populated details 
    - Virtual Network
    - Cluster Subnet
    - Kubernetes Service address range
    - Kubernetes DNS Service IP Address
    - DNS Name prefix
  - **Traffic routing:** leave to defaults
  - **Security:** Leave to defaults
- **Integrations**
  - **Azure Container Registry:** None
  - All leave to defaults
- **Advanced**
  -  All leave to defaults
- **Tags**
  - leave to defaults
- **Review + Create**
  - Click on **Create**

# Step-03: Cloud Shell - Configure kubectl to connect to AKS Cluster
- Go to https://shell.azure.com
- Run the following command
```t
# Replace Resource Group & Cluster Name
az aks get-credentials --resource-group aks-rg1 --name aksdemo1

# List Kubernetes Worker Nodes
kubectl get nodes 
kubectl get nodes -o wide
```

# Step-04: Explore Cluster Control Plane and Workload inside that
- Run the following command
```t
# List Namespaces
kubectl get namespaces
kubectl get ns

# List Pods from all namespaces
kubectl get pods --all-namespaces

# List all k8s objects from Cluster Control plane
kubectl get all --all-namespaces
```

# Step-05: Explore the AKS cluster on Azure Management Console
- Explore the following features on a high-level:
- **Overview**
  - Activity Log
  - Access Control (IAM)
  - Security
  - Diagnose and solver problems
  - Microsoft Defender for Cloud
- **Kubernetes Resources**  
  - Namespaces
  - Workloads
  - Services and Ingress
  - Storage
  - Configuration
- **Settings**
  - Node Pools
  - Cluster Configuration
  - Extensions + Applications
  - Backup (preview)
  - Open Service Mesh
  - GitOps
  - Automated Deployments (preview)
  - Policies
  - Properties
  - Locks
- **Monitoring**
  - Insights
  - Alerts
  - Metrics
  - Diagnostic Settings
  - Advisor Recommendations
  - Logs
  - Workbooks
- **Automation** 
  - Tasks
  - Export Template    
