# armtemplates

# Azure Kubernetes Service (AKS)

![Azure Public Test Date](https://azurequickstartsservice.blob.core.windows.net/badges/101-aks-vmss-systemassigned-identity/PublicLastTestDate.svg)
![Azure Public Test Result](https://azurequickstartsservice.blob.core.windows.net/badges/101-aks-vmss-systemassigned-identity/PublicDeployment.svg)

![Azure US Gov Last Test Date](https://azurequickstartsservice.blob.core.windows.net/badges/101-aks-vmss-systemassigned-identity/FairfaxLastTestDate.svg)
![Azure US Gov Last Test Result](https://azurequickstartsservice.blob.core.windows.net/badges/101-aks-vmss-systemassigned-identity/FairfaxDeployment.svg)

![Best Practice Check](https://azurequickstartsservice.blob.core.windows.net/badges/101-aks-vmss-systemassigned-identity/BestPracticeResult.svg)
![Cred Scan Check](https://azurequickstartsservice.blob.core.windows.net/badges/101-aks-vmss-systemassigned-identity/CredScanResult.svg)

[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fabotzki%2Fmain%2Farmtemplates%2Faks-nodepools.json)

This template deploys a managed **Azure hosted Kubernetes cluster** via **Azure Kubernetes Service (AKS)** with **Virtual Machine Scale Sets** Agent Pool.

**VMSS based agent pools** gives **AKS cluster** **auto-scaling** capabilities.
See [https://docs.microsoft.com/en-us/azure/aks/cluster-autoscaler#about-the-cluster-autoscaler](https://docs.microsoft.com/en-us/azure/aks/cluster-autoscaler#about-the-cluster-autoscaler) for detailed information about cluster auto-scaler. 

## Sample overview and deployed resources

This is an overview of the solution

The following resources are deployed as part of the solution

### Resource provider Microsoft.ContainerService

Description Resource Provider Microsoft.ContainerService

+ **Resource type managedClusters**: Azure Kubernetes Service Managed Cluster

This deployment will also create another `Managed` Resource Group with name `MC_#{AksResourceGroupName}#_#{YourAksClusterName}#_#{AksResourceLocation}#` which will be managed by the cluster and used to provision cluster resources.  

## Deployment steps

You can click the "deploy to Azure" button at the beginning of this document or follow the instructions for command line deployment using the scripts in the root of this repo.

## Usage

### Connect

How to connect to the solution

The template deployment will output `controlPlaneFQDN` value while will be the Kubernetes API endpoint for the cluster.  

Sample Output:

```
Outputs:
Name                Type                       Value
==================  =========================  ==========
controlPlaneFQDN    String                     #{Your DNS Prefix}#-a38a5fa0.hcp.#{AksResourceLocation}#.azmk8s.io
```

#### Management

How to manage the solution

To get your credentials for your kubectl-cli you can use the Azure CLI command: 

```bash
az aks get-credentials --name MyManagedCluster --resource-group MyResourceGroup
```

## Notes

Solution notes

`Tags: AKS, Azure Kubernetes Service, Virtual Machine Scale Sets`
