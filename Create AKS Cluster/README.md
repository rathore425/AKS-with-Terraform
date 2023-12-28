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
`# Replace Resource Group & Cluster Name
az aks get-credentials --resource-group aks-rg1 --name aksdemo1

# List Kubernetes Worker Nodes
kubectl get nodes 
kubectl get nodes -o wide
`