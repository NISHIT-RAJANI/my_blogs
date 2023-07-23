---
title: "Day 6 of #TerraWeek - Terraform Providers"
datePublished: Mon Jun 12 2023 12:22:46 GMT+0000 (Coordinated Universal Time)
cuid: clistrdf100090alcga5ohd3j
slug: day-6-of-terraweek-terraform-providers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1686568376309/402307c5-026b-414d-be79-f9806c9704f8.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1686572553663/87b963f2-9113-4c35-989a-2d238a14502e.png
tags: aws, automation, terraform, iac, cloudautomation

---

## **• Introduction**

In this blog, we will explore the concept of Terraform providers, compare major cloud providers such as AWS, Azure, and Google Cloud, delve into provider configuration and authentication, and provide insights on working with each provider. Get ready to elevate your cloud infrastructure management with Terraform.

## **• Understanding Terraform Providers**

Terraform providers serve as plugins that facilitate communication between Terraform and diverse cloud platforms, infrastructure services, and APIs. Providers play a pivotal role by understanding API interactions and exposing manageable resources within Terraform. Renowned providers encompass AWS, Azure, Google Cloud, among others.

To utilize a provider, it is necessary to declare it within your Terraform configuration file, typically denoted by a .tf extension. Below is an illustration of declaring the AWS provider:

```plaintext
provider "aws" {
  region = "us-east-1"
}
```

## **• Comparing Providers**

Terraform providers are plugins that enable Terraform to establish connections with different cloud platforms and infrastructure services. These providers have the capability to comprehend API interactions and make accessible the resources that can be managed through Terraform. Several well-known Terraform providers include:

**AWS**: [Terraform AWS provider](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)

**Azure**: [Terraform AzureRM Provider](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs)

**Google Cloud**: [Terraform Google Cloud Provider](https://registry.terraform.io/providers/hashicorp/google/latest/docs)

Every provider offers a distinct range of supported resources and functionalities. To conduct a comparison, refer to the official documentation of each provider and explore the available resources and data sources they provide. This will allow you to assess the capabilities and features offered by each provider in order to make informed decisions based on your specific requirements.

## **• Provider Configuration and Authentication**

Every provider has its unique configuration options used for authentication and interaction with the associated cloud platform or service. These options encompass API keys, access tokens, or other credentials necessary for authentication purposes.

For instance, the AWS provider necessitates an access key and secret key for authentication. You can provide these credentials through various means, including environment variables, a shared credentials file, or directly within the provider configuration block:

To configure authentication for each provider on your local machine, adhere to the following general procedures for widely-used cloud providers:

**AWS (Amazon Web Services)**

» Create an IAM user in the AWS Management Console.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686570276670/3d70bf1e-7bea-4c26-a029-e5bd37c7f036.png align="center")

» Grant the necessary permissions to the IAM user according to your specific needs.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686570370196/bbf1d327-e4b2-477a-a261-a7e1d0c5260d.png align="center")

» Once the user is successfully created, navigate to the security credentials section within the user's settings. and click on Create access key.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686570548846/806360fd-1a92-4ab9-b92e-32b14d955584.png align="center")

» Select CLI and click on next.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686570597305/dc721450-711e-4744-9ff6-4d54dec3b17f.png align="center")

» Once access keys and secrets are generated, you can copy them from the designated location and configure them locally by utilizing the `aws configure` command.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686570739203/c0c391d4-a085-4012-9592-e66508c21f8f.png align="center")

» Configure the AWS Command Line Interface (CLI) or establish environment variables (AWS\_ACCESS\_KEY\_ID and AWS\_SECRET\_ACCESS\_KEY) with the generated credentials.

**Azure (Microsoft Azure)**

» Create an Azure Active Directory (AAD) application registration.

» Retrieve the Client ID, Client Secret, and Tenant ID associated with the application registration.

» Assign the required roles and permissions to the application registration.

» Configure the Azure CLI or establish environment variables (AZURE\_CLIENT\_ID, AZURE\_CLIENT\_SECRET, and AZURE\_TENANT\_ID) with the obtained credentials.

**GCP (Google Cloud Platform)**

» Create a GCP service account and generate a key file (JSON format).

» Assign the necessary roles and permissions to the service account.

» Set the environment variable GOOGLE\_APPLICATION\_CREDENTIALS to the file path of the generated key file.

## **• Working with AWS Provider**

To begin managing resources within your AWS account using Terraform, you can initiate the process by declaring the AWS provider within your Terraform configuration file.

```plaintext
provider "aws" {
  region = "us-east-1"
}
```

Now, we will proceed to create an Amazon S3 bucket utilizing the AWS provider.

```plaintext
resource "aws_s3_bucket" "terraweek-bucket" {
  bucket = "terraweek-demo-bucket"
  acl    = "private"
}
```

Once the resource is defined, execute the "terraform init" command to initialize your Terraform working directory and download the necessary provider plugins. Subsequently, run the "terraform apply" command to create the S3 bucket as specified.

## **• Working with Azure Provider**

To initiate the management of resources within your Azure account using Terraform, you can begin by declaring the Azure provider within your Terraform configuration file.

```plaintext
provider "azurerm" {
  features {}
}
```

Now, we will proceed to create a resource group utilizing the Azure provider.

```plaintext
resource "azurerm_resource_group" "example" {
  name     = "my-resource-group"
  location = "West US"
}
```

Once the resource is defined, execute the "terraform init" command followed by "terraform apply" to create the resource group as specified.

## **• Working with Google Cloud Provider**

To begin managing resources within your Google Cloud account using Terraform, you can initiate the process by declaring the Google Cloud provider within your Terraform configuration file.

```plaintext
provider "google" {
  project = "my-demo-project"
  region  = "us-central1"
  zone    = "us-central1-b"
}
```

Now, we will proceed to create a Google Cloud Storage bucket utilizing the Google Cloud provider.

```plaintext
resource "google_storage_bucket" "terraweek-bucket" {
  name     = "my-demo-bucket"
  location = "us-central1"
  storage_class = "STANDARD"
}
```

Once the resource is defined, execute the "terraform init" command followed by "terraform apply" to create the storage bucket.

## **• Conclusion**

In this blog, we explored the essential concepts of Terraform providers and their role in managing cloud resources. We compared popular providers like AWS, Azure, and Google Cloud, highlighting their unique features. Provider configuration and authentication were discussed, along with practical examples of working with AWS, Azure, and Google Cloud. By understanding Terraform providers, you now have the tools to effectively manage your cloud infrastructure and leverage the flexibility of Terraform for automating and scaling resources. Embrace Infrastructure as Code and unlock the full potential of Terraform providers for your cloud deployments.

*If you found this blog post informative and useful, I would sincerely appreciate your support by giving it a like* ❤️ *and following for more content. Your engagement means a lot to me, and I'm grateful for the time spent reading this post. Thank you!*

~ **Nishit Rajani**