# In Security Group we define ingress i.e incoming address and engress i.e outgoing address.
# we can define more then one ingress rule for different address.
```
provider "aws" {
  region = "us-west-2"  # Change to your desired region
}

resource "aws_security_group" "example" {
  name        = "example-security-group"
  description = "Example security group for Terraform"
  
  vpc_id = "vpc-12345678"  # Change to your VPC ID
  
  # Ingress rules
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

  # Egress rule
  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"  # Allow all protocols
    cidr_blocks = ["0.0.0.0/0"]
  }
}
