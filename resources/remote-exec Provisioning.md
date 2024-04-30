# The remote-exec provisioner in Terraform is used to execute commands on a remote resource after it has been created. This provisioner is commonly used for tasks such as software installation, configuration, or any other actions that need to be performed on the remote resource.
## Example
```
resource "aws_instance" "example" {
  ami           = "ami-12345678"
  instance_type = "t2.micro"
  key_name      = "example-key"

  connection {
    type        = "ssh"
    user        = "ec2-user"
    private_key = file("/path/to/private/key.pem")
    host        = self.public_ip
  }

  provisioner "remote-exec" {
    inline = [
      "sudo yum update -y",
      "sudo yum install -y nginx",
      "echo 'Hello, world!' | sudo tee /usr/share/nginx/html/index.html",
      "sudo systemctl start nginx"
    ]
  }
}
```
# inline :
## This is a list of command strings. The provisioner uses a default shell unless you specify a shell as the first command (eg., #!/bin/bash). You cannot provide this with script or scripts.
# script :
## This is a path (relative or absolute) to a local script that will be copied to the remote resource and then executed. This cannot be provided with inline
