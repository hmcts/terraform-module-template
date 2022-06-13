# Terraform Module Template

The purpose of this template is to speed up the creation of Terraform module template within HMCTS and help keep the same standards across multiple teams. If you need to create a new app, you can simply use this one as a starting point and build on top of it.A brief description of what this project does and who it's for.

<!-- BEGIN_TF_DOCS -->


## Github actions in the workflow

A typical workflow for a Terraform module includes terraform init and terraform validate commands. The init command initializes the module and downloads any needed providers. The validate command helps validate the configuration files in the module and is useful for general verification.

Now, let’s take a look at how to construct this workflow with a GitHub Actions workflow file. Create a new workflow file at /.github/workflows/terraform.yml in the root of the GitHub repository.
Workflow should be triggered on a pull request event opened against the master branch. Then, define each step to be run during this workflow. In the example, we use the predefined checkout action to retrieve the code contained in the repository. /cnp-azuredevops-libraries file change to execute mode after that it run the file use the bash shell script. Specify steps to execute terraform init,validate and format commands.




## Providers

| Name | Version |
|------|---------|
| <a name="provider_azurerm"></a> [azurerm](#provider\_azurerm) | n/a |

## Resources

| Name | Type |
|------|------|
| [azurerm_resource_group.rg](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/resource_group) | resource |
| [azurerm_subscription.current](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/data-sources/subscription) | data source |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_password"></a> [password](#output\_password) | n/a |
| <a name="output_resource_group_location"></a> [resource\_group\_location](#output\_resource\_group\_location) | n/a |
| <a name="output_resource_group_name"></a> [resource\_group\_name](#output\_resource\_group\_name) | n/a |
<!-- END_TF_DOCS -->