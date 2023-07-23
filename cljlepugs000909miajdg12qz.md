---
title: "Simplify AWS Resource Tracking with the AWS Resource Tracker Script"
datePublished: Sun Jul 02 2023 12:27:00 GMT+0000 (Coordinated Universal Time)
cuid: cljlepugs000909miajdg12qz
slug: simplify-aws-resource-tracking-with-the-aws-resource-tracker-script
tags: aws, automation, shell-script

---

### **• Introduction**

Managing resources in Amazon Web Services (AWS) can be a complex task, especially when you have numerous S3 buckets, EC2 instances, Lambda functions, RDS instances, and IAM users to keep track of. Without a proper tracking system, it's easy to lose sight of your resources and their configurations. To simplify this process, we have developed the "AWS Resource Tracker" script. This script automates the listing of various AWS resources and saves the output in separate files, making it easier for administrators and developers to monitor and manage their AWS resources effectively.

### **• Overview of the Script**

The AWS Resource Tracker script is a bash script that utilizes the AWS Command Line Interface (CLI) and other AWS CLI tools like AWS CLI, jq, and awk. It provides a simple menu-driven interface that allows users to select the type of resource they want to track. Once the selection is made, the script retrieves the necessary information from the corresponding AWS service and saves it in a timestamped file.

### **• Script**

```plaintext
#!/bin/bash

Time=$(date "+%Y-%m-%d-%H-%M-%S")

# Function to save output to a file
function save_output {
    local data="$1"
    local file_name="$2"
    echo "$data" > "${Time}_${file_name}"
    echo "List of $3 saved to ${Time}_${file_name}"
}

# Function to list S3 buckets
function list_s3_buckets {
    local buckets=$(aws s3 ls | awk '{print $3}')
    save_output "$buckets" "s3_buckets.txt" "S3 buckets"
}

# Function to list EC2 instances
function list_ec2_instances {
    local instance_ids=$(aws ec2 describe-instances | jq -r '.Reservations[].Instances[].InstanceId')
    save_output "$instance_ids" "ec2_instances.txt" "EC2 instances"
}

# Function to list Lambda functions
function list_lambda_functions {
    local function_names=$(aws lambda list-functions | jq -r '.Functions[].FunctionName')
    save_output "$function_names" "lambda_functions.txt" "Lambda functions"
}

# Function to list RDS instances
function list_rds_instances {
    local rds_instances=$(aws rds describe-db-instances | jq -r '.DBInstances[].DBInstanceIdentifier')
    save_output "$rds_instances" "rds_instances.txt" "RDS instances"
}

# Function to list IAM users
function list_iam_users {
    local iam_users=$(aws iam list-users | jq -r '.Users[].UserName')
    save_output "$iam_users" "iam_users.txt" "IAM users"
}

# Function to display the menu and get user's choice
function display_menu {
    echo "Select the resource type you want to list:"
    echo "1. S3 Buckets"
    echo "2. EC2 Instances"
    echo "3. Lambda Functions"
    echo "4. RDS Instances"
    echo "5. IAM Users"
    echo "6. Exit"
    read -p "Enter your choice (1-6): " choice
}

# Execution
display_menu

while [ "$choice" != "6" ]; do
    case $choice in
        1) list_s3_buckets ;;
        2) list_ec2_instances ;;
        3) list_lambda_functions ;;
        4) list_rds_instances ;;
        5) list_iam_users ;;
        *)
            echo "Invalid choice. Please select again."
            ;;
    esac

    display_menu
done

echo "Script execution completed."
```

### **• Usage**

» To use the AWS Resource Tracker script, follow these steps:

» Make sure you have the necessary prerequisites installed, such as AWS CLI, jq, and awk.

» Download the script and save it with the name `aws_resource_tracker.sh`.

» Grant execution permissions to the script by running the command `chmod +x aws_resource_tracker.sh`.

» Run the script using the command `./aws_resource_tracker.sh`.

» The script will display a menu with options to select the type of resource you want to track. Enter the corresponding number and press Enter.

» The script will retrieve the information from the selected AWS service and save it in a file with a timestamp.

» Repeat the process for other resource types or choose the "Exit" option to end the script.

### **• Automating Execution with crontab**

To further streamline the resource tracking process, you can automate the execution of the AWS Resource Tracker script using crontab. By configuring a crontab entry, you can schedule the script to run daily at 7 PM for more useful for the organization. Here's how you can do it:

1. Open the crontab configuration using the command `crontab -e`.
    
2. Add the following line to the crontab file:
    

```plaintext
0 19 * * * /path/to/script.sh
```

With this configuration, the script will execute automatically at 7 PM every day, collecting the latest information about your AWS resources.

### **• Conclusion**

Keeping track of AWS resources is crucial for effective management and security. The AWS Resource Tracker script simplifies this task by providing a convenient way to list and save resource details. By automating its execution with crontab, you can ensure that resource tracking becomes a seamless daily routine. Leverage the AWS Resource Tracker script to stay organized, maintain an overview of your AWS resources, and enhance your resource management practices.

*If you found this blog post informative and useful, I would sincerely appreciate your support by giving it a like* ❤️ *and following for more content. Your engagement means a lot to me, and I'm grateful for the time spent reading this post. Thank you!*