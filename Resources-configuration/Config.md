# For Provider
In Terraform, you use provider blocks to specify the infrastructure provider you want to use and configure the details necessary for Terraform to interact with that provider's API. For AWS (Amazon Web Services), you would use a provider block to define AWS as your infrastructure provider.
```
provider "aws" {
  region = "us-west-2"
  access_key = "your_access_key"
  secret_key = "your_secret_key"
}
```
# For Resource Block

In Terraform, a resource block defines a single resource managed by Terraform. Resources represent infrastructure components such as virtual machines, databases, networks, security groups, etc., that you want to create and manage using Terraform.
## Here's the basic syntax of a Resource Block :
```
resource "resource_type" "resource_name" {
  # Configuration settings for the resource
}
```
example
```
resource "aws_instance" "example_instance" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
  tags = {
    Name = "example-instance"
  }
}
```
# For Data Block
In Terraform, a data block is used to retrieve and reference information from remote data sources, such as existing infrastructure components or external systems, without actually creating or managing those resources. Data blocks allow you to query information from external sources and use that data within your Terraform configuration.
## Here's the basic syntax of a data block:
```
data "data_source_type" "data_source_name" {
  # Configuration settings for the data source
}
```
## example
```
data "aws_ami" "example_ami" {
  most_recent = true
  owners      = ["amazon"]

  filter {
    name   = "name"
    values = ["ubuntu/images/hvm-ssd/ubuntu-focal-20.04-amd64-server-*"]
  }
}
```
# For Variable Block
In Terraform, a variable block is used to declare input variables within your configuration. Variables allow you to parameterize your Terraform code, making it more flexible and reusable across different environments or scenarios. You can define variables for values that may vary between deployments, such as IP addresses, instance types, or resource names.
## Here's the basic syntax of a variable block:
```
variable "variable_name" {
  type        = <data_type>
  default     = <default_value>
  description = "Description of the variable."
}
```
## example
```
variable "instance_type" {
  type        = string
  default     = "t2.micro"
  description = "The instance type for the EC2 instance."
}

variable "ami_id" {
  type        = string
  description = "The ID of the Amazon Machine Image (AMI) to use for the EC2 instance."
}
```
variable: This keyword indicates that you're defining a variable block.

"variable_name": This is the name of the variable you're defining. It's used to reference the variable within your Terraform configuration.

type: This attribute specifies the data type of the variable, such as string, number, list, map, bool, etc. It defines the kind of values that can be assigned to the variable.

default: This attribute specifies a default value for the variable. If no value is provided when running Terraform, it will use this default value. This attribute is optional.

description: This attribute provides a description of the variable, explaining its purpose or usage. While optional, providing descriptions can improve the clarity and maintainability of your code, especially for shared configurations.
