---
title: "Day 3 of #TerraWeek - Managing Resources"
datePublished: Wed Jun 07 2023 17:56:59 GMT+0000 (Coordinated Universal Time)
cuid: clim0hx0e00000ajp77iicrdk
slug: day-3-of-terraweek-managing-resources
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1686157767688/f30b20ef-aa20-4f83-9fb2-46612dd5480b.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1686160608871/63f68b28-0d7b-4709-b1ee-46cecf474c56.png
tags: automation, devops, terraform, infrastructure-as-code, iac

---

### **• Introduction**

In this article, we will delve into resource management with Terraform, examining resource types in AWS EC2 instances. We will explore their configurations, resource dependencies, provisioners, and lifecycle management to gain a comprehensive understanding of effective resource management using Terraform.

### **• Terraform with AWS**

Provisioning on AWS is quite easy with Terraform.

Prerequisites:

* **AWS CLI installation:**
    
    The AWS Command Line Interface (AWS CLI) is a unified tool to manage your AWS services. With just one tool to download and configure, you can control multiple AWS services from the command line and automate them through scripts.
    
* **AWS IAM user:**
    
    IAM (Identity Access Management) AWS Identity and Access Management (IAM) is a web service that helps you securely control access to AWS resources. You use IAM to control who is authenticated (signed in) and authorized (has permissions) to use resources.
    

To connect your AWS account and Terraform, you need the access keys and secret access keys exported to your machine.

`export AWS_ACCESS_KEY_ID=<access_key>`

`export AWS_SECRET_ACCESS_KEY=<secret_access_key>`

### **• AWS EC2 Instance Configuration**

```plaintext
provider "aws" {
  access_key = "<your-access-key>"
  secret_access_key = "<your-secret-access-key>"
  region = "<your-preferred-region>"
}

# Create an EC2 instance
resource "aws_instance" "my_ec2_instance" {
  count = 1
  ami = "<your-ami-id>"
  instance_type = "t2.micro"
  key_name = "<your-key-pair-name>"

# Define tags
  tags = {
    Name = "EC2-Instance"
  }
}

# Get the Public IPs for the provisioned instances

output "instance_pub_ip" {
value = aws_instance.aws_ec2_test[*].public_ip
}
```

The provided HCL file demonstrates the configuration for an AWS provider and the creation of an EC2 instance:

» The AWS provider block sets up the connection to AWS using your access key, secret access key, and preferred region.

» The resource block `aws_instance` defines the creation of an EC2 instance. You need to specify the AMI ID (Amazon Machine Image) for the instance, the desired instance type (e.g., "t2.micro"), and the name of the key pair for SSH access.

» The tags block is used to assign metadata to the EC2 instance. In this case, a single tag "Name" is set with the value "EC2-Instance".

» To use this configuration, replace the placeholder values (`<your-access-key>`, `<your-secret-access-key>`, `<your-preferred-region>`, `<your-ami-id>`, and `<your-key-pair-name>`) with your actual AWS credentials, region, desired AMI ID, and key pair name.

By running Terraform commands such as `terraform init`, `terraform plan`, and `terraform apply`, you can initialize the working directory, preview the changes, and apply the configuration to create the specified AWS EC2 instance with the defined settings and tags.

### **• Resource Dependencies**

In Terraform, resource dependencies determine the desired sequence for creating, updating, or destroying resources. Terraform automatically identifies dependencies based on configuration, but you can also explicitly define them using the `depends_on` argument. For instance, you can establish a dependency between an AWS EC2 instance and a security group using the `depends_on` argument.

```plaintext
resource "aws_security_group" "example" {
  name = "example"
}

resource "aws_instance" "EC2-Instance" {
  ami           = "ami-053b0d53c279acc90"
  instance_type = "t2.micro"

  vpc_security_group_ids = ["${aws_security_group.example.id}"]

  depends_on = [aws_security_group.example]
}
```

### **• Provisioners**

In Terraform, provisioners are used to performing actions or execute scripts on the resource instances during their creation or destruction. Provisioners enable the configuration of additional software, installation of packages, running scripts, and other tasks that are necessary for setting up or configuring resources.

```plaintext
resource "aws_instance" "EC2-Instance" {
  ami           = "ami-053b0d53c279acc90"
  instance_type = "t2.micro"

  provisioner "remote-exec" {
    inline = [
      "echo 'Hello, World!'",
      "apt-get update",
      "apt-get install -y apache2",
    ]
  }
}
```

In this example, a provisioner of the type `remote-exec` is used to execute inline commands on the created AWS EC2 instance. The provided inline commands perform actions such as echoing a message and installing the Apache web server.

### **• Lifecycle Management**

In Terraform, lifecycle management refers to controlling the lifecycle behavior of resources. It allows you to define how resources should be created, updated, or destroyed based on specific conditions or requirements.

Terraform provides several lifecycle management settings that can be used within a resource block:

**Create Before Destroy**: This setting, `create_before_destroy`, specifies whether to create a new resource before destroying the existing one. It can be useful when transitioning from one resource version to another to avoid downtime.

**Prevent Destroy**: By using the `prevent_destroy` setting, you can prevent a resource from being destroyed by Terraform. This is helpful when you want to protect critical resources from accidental deletion.

**Ignore Changes**: The `ignore_changes` setting allows you to ignore specific attribute changes during updates. This ensures that certain attributes of a resource are not updated, preventing unintended modifications.

**Timeouts**: Timeout settings, such as `create_timeout` and `delete_timeout`, define the maximum time Terraform should wait for a resource to be created or destroyed before timing out. These settings are useful when working with resources that have longer provisioning or deletion times.

Here's an example showcasing the use of lifecycle management settings:

```plaintext
resource "aws_instance" "EC2-Instance" {
  ami           = "ami-053b0d53c279acc90"
  instance_type = "t2.micro"

  lifecycle {
    create_before_destroy = true
    prevent_destroy       = true
    ignore_changes        = [tags]
    create_timeout        = "10m"
    delete_timeout        = "5m"
  }
}
```

In this example, the `aws_instance` resource has various lifecycle management settings specified within the `lifecycle` block. It will create a new instance before destroying the existing one, prevent accidental destruction, ignore changes to the `tags` attribute during updates, and set timeouts for creation and deletion operations.

By utilizing these lifecycle management settings, you can control the behavior of resource creation, updates, and destruction in Terraform, ensuring the desired management and protection of your infrastructure.

### **• Conclusion**

In this article, we have examined resource management with Terraform, specifically delving into resource types like AWS EC2 instances. Additionally, we have explored resource dependencies, provisioners, and lifecycle management. Acquiring knowledge in these areas will empower you to efficiently manage your cloud infrastructure using Terraform.

*If you found value in this post, I kindly request you to consider following and clicking the* ❤️ *button as a gesture of support.*

Thank you for investing your time in reading!

~ **Nishit Rajani**