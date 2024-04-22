# String
```
variable username {
  type        = string
  description = "define username"
  default     = "dev"
}
```
# Number
```
variable age {
  type        = number
  description = "define age"
  default     = 23
}
```
# Boolean
```
variable enable_monitoring {
  type        = bool
  description = "Enable monitoring for the infrastructure"
  default     = true
}
```
# List
```
variable users {
  type        = list
  description = "A list of subnet IDs"
  default     = ["a","b","c"]
}
```
## Example
```
variable users {
  type = list
  default = ["a","b"]
}
output detali1{
  value = "my first user is ${var.users[0]}"
}
output detali2{
  value = "my second user is ${var.users[1]}"
}
```
### output
```
Changes to Outputs:
  + detali1 = "my first user is a"
  + detali2 = "my second user is b"
```

# Map (directory)
```
variable "tags" {
  type        = map(string)
  description = "A map of instance tags"
  default     = {
    Name        = "Abhishek"
    roll_no     = 23
    Project     = "Terraform"
  }
}
```
## example ( we use function lookup(map_name,key_value) to use the key from map )
```
variable map {
  type = map
  default = {
    gaurav=23
    abhishek=43
  }
}

variable name{
  type = string
}


output detali{
  value = "my name is ${var.name} and my age is ${lookup(var.map,"${var.name}")}" 
}
```
### output
```
var.name
  Enter a value: abhishek
Changes to Outputs:
  + detali = "my name is abhishek and my age is 43"
```

# Object
```
variable "instance_config" {
  type = object({
    ami_id   = string
    instance_type = string
    subnet_id = string
  })
  description = "Configuration for the instance"
  default = {
    ami_id        = "ami-123456"
    instance_type = "t2.micro"
    subnet_id     = "subnet-123456"
  }
}
```



