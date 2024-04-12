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
variable age {}
output my_details{
    value = " my name is '${var.username}' and my age is '${var.age}' "
}
```
### ouput
```
var.age
  Enter a value: 23
var.username
  Enter a value: Abhishek
Changes to Outputs:
  + my_details = " my name is 'Abhishek' and my age is '23' "
```
# We can give variable value from command line (-var "variablename=value").
## it will not ask user input and directly print the value.
### example
```
variable username {}
variable age {}
output mydetails{
    value = "hi my name is '${var.varable_name)and my age is '${var.age' "
}
```
on command line ``` terraform plan -var "username=Rajubhai" -var "age=23" ```

#### output
```
Changes to Outputs:
  + my_details = " my name is 'Abhishek' and my age is '23' "
```
# How to set default value to Variable
It will not asked to define the value of variable from input.
## Example
```
variable username {
    default="ram"
}
variable age {
    default=23
}
output my_details{
    value = " my name is '${var.username}' and my age is '${var.age}' "
}
```
Directly run the command ``` terraform plan ```
### Output
```
Changes to Outputs:
  + my_details = " my name is 'ram' and my age is '23' "
```
