<!-- BEGIN_TF_DOCS -->

# Terraform Module Template

The purpose of this template is to speed up the creation of Terraform module template within HMCTS and help keep the same standards across multiple teams. If you need to create a new app, you can simply use this one as a starting point and build on top of it.A brief description of what this project does and who it's for.

## Github actions in the workflow

A typical workflow for a Terraform module includes terraform init and terraform validate commands. The init command initializes the module and downloads any needed providers. The validate command helps validate the configuration files in the module and is useful for general verification.
Now, let’s take a look at how to construct this workflow with a GitHub Actions workflow file. Create a new workflow file at /.github/workflows/terraform.yml in the root of the GitHub repository.
Workflow should be triggered on a pull request event opened against the master branch. Then, define each step to be run during this workflow. In the example, we use the predefined checkout action to retrieve the code contained in the repository. /cnp-azuredevops-libraries file change to execute mode after that it run the file use the bash shell script. Specify steps to execute terraform init,validate and format commands.

## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_azurerm"></a> [azurerm](#requirement\_azurerm) | >= 3.7.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_azurerm"></a> [azurerm](#provider\_azurerm) | >= 3.7.0 |

## Resources

| Name | Type |
|------|------|
| [azurerm_resource_group.rg](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/resource_group) | resource |
| [azurerm_subscription.current](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/data-sources/subscription) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_common_tags"></a> [common\_tags](#input\_common\_tags) | Common tag to be applied to resources. | `map(string)` | n/a | yes |
| <a name="input_component"></a> [component](#input\_component) | https://hmcts.github.io/glossary/#component | `string` | n/a | yes |
| <a name="input_env"></a> [env](#input\_env) | Environment value. | `string` | n/a | yes |
| <a name="input_existing_resource_group_name"></a> [existing\_resource\_group\_name](#input\_existing\_resource\_group\_name) | Name of existing resource group to deploy resources into | `string` | `null` | no |
| <a name="input_location"></a> [location](#input\_location) | Target Azure location to deploy the resource | `string` | `"UK South"` | no |
| <a name="input_name"></a> [name](#input\_name) | The default name will be product+component+env, you can override the product+component part by setting this | `string` | `""` | no |
| <a name="input_product"></a> [product](#input\_product) | https://hmcts.github.io/glossary/#product | `string` | n/a | yes |
| <a name="input_project"></a> [project](#input\_project) | Project name - sds or cft. | `any` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_resource_group_location"></a> [resource\_group\_location](#output\_resource\_group\_location) | n/a |
| <a name="output_resource_group_name"></a> [resource\_group\_name](#output\_resource\_group\_name) | n/a |
<!-- END_TF_DOCS -->