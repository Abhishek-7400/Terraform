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



