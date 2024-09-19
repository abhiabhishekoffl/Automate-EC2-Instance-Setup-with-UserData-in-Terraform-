# Automate-EC2-Instance-Setup-with-UserData-in-Terraform-
To automate the setup of an EC2 instance using UserData in Terraform


🛠️ What is UserData?
UserData is a feature in AWS EC2 that allows you to run scripts or commands automatically when an instance starts. It’s perfect for automating setup tasks like installing software or configuring settings.


💻 Why Use Terraform?
Terraform makes managing infrastructure simple and scalable. By adding a UserData script to your EC2 resource, you can launch instances that are pre-configured and ready to go!


💡 How to Do It?

• Define your EC2 instance in Terraform.

• Add a UserData script block to specify your setup commands.

• Apply the Terraform configuration to launch and configure your EC2 instance automatically.


💡 Pro Tip: Automating EC2 setups reduces manual work and ensures consistency across environments!

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Optionally


⁕ The count Object :- In blocks where count is set, an additional count object is available in expressions, so you can modify the configuration of each instance. This object has one attribute:

» count.index — The distinct index number (starting with 0) corresponding to this instance.


resource "aws_instance" "web" {

    ami           = "ami-0182f373e66f89c85"
  
    instance_type = "t2.micro"
  
    security_groups = [aws_security_group.TF_SG.name]
  
    key_name = "TF_key"

  
    count =50
  
    tags = {
  
      Name = "Instance ${count.index}"
    
    }
  
}

