# Taking variable from user
```
variable username {}
```
## output
```
var.username
  Enter a value:
```
## example
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

