# In Security Group we define ingress i.e incoming address and engress i.e outgoing address.
## we can define more then one ingress rule for different address.
## If we not define the VPC,Security group will be create in default VPC. 
## cidr_blocks we define ip address who can access.
```
provider "aws" {
  region     = "ap-south-1"
  access_key = " "
  secret_key = "  "

}

resource "aws_security_group" "security_group_example" {
  name        = "example-security-group"
  description = "Example security group for Terraform"
  ingress {
    from_port   = 22
    to_port     = 22
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
  ingress {
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
  ingress {
    from_port   = 443
    to_port     = 443
    protocol    = "tcp"  
    cidr_blocks = ["0.0.0.0/0"]
  }
 tags = {
    Name = "terraform_security_group"
  }
}
```
# By Defining different ingress rule for different address we can define it in one ingress rule by using dynamic Block.
## A dynamic block acts much like a for expression, but produces nested blocks instead of a complex typed value.
```
provider "aws" {
  region     = "ap-south-1"
  access_key = " "
  secret_key = "  "
}

resource "aws_security_group" "security_group_example" {
  name        = "example-security-group-1"
  description = "Example security group for Terraform"

 dynamic "ingress" {
    for_each = [22,80,443]
     iterator = port
    content {
      from_port   = port.value.from_port
      to_port     = port.value.to_port
      protocol    = "tcp" 
      cidr_blocks = ["0.0.0.0/0"]
    }
 tags = {
    Name = "terraform_security_group-2"
  }
}
```


}
