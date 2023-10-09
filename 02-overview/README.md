## 02 - Overview + Setup

## Install Terraform

Official installation instructions from HashiCorp: https://learn.hashicorp.com/tutorials/terraform/install-cli

## AWS Account Setup

AWS Terraform provider documentation: https://registry.terraform.io/providers/hashicorp/aws/latest/docs#authentication

1) create non-root AWS user
2) Add the necessary IAM roles (e.g. AmazonEC2FullAccess)
3) Save Access key + secret key (or use AWS CLI `aws configure` -- https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)

## Hello World

`./main.tf` contains minimal configuration to provision an EC2 instance.

1) `aws configure`
2) `terraform init` Initializes the back-end, and stores the state locally.
3) `terraform plan` Queries AWS API and shows a comparison of whats currently deployed (current state in aws) and the resources in our .ft (config) file
4) `terraform apply` Takes the action in the plan
5) terraform destroy To remove all we did and dont get billed
