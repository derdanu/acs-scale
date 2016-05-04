# Login
```
Login-AzureRmAccount
```
# Deployment of ACS
```
New-AzureRmResourceGroup -Location northeurope -Name ACStest
New-AzureRmResourceGroupDeployment -Name ACSDeployment -ResourceGroupName ACStest -TemplateFile .\acs.json -TemplateParameterFile .\acs.parameters.json
```
# Get Swarm Node Scale Set name
```
Find-AzureRmResource -ResourceGroupNameContains  ACStest2 -ResourceType "microsoft.compute/virtualMachineScaleSets" | Select-Object -Property ResourceName
```

# Scale in or out of the existing ACS
```
New-AzureRmResourceGroupDeployment -Name ACSScale -ResourceGroupName ACStest -TemplateFile .\acs-scale.json -vmSSName swarm-agent-D3A28560-vmss -agentCount 5
```



