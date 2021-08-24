# deploy azure resources

## resource groups

Default resource group name is appName-location.
In this app, appName is `sample-keda` and location is `japaneast`

```bash
az group create --name sample-keda --location japaneast
```

## prerequisit

```bash
# deploy log analytics workspace
az deployment group create -f deploy-workspace.bicep --resource-group sample-keda

# deploy virtual networks
az deployment group create -f deploy-vnet.bicep --resource-group sample-keda

# deploy workspace acr and aks
az deployment group create -f deploy-aks-aci.bicep --resource-group sample-keda

```

## containers