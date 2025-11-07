# 🚀 Terraform AWS EC2 Instance Module

This Terraform module provisions an **AWS EC2 instance** with customizable parameters such as AMI ID, instance type, and security group IDs. It’s designed for DevOps automation labs and real-time infrastructure provisioning in AWS.

---

## 🧩 Features
- Create lightweight EC2 instances using modular Terraform code  
- Supports parameterized AMI IDs and instance types  
- Attaches existing Security Groups  
- Outputs instance details for downstream configurations  

---

## ⚙️ Usage

``hcl
module "ec2_instance" {
  source = "github.com/prashanthteja139/terraform-aws-ec2-instance-module"

  ami_id         = "ami-09c813fb71547fc4f"
  instance_type  = "t3.micro"
  sg_ids         = ["sg-0a1234567890abcd1"]
  tags = {
    Name = "devops-ec2"
    Environment = "dev"
  }
}
📥 Inputs
Name	Description	Type	Default	Required
ami_id	AMI ID of the EC2 instance	string	"ami-09c813fb71547fc4f"	No
instance_type	Type of EC2 instance	string	"t3.micro"	No
sg_ids	List of Security Group IDs	list(string)	null	✅ Yes
tags	Tags to associate with the instance	map(string)	{}	✅ Yes

📤 Outputs
Name	Description
public_ip	Public IP address of the instance
private_ip	Private IP address of the instance
instance_id	Instance ID of the created EC2 instance

🧠 Best Practices
Use Terraform Cloud or S3 backend for state management

Follow naming conventions for tag consistency

Use terraform fmt and terraform validate before commits

Integrate this module into your CI/CD workflow using GitHub Actions

🧑‍💻 Author
Prashanth Teja
DevOps & DevSecOps Enthusiast | Cloud Automation Learner
