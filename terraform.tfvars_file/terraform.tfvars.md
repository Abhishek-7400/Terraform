# In Terraform, a .tfvars file is used to store variable values separately from the main configuration files. 
# This allows you to keep sensitive or environment-specific information out of your main Terraform files, making your configurations more modular and easier to manage across different environments.
## Example (using default terraform.tfvars file)
```
variable username {
  type = string
}
variable age {
  type = number
}
output detail{
  value = "my name is ${var.username} and my age is ${var.age}."
}
```
### Output
```
Changes to Outputs:
  + detail = "my name is Abhishek and my age is 23."
```
## Example (Using customize detail.tfvars file)
### ON command line just enter
```
terraform plan -var-file=detail.tfvars
```
### output
```
Changes to Outputs:
  + detail = "my name is Ravi and my age is 23."
```
