# Deployment of ACS
Login-AzureRmAccount
New-AzureRmResourceGroup -Location northeurope -Name ACStest
New-AzureRmResourceGroupDeployment -Name ACSDeployment -ResourceGroupName ACStest -TemplateFile .\acs.json -TemplateParameterFile .\acs.parameters.json

# Scale in or out of the existing ACS
New-AzureRmResourceGroupDeployment -Name ACSScale -ResourceGroupName ACStest -TemplateFile .\acs-scale.json -vmSSName swarm-agent-D3A28560-vmss -agentCount 5



