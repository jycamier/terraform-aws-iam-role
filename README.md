<a href="https://lacework.com"><img src="https://techally-content.s3-us-west-1.amazonaws.com/public-content/lacework_logo_full.png" width="600"></a>

# terraform-aws-iam-role

[![GitHub release](https://img.shields.io/github/release/lacework/terraform-aws-iam-role.svg)](https://github.com/lacework/terraform-aws-iam-role/releases/)
[![Codefresh build status]( https://g.codefresh.io/api/badges/pipeline/lacework/terraform-modules%2Ftest-compatibility?type=cf-1&key=eyJhbGciOiJIUzI1NiJ9.NWVmNTAxOGU4Y2FjOGQzYTkxYjg3ZDEx.RJ3DEzWmBXrJX7m38iExJ_ntGv4_Ip8VTa-an8gBwBo)]( https://g.codefresh.io/pipelines/edit/new/builds?id=607e25e6728f5a6fba30431b&pipeline=test-compatibility&projects=terraform-modules&projectId=607db54b728f5a5f8930405d)

Terraform module that creates a cross-account IAM role to integrate Lacework and AWS accounts.

## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 0.14 |
| <a name="requirement_aws"></a> [aws](#requirement\_aws) | >= 3.0 |
| <a name="requirement_random"></a> [random](#requirement\_random) | >= 2.1 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | >= 3.0 |
| <a name="provider_random"></a> [random](#provider\_random) | >= 2.1 |

## Resources

| Name | Type |
|------|------|
| [aws_iam_role.lacework_iam_role](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role) | resource |
| [random_id.uniq](https://registry.terraform.io/providers/hashicorp/random/latest/docs/resources/id) | resource |
| [random_string.external_id](https://registry.terraform.io/providers/hashicorp/random/latest/docs/resources/string) | resource |
| [aws_iam_policy_document.lacework_assume_role_policy](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_create"></a> [create](#input\_create) | Set to false to prevent the module from creating any resources | `bool` | `true` | no |
| <a name="input_external_id_length"></a> [external\_id\_length](#input\_external\_id\_length) | The length of the external ID to generate | `number` | `16` | no |
| <a name="input_iam_role_name"></a> [iam\_role\_name](#input\_iam\_role\_name) | The IAM role name | `string` | `""` | no |
| <a name="input_lacework_aws_account_id"></a> [lacework\_aws\_account\_id](#input\_lacework\_aws\_account\_id) | The Lacework AWS account that the IAM role will grant access | `string` | `"434813966438"` | no |
| <a name="input_tags"></a> [tags](#input\_tags) | A map/dictionary of Tags to be assigned to created resources | `map(string)` | `{}` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_arn"></a> [arn](#output\_arn) | IAM Role ARN |
| <a name="output_created"></a> [created](#output\_created) | Was the IAM Role created |
| <a name="output_external_id"></a> [external\_id](#output\_external\_id) | The External ID configured into the IAM role |
| <a name="output_name"></a> [name](#output\_name) | IAM Role name |
