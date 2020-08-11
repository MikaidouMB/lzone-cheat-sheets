
## CLI

    az login

    az aks get-credentials --resource-group <group name> --name <name>

## Resources / Groups

    az resource list
    az resource list --name <name>
    
    az group list
    
    az resource show   --name MySubnet --resource-group MyResourceGroup --resource-type "Microsoft.Compute/virtualMachines"
    az resource delete --name MyVm --resource-group MyResourceGroup --resource-type "Microsoft.Compute/virtualMachines"     


## ARM

- [arm-ttk: Template validation](https://dev.to/omiossec/how-to-test-your-azure-arm-template-with-arm-template-toolkit-arm-ttk-2492)
- ARM What-If Validation
  - https://blog.tyang.org/2020/04/26/validating-arm-templates-with-arm-what-if-operations/
  - https://4bes.nl/2020/06/28/step-by-step-test-and-deploy-arm-templates-with-github-actions/
  
        $Parameters = @{
          ResourcegroupName    = "ARMDeploymentTest"
          Templatefile         = ".\StorageAccount\azuredeploy.json"
          TemplateParameterfile = ".\StorageAccount\azuredeploy.parameters.json"
          Mode                 = 'Incremental'
        }
        $Result = Get-AzResourceGroupDeploymentWhatIfResult @Parameters
        $Result
        
     or
     
        az deployment group what-if -g <group> -f <template file> -p <parameters>
  
- [Pester: Template deployment validation](https://medium.com/charot/test-arm-templates-using-pester-azure-devops-837b5006c30c)