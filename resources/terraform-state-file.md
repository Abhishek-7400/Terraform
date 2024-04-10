# Terraform State File(terraform.tfstate)
1. The terraform state file which check the state of infrastructure and it ts compulsory to create.
2. by default, is named terraform. tfstate and is held in the same directory where Terraform is run. 
3. It is created after running terraform apply . 
4. The actual content of this file is a JSON formatted mapping of the resources defined in the configuration and those that exist in your infrastructure.
## code (store in Bakend locally)
```
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region     = "ap-south-1"
  
}
```
## code (store in Bakend s3 Bucket)
```
terraform {
  backend "s3" {
    bucket = "mybucket"     
    key    = "terraform.tfstate
    region = "ap-south-1"
  }
}

provider "aws" {
  region     = "ap-south-1"
  
}
```
## here bucket name is mention "mybucket" and file (key) "terraform.tfstate
