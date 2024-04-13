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
# If wanted to print somthing during Plan or Execution use output (got to Attributes Reference )

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
output full_reponame{
value = github_repository.terraform-github-repo.full_name
}
output rep_url{
value = github_repository.terraform-github-repo.html_url
}
```    
