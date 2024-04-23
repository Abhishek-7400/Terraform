# In Security Group we define ingress i.e incoming address and engress i.e outgoing address.
## we can define more then one ingress rule for different address.
## If we not define the VPC,Security group will be create in default VPC. 
## cidr_blocks we define ip address who can access.
```
provider "aws" {
  region = "us-west-2"  # Change to your desired region
}

resource "aws_security_group" "example" {
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
}
