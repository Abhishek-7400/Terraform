# to Check provider which one using
```
terraform providers
```
# to applies a standard formatting to your .tf files, adjusting indentation, spacing, and other formatting rules.
```
terraform fmt
```

# to initiate Plugins
```
terraform init
```

# to validate the syntax of Terraform configuration files
```
terrform validate
```

# to plan
```
terraform Plan
```

# to apply
```
terraform apply
```
## or
```
terrform apply --auto-approve
```

# to destroy
```
terraform destroy
```
## or
```
terrform destroy --auto-approve
```

# to destory particular resource
```
terraform destroy --target resource_type.resource_name
```

# to opens an interactive console where you can evaluate expressions and functions directly within the context of your Terraform configuration
```
terraform console
```

# When a resource is tainted, Terraform will consider it as needing to be destroyed and recreated on the next apply, even if there are no changes to its configuration.
```
terraform taint [options] RESOURCE_TYPE.RESOURCE_NAME
```
