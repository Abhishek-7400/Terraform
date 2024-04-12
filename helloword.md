# Printng output in Terraform
## Output is simillar to print() 
```
block label1 lable2 {
identifire = expression
}
```
# Example
```
output hello{
value = "hello word"
}

```
### run command terraform plan
## output
```
Changes to Outputs:
  + hello = "hello Word"
```

