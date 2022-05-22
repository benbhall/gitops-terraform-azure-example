# gitops-terraform-azure-example
...

## Storing the Terraform File
...

```
# Create a Resource Group
az group create -n gitopsdemo-tfstates-rg -l uksouth
 
# Create a Storage Account
az storage account create -n gitopsdemostore -g gitopsdemo-tfstates-rg -l uksouth --sku Standard_LRS
 
# Create a Storage Account Container
az storage container create -n gitopsdemotfstates --account-name gitopsdemostore
```

## Azure Service Principal

We will need a service principal for Terraform to authenticate with Azure.

```
# Create a Service Principal 
Write-Output (az ad sp create-for-rbac --name gitopsdemo-tf-sp --role Contributor --scopes /subscriptions/<subscription-id>)
```

### Save the Service Principal Credentials

```

```