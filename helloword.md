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
# Terraform run the all the file present in the same direction in alphabatical order of the file.
## if in folder 3 file are there the terraform run all three files.
