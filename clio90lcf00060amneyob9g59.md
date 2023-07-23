---
title: "Day 4 of #TerraWeek - Terraform State Management"
datePublished: Fri Jun 09 2023 07:31:00 GMT+0000 (Coordinated Universal Time)
cuid: clio90lcf00060amneyob9g59
slug: day-4-of-terraweek-terraform-state-management
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1686290316690/79606743-9d29-4689-ae74-ab76165c0e99.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1686295850659/b0470697-3dc0-400c-9763-10b531d366be.png
tags: devops, terraform, iac, aws-automation

---

## **• Introduction**

In this informative blog post, we delve into the crucial topic of Terraform state management. Explore the significance of understanding Terraform state and learn about the options for storing state files, including the advantages and considerations of local versus remote storage. Discover the various remote state management solutions available to optimize your Terraform workflows.

## **•** Understanding Terraform State

Terraform state refers to the record of the current state of your infrastructure managed by Terraform. It stores information about the resources provisioned, their configurations, and their dependencies. The state file is crucial for Terraform to track and manage infrastructure changes accurately.

The importance of Terraform state in managing infrastructure lies in several key aspects:

**Tracking Resource State**: Terraform state allows you to keep track of the current state of your provisioned resources. It enables Terraform to determine whether changes are needed, what changes are required, and which resources should be updated, created, or destroyed.

**Dependency Management**: Terraform uses the state to understand the dependencies between resources. It ensures that resources are provisioned in the correct order, taking into account dependencies specified in the configuration. This helps maintain a consistent and reliable infrastructure.

**Stateful Attributes**: Terraform state stores attribute values of resources. This information is vital for subsequent resource management, as it provides the necessary input for making informed decisions during updates or changes to the infrastructure.

**Concurrency and Collaboration**: Terraform state helps facilitate collaboration among team members working on the same infrastructure. It enables concurrent modifications to different resources while maintaining consistency across the infrastructure state.

**State Locking**: Terraform state supports locking mechanisms to prevent concurrent modifications and conflicts. This ensures that only one user or process can make changes to the state at a given time, reducing the risk of data corruption or inconsistent infrastructure changes.

## **•** Understand different methods of storing state file

There are various methods available for storing Terraform state files, each with its advantages and considerations. Here are some commonly used methods:

**Local Storage**:

* State files are stored on the machine where Terraform is executed.
    
* Simple and straightforward setup.
    
* Suitable for individual developers or small teams working on simple projects.
    
* Lacks collaboration features and remote accessibility.
    
* May lead to data loss if the local machine is compromised or experiences failures.
    

**Remote Storage**:

* State files are stored in a remote location, such as Amazon S3, Azure Blob Storage, or a file-based backend like Consul or etcd or terraform cloud.
    
* Enables collaboration and sharing of state files among team members.
    
* Provides versioning, access control, and history tracking for better management.
    
* Supports remote accessibility and easy integration with other tools.
    
* Offers enhanced security and durability compared to local storage.
    
* Suitable for team-based or production environments with multiple developers.
    

## **•** Remote state management using AWS S3 & Dynamo DB

Remote state management using AWS S3 and DynamoDB is a popular approach in Terraform. Here's how it works:

**AWS S3**: Amazon Simple Storage Service (S3) is used as the storage backend for storing the Terraform state file. S3 provides durable and scalable object storage. Each Terraform project typically has its own S3 bucket dedicated to storing state files.

**DynamoDB**: Amazon DynamoDB is a NoSQL database service used to store the state lock information. Terraform uses DynamoDB to acquire and manage locks to prevent concurrent modifications to the state.

To establish the AWS provider in Terraform, create a file named "[terraform.tf](http://terraform.tf)" that contains the necessary configuration for provisioning resources using Terraform with AWS.

```plaintext
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "4.66.1"
    }
  }
}
```

Now, execute "**terraform init"** command that initializes a Terraform working directory. It downloads the necessary provider plugins, sets up the backend configuration, and prepares the environment for Terraform to manage the infrastructure.

To instruct Terraform to create AWS resources in a specific region, create a file named "[provider.tf](http://provider.tf)" that specifies the AWS provider configuration. This file will define the desired region where the resources should be provisioned.

```plaintext
provider "aws" {
    region = "us-east-1"
}
```

Next, create a file named "[resource.tf](http://resource.tf)" to define AWS backend resources for storing the Terraform state file and lock information. Within this file, specify the creation of an S3 bucket to store the state file and a DynamoDB table to store the locking information.

```plaintext
# backend resources
resource "aws_s3_bucket" "my_s3_bucket" {
    bucket = "terraweek-day4-state-bucket"
}

resource "aws_dynamodb_table" "my_dynamodb_table" {
    name = "terraweek_day4_state_table"
    billing_mode = "PAY_PER_REQUEST"
    hash_key = "LockID"
    attribute {
        name = "LockID"
        type = "S"
    }
}
```

Executing "**terraform plan**" generates an execution plan by analyzing the Terraform configuration and current state. It identifies the required modifications to reach the desired infrastructure state, providing a preview without applying changes. Subsequently, running "**terraform apply**" applies the specified configuration changes, requiring confirmation. Resources are provisioned or modified accordingly, updating the state file to reflect the current infrastructure state.

AWS S3, a bucket is created according to the instructions specified in the file.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686293821905/ac588c71-0352-476b-8547-7ce7839e415b.png align="center")

Similarly, in DynamoDB, a table is created based on the provided instructions in the file.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686293893510/f6b6ae85-48ee-4f70-86ce-4b49e70ca7f6.png align="center")

We are currently setting up the backend configuration. To utilize this backend, create a directory and within that directory, Create a file called "[terraform.tf](http://terraform.tf)" where you will specify the required AWS provider configuration. Additionally, include a backend block in the file, providing the name of the S3 bucket and DynamoDB table for storing Terraform state, as well as the access key, region, and other necessary details.

```plaintext
terraform {

required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "4.66.1"
    }
  }

backend "s3" {
        bucket = "terraweek-day4-state-bucket"
        key = "terraform.tfstate"
        region = "us-east-1"
        dynamodb_table = "terraweek_day4_state_table"
}
}
```

To verify if our state file is successfully stored in remote storage on AWS S3, let's create a file named "[resource.tf](http://resource.tf)". In this file, include the necessary commands to create an EC2 instance and specify the region where the resource should be provisioned.

```plaintext
provider "aws" {
    region = "us-east-1"
}

resource "aws_instance" "aws_ec2_test" {

        ami = "ami-053b0d53c279acc90"
        instance_type = "t2.micro"
        tags = {
        Name = "terraform-instance"
  }
}
```

Execute "**terraform plan**" command to generate an execution plan for desired infrastructure changes without applying them. "**terraform apply**" applies the changes, provisioning or modifying resources and updating the state file.

Our instance is creating successfully and the state file is now stored in the S3 bucket, and it is visible and accessible for further reference and management.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686295013257/0913c924-7a8a-4b93-9379-dca46e165682.png align="center")

Furthermore, a lock ID is generated in DynamoDB, ensuring proper synchronization and coordination during the management of resources.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686295436310/97c96da4-aad2-45ec-8a26-ddbc769f749d.png align="center")

## **•** **Conclusion**

In conclusion, understanding Terraform state and the different methods of storing state files is vital for efficient infrastructure management. By leveraging remote state management using AWS S3 and DynamoDB, you can ensure secure storage, collaborative workflows, and a consistent infrastructure state, enhancing the overall effectiveness of your Terraform deployments.

*If you found this post valuable, I would greatly appreciate your support by following and liking it with a* ❤️. *Thank you for taking the time to read and engage!*

**~ Nishit Rajani**