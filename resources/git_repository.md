# Created Public Git repo using Terraform.
```
provider "github" {
    token = ""
}

resource "github_repository" "terraform-github-repo" {
  name        = "First-terraform-githu-repo"
  description = "My first github repo using terraform"

  visibility = "public"

  auto_init = true
}
```
