# Architecture
## image
```
https://github.com/Abhishek-7400/Terraform/blob/e5079128010bc75c80e9d04b685a8256617b321c/Architecure/terraform-architecture-diagram.png
```

## Terraform architecture mainly consists of the following components:
### Terraform Core
### Configure file
### Providers
### State file
### Backend

#### 1. Terraform Core
Terraform’s core (also known as Terraform CLI) is built on a statically-compiled binary that’s developed using the Go programming language.
Users run commands such as
``` terraform init ``` :- Use to initialize terrform working directories and you are ready to run other commands.
``` terraform referesh ```:- Query infrastructure provider to get current state of the infrastructure.
``` terraform plane ```:- Create execution plane.
``` terraform apply ```:- Execute plane and create resources.
``` terraform destroy ```:- destroy the resources.

#### 2. Configuration Files
Terraform configuration files, usually named *.tf, define the desired state of the infrastructure.
These files describe the resources and their configurations (e.g., virtual machines, networks, storage) using HashiCorp Configuration Language (HCL) or JSON format.

#### 3. Providers
Terraform interacts with different infrastructure providers (e.g., AWS, Azure, Google Cloud Platform) through provider plugins.
Each provider plugin implements the Terraform Provider Protocol, which defines a standard interface for managing resources.

#### 4. State file
It is a JSON file that stores information about the resources that Terraform manages, as well as their current state and dependencies.
Terraform maintains a state file (terraform.tfstate) that keeps track of the current state of managed infrastructure resources.
#### 5. Backend
The backend in Terraform defines where the state file is stored and managed.
Terraform supports various backend types such as local, remote (e.g., AWS S3, Azure Blob Storage), and enhanced remote backends like Terraform Cloud or Terraform Enterprise
