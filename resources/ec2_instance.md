```
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }



provider "aws" {
  region     = "ap-south-1"
  access_key = " "
  secret_key = "  "

}

resource "aws_instance" "terraform_instance" {
  ami           = "ami-007020fd9c84e18c7"
  instance_type = "t2.micro"
  key_name = "terraform"
  tags = {
    Name = "HelloWorld"
  }
}
```
# to Check provider which one using
```
terraform providers
```
# to initiate
```
terraform init
```
# to plan
```
terraform Plan
```
# to apply
```
terraform apply
```
# to destroy
```
terraform destroy
```
# to destory particular resource
```
terraform destroy --target resource_type.resource_name
```

