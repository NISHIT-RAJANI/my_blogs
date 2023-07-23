---
title: "Day 2 of #TerraWeek - Terraform Configuration Language (HCL)"
datePublished: Tue Jun 06 2023 17:25:19 GMT+0000 (Coordinated Universal Time)
cuid: clikjxc4y000309l7bnzc7hvr
slug: day-2-of-terraweek-terraform-configuration-language-hcl
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1686059574972/6a67f226-d902-4a64-a679-eaec0551a386.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1686072264618/f35f7757-0e97-4942-aa2a-1c955bbf7934.png
tags: automation, devops, terraform, iac

---

### **• What is HCL?**

HCL (HashiCorp Configuration Language) is the primary language used for writing configuration files in Terraform. Terraform is an infrastructure provisioning and management tool developed by HashiCorp.

In the context of Terraform, HCL is used to define and configure the infrastructure resources, data sources, providers, variables, and other elements required to manage your infrastructure as code.

### • **HCL Syntax**

HCL (HashiCorp Configuration Language) syntax is used to write infrastructure as code. Here's an overview of the HCL syntax specifically in the context of Terraform:

◾ Blocks:

» Blocks define resources, data sources, providers, and other constructs in Terraform.

» Blocks start with the block type followed by the resource or data source name.

» The opening brace "{" must be placed on the same line as the block declaration, and the closing brace "}" must be on a separate line.

» Example: `resource "aws_instance" "example" { ... }`

◾ Attributes:

» Attributes are key-value pairs within a block and define the configuration for a resource or data source.

» The key and value are separated by an equal sign "=".

» Attributes can also be nested within a block using blocks within blocks.

» Example: `key_name = "my-key"`

◾ Comments:

» Single-line comments start with the "#" character.

» Multi-line comments start with "/*" and end with "*/".

### • **Variables, Data types, and Operators in HCL**

In HCL (HashiCorp Configuration Language), variables are used to parameterize and customize your configurations. They allow you to define values that can be passed into your configuration at runtime. Here's how variables are declared and used in HCL:

**Variable declaration:**

To declare a variable, create a [**variable.tf**](http://variable.tf) file in that define variable using the `variable` block.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686069786501/14784393-14fc-46b1-a973-5a1debaf8cb6.png align="center")

**Variable usage:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686070211395/4b13a84d-36f5-47a2-88f2-85b592b03f40.png align="center")

In the given code snippet, two Terraform resources are defined:

`resource "local_file" "devops"`: This resource represents a local file that will be managed by Terraform. It has a unique identifier `devops` within the `local_file` resource type.

`filename = "/root/terraform/terraform-local/automate-file.txt"`: This line specifies the name or path of the file that Terraform will create or manage. In this case, the file name is set to `automate-file.txt`, and it is located at `"/root/terraform/terraform-local/"`.

`content = "It's Day 2 Terraweek challenge"`: This line sets the content of the file. The file will contain the text `"It's Day 2 Terraweek challenge"`.

`resource "local_file" "devops_var"`: This resource is similar to the first one, but it utilizes variables to set the `filename` and `content` values dynamically.

`filename = var.filename`: This line assigns the value of the variable `filename` to the `filename` attribute of the resource. This means that the actual file name/path will be determined by the value of the `filename` variable defined in the variable.tf file.

`content = var.content`: This line assigns the value of the variable `content` to the `content` attribute of the resource. The content of the file will be determined by the value of the `content` variable defined in the variable.tf file.

**Data types:**

In HashiCorp Configuration Language (HCL), the following data types are commonly used:

String: Represents a sequence of characters. Strings are typically enclosed in double quotes (" ") or single quotes (' '). Example: "Hello, World!"

Number: Represents numeric values, including integers and floating-point numbers. Example: 42, 3.14

Boolean: Represents a logical value that can be either true or false.

List: Represents an ordered collection of values. Lists are defined using square brackets (\[\]) and can contain elements of any data type. Example: \[1, 2, 3\], \["apple", "banana", "orange"\]

Map: Represents a collection of key-value pairs. Maps are defined using curly braces (`{}`) and can have string keys and values of any data type. Example: { "name": "Raj", "age": 16, "city": "Dubai" }

**Operators:**  
In HashiCorp Configuration Language (HCL), there are various operators available for performing operations and comparisons. Here are some commonly used operators in HCL:

* **+**, **\-**, **\***, **/**: arithmetic operators for addition, subtraction, multiplication, and division
    
* **&&**, **||**, **!**: logical operators for AND, OR, and NOT operations
    
* **\\==**, **!=**, **&lt;**, **\&gt;**, **&lt;=**, **\&gt;=**: comparison operators for equality and inequality, and less than or greater than comparisons.
    

### • **Writing Terraform configurations using HCL syntax**

Create Docker container using Terraform. So, here first of all create one **main.tf** file

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686071437703/387c73a3-29d7-42a8-b2e8-3d2b603359ce.png align="center")

The Terraform configuration declares the required Docker provider version, specifies the Docker image resource named "nginx\_image" with the image name "nginx" and sets "keep\_locally" to false. It also defines a Docker container resource named "nginx\_container" using the latest version of the "nginx\_image", with the container name "practice" and port mapping from internal 80 to external 80.

To execute main.tf file follow below commands:

`terraform init`: This command initializes a Terraform working directory. It downloads the necessary provider plugins, sets up the backend configuration, and prepares the environment for Terraform to manage the infrastructure.

`terraform plan`: This command creates an execution plan based on the Terraform configuration and any existing state. It determines what changes are needed to achieve the desired infrastructure state. It shows a preview of the changes that will be made without actually applying those changes.

`terraform apply`: This command applies the changes specified in the Terraform configuration to the infrastructure. It prompts for confirmation before proceeding. Once confirmed, it provisions or modifies the resources defined in the configuration and updates the state file to reflect the current state of the infrastructure.

Check the output as we can see in below image container is running and using public IP we can access nginx page.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686071921793/bdbec4f6-01f2-47b5-a67c-9d262f49f95c.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686071878605/994d46cd-ae2c-412f-9bb1-0a807a31c441.png align="center")

*If you found this post useful, please consider following and clicking the* ***♡*** *button to show your support.*

**Thank you** for taking the time to read!

~ Nishit Rajani