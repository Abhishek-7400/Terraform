# Taking variable from user
```
variable variable_name {}
```
## output
```
var.variable_name
  Enter a value:
```
## example1 
```
variable username {}
output myname{
    value = var.username
}
```
### ouput
```
var.username
  Enter a value: Abhishek

Changes to Outputs:
  + myname = "Abhishek"
```
# Adding variable with string ``` '${var.varable_name)' ```
## example
```
variable username {}
output myname{
    value = "hi my name is '${var.varable_name)'"
}
```
### ouput
```
var.username
  Enter a value: Abhishek
  
Changes to Outputs:
  + myname = "hi my name is 'Abhishek' "
```
