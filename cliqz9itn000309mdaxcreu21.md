---
title: "Day 5 of #TerraWeek - Terraform Modules"
datePublished: Sun Jun 11 2023 05:21:19 GMT+0000 (Coordinated Universal Time)
cuid: cliqz9itn000309mdaxcreu21
slug: day-5-of-terraweek-terraform-modules
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1686459015342/bf12b034-38f6-44ff-81be-170dede27cad.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1686460813312/653ccd48-69b5-493b-bc41-aeac269b1ce6.png
tags: automation, terraform, iac

---

## **• Introduction**

In this blog post, we dive deep into understanding the fundamentals of modules, explore their numerous benefits, learn how to create and utilize them effectively, discover the art of module composition, and gain insights into module versioning.

## **• Understanding Terraform Modules**

Terraform modules are reusable components that encapsulate infrastructure code. They allow you to define sets of resources, variables, and outputs, enabling the creation of scalable and composable infrastructure configurations. Modules abstract complex components or entire infrastructure stacks, accept input variables for customization and provide output values for resource information. They promote code reuse and maintainability by enabling module composition and integration into your Terraform code. With a public module registry, you can easily share and discover pre-built modules, making it a powerful tool for organizing and managing infrastructure deployments.

## **• Benefits of Using Terraform Modules**

Using Terraform modules offers the following benefits:

**Reusability**: Modules encapsulate infrastructure resources and configurations, allowing for easy sharing and reuse of infrastructure code across projects.

**Modularity**: Modules abstract away complex infrastructure details, providing a simplified and standardized interface for provisioning resources. This promotes code organization and makes infrastructure configurations more manageable.

**Collaboration**: Multiple teams can work concurrently on different modules, which can then be combined to create complex infrastructure setups. This promotes collaboration and code sharing, making it easier for teams to work together on infrastructure projects.

**Maintainability**: Changes made to a module can be propagated to all instances where it is used, ensuring consistency and easier maintenance. Modules enable the adoption of best practices, policies, and standards, which can be enforced across deployments.

**Scalability and flexibility**: Modules allow for the creation of infrastructure patterns that can be easily replicated and scaled up or down as needed. This promotes flexibility in adapting to changing requirements and simplifies the process of scaling infrastructure.

**Version control**: Modules can be versioned separately, enabling the use of specific module versions for different deployments. This ensures that infrastructure can be reproduced reliably and mitigates potential issues caused by version conflicts.

**Documentation and self-contained configuration**: Modules provide a clear and concise way to document infrastructure resources and their dependencies. The encapsulated nature of modules makes it easier to understand and maintain the overall infrastructure configuration.

By leveraging Terraform modules, organizations can achieve code reusability, modularity, collaboration, maintainability, scalability, version control, and streamlined documentation for their infrastructure provisioning processes.

## **• Creating and Using Terraform Modules**

**Module Creation:**

» Create a directory named "my\_module" for the module.

» In the "my\_module" directory, create a [main.tf](http://main.tf) file with the following content:

```plaintext
resource "aws_instance" "example" {
  ami           = var.ami_id
  instance_type = var.instance_type
}
```

» Create a [variables.tf](http://variables.tf) file in the same directory with the following content:

```plaintext
variable "ami_id" {
  description = "AMI ID for the EC2 instance"
}

variable "instance_type" {
  description = "Instance type for the EC2 instance"
}
```

» Create an [outputs.tf](http://outputs.tf) file with the following content:

```plaintext
output "instance_id" {
  value = aws_instance.example.id
}
```

**Module Usage:**

» Create a new Terraform configuration file (e.g., [main.tf](http://main.tf)) in a separate directory.

» Declare the module in the [main.tf](http://main.tf) file:

```plaintext
module "example" {
  source     = "./my_module"
  ami_id     = "ami-053b0d53c279acc90"
  instance_type = "t2.micro"
}
```

» Access the outputs of the module to retrieve information:

```plaintext
output "module_instance_id" {
  value = module.example.instance_id
}
```

In this example, we created a Terraform module for an AWS EC2 instance. The module accepts input variables for the AMI ID and instance type. The [main.tf](http://main.tf) file in the module defines the AWS instance resource. The [outputs.tf](http://outputs.tf) file exposes the instance ID as an output. In the [main.tf](http://main.tf) file of the module usage directory, we declare the module and provide the required input variables. Finally, we access the output value of the module to retrieve the instance ID.

## **• Module Versioning**

Module versioning in Terraform allows for the management and tracking of different versions of a module, enabling controlled updates and ensuring consistency across infrastructure deployments. Here's an example of how module versioning works with AWS:

Let's say you have a Terraform module that provisions an AWS EC2 instance. Initially, you publish the module with version 1.0.0. You can specify this version in your root Terraform configuration file using the "source" attribute, like this:

```plaintext
module "ec2_instance" {
  source  = "your-module-registry/your-module/aws"
  version = "1.0.0"
  // Other configuration options...
}
```

Now, let's assume you make some updates to the module, adding new features or fixing bugs, and you publish a new version, 1.1.0. To use this updated version, you can simply update the module version in your configuration file:

```plaintext
module "ec2_instance" {
  source  = "your-module-registry/your-module/aws"
  version = "1.1.0"
  // Other configuration options...
}
```

By explicitly specifying the version, you ensure that the same module version is used consistently across different deployments, providing predictability and allowing you to control when and how updates are applied to your infrastructure.

## **• Conclusion**

In summary, Terraform modules offer a powerful solution for managing infrastructure as code. By understanding their principles, users can reap the benefits of code reuse, collaboration, and faster deployment. Creating and using modules involves defining variables and configuring resources, while module composition allows for building complex infrastructures. Module versioning ensures stability and consistency. Ultimately, Terraform modules streamline infrastructure management and promote scalability, efficiency, and maintainability.

*If you found this post valuable, I would greatly appreciate your support by following and liking it with a* ❤️. *Thank you for taking the time to read and engage!*

**~ Nishit Rajani**