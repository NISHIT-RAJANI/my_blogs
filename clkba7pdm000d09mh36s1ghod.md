---
title: "Day 6 - File Permissions and Access Control Lists"
datePublished: Thu Jul 20 2023 15:02:56 GMT+0000 (Coordinated Universal Time)
cuid: clkba7pdm000d09mh36s1ghod
slug: day-6-file-permissions-and-access-control-lists
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1689858278523/699556f9-761c-4fee-9180-3c8d623c4ae2.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1689865369112/d6eee557-4040-4747-b4c9-50ffaa899a81.jpeg
tags: linux, devops, file-permission, 90daysofdevops, tws

---

### 📚 Introduction

Welcome to Day 6 of the #90DaysOfDevOps challenge. In this blog, we'll explore File Permissions and Ownership in Linux, making it simple to understand! We'll learn how to modify permissions, ownership, and even dive into Access Control Lists (ACL) using commands like "getfacl" and "setfacl." Let's unlock the secrets of secure file management! 🗝️📂

### 📂 File Permissions Overview

In Linux, file permissions dictate who can access, modify, and execute files and directories. They are crucial for ensuring security and control over sensitive data and system resources.

Three categories of users can have distinct permissions for a file:

1. Owner (user) 👤: The user who creates the file or owns it.
    
2. Group 👥: A set of users who share the same access permissions for the file.
    
3. Others 👤👥: All users not included in the owner or group category.
    

🔑 Each category can be assigned three types of permissions:

1. Read (r) 🔍: Users with read permission can view the content of a file or the list of a directory.
    
2. Write (w) ✏️: Users with write permission can modify or delete files and directories.
    
3. Execute (x) 🏃‍♂️: Users with execute permission can run executable files or access directories to list their contents.
    

🔢 File permissions are represented using a three-character string for each category. For example, "rw-r--r--" means the owner has read and write permissions, while the group and others have only read permissions.

👀 To view and modify file permissions, you can use the `ls -l` command to display the permissions for files and directories in the current directory. To change permissions, you can use the `chmod` command, followed by the desired permission code and the filename.

It is crucial to set appropriate file permissions to prevent unauthorized access to sensitive files and maintain the integrity of the system. Always exercise caution when modifying file permissions, as improper settings can lead to security risks and system vulnerabilities.

### 🔒 Task 1: Change the Permission of file/directories

In Linux, when we want to modify file or directory permissions, we use the `chmod` command.

There are two ways to change permissions: the Symbolic method and the Absolute method. 😊

**Symbolic method (ugo):**

* "u" stands for User
    
* "g" stands for Group
    
* "o" stands for Other
    

For example, if a manager asks us to add execute permission for the user, add write permission for the group, and remove read permission for others, and to verify whether permission is changed or not use the following command:

```plaintext
chmod u+x, g+w, o-r file.txt
ls -l file.txt
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689863381319/3ae2da9d-bb23-4d55-8169-6db2ddc4d5d3.png align="left")

**Absolute method:**

Here we use numbers to set permissions for a file or directory. 🧮

Here's the numeric mapping:

* 4 stands for Read 📖
    
* 2 stands for Write ✍️
    
* 1 stands for Execute 🏃‍♂️
    

For example, if we want to set the permissions to read, write, and execute for the owner, read and write for the group, and only read for others, we can use the following command:

```plaintext
chmod 632 test.txt
ls -l file.txt
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689863575798/d22293b0-8155-438c-aaac-a3e73ef5c4cc.png align="left")

Using numbers in the Absolute method provides a quick and precise way to manage permissions in Linux!

### 🔑 Task 2: Change the ownership of a file/directory

In Linux, you can change the ownership of a file using the `chown` command, which stands for "change owner." Only the root user can perform this action.

For example, to change the owner of **file.txt** to ubuntu, you can use the following command:

```plaintext
sudo chown ubuntu file.txt
ls -l file.txt
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689863909984/ff57cf75-6f6e-4185-87a2-c477a7b03bed.png align="left")

After executing the command, the **ubuntu** user becomes the owner of the file.txt file.

### 👥 Task 3: Change the group permission of a file/directory

In Linux, you can alter the group ownership of a file or directory using the `chgrp` command. This task is exclusively restricted to the root user, meaning only the superuser can execute this command.

Example: To illustrate, consider the following command:

```plaintext
chgrp ubuntu devtxt.txt
ls -l file.txt
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689864444395/342a1f26-3f32-4fdf-98c6-db0232e0443b.png align="left")

With this command, the group ownership of the file named file.txt is changed to "ubuntu." However, keep in mind that only the root user or a user with equivalent administrative privileges can successfully perform this action. 🛡️💻

### 🔐 Access Control Lists (ACL) commands getfacl and setfacl

Access Control Lists (ACLs) give precise control over file permissions. Unlike regular permissions (owner, group, and others), ACL lets you set specific access for users or groups.

💡 Two helpful commands for ACL are getfacl (🔍) to view ACL settings and setfacl (🛠️) to modify entries.

To see ACL settings of a file, use:

```plaintext
getfacl file.txt
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689860925305/94d1145b-948d-4717-8060-a7260c2a1253.png align="left")

Note: To use ACL, install it using `sudo apt install acl`.

To change the ACL entries and give particular permissions to users or groups, utilize the **setfacl** command. For example, to grant read, write and execute permissions to a user:✨

```plaintext
setfacl -m u::rw file.txt
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689861520002/4bca3247-4625-4038-86e4-de86648bdf27.png align="left")

ACLs offer a cool way to handle file permissions, especially in tricky situations where you want to give certain people or groups special access.

### 🎯 Conclusion

Congratulations on completing Day 5 of the #90DaysOfDevOps challenge. 🌟 Today, we explored file permissions is essential for secure and controlled access to files and directories in Linux. Throughout this overview, we explored tasks related to changing permissions, ownership, and group permissions of files and directories. Additionally, we learned about Access Control Lists (ACL) and the useful commands `getfacl` and `setfacl` for finer control over permissions. With this knowledge, you can confidently manage file access and ensure data security in your Linux environment. 🚀🔒

Stay in the loop with my latest insights and articles on cloud ☁️ and DevOps 🚀 by following me on Hashnode, LinkedIn ([**www.linkedin.com/in/nishit1907**](http://www.linkedin.com/in/nishit1907)), and GitHub ([**https://github.com/NISHIT-RAJANI**](https://github.com/NISHIT-RAJANI)).

**Thank you for reading!** 🙏 Your support means the world to me. Let's keep learning, growing, and making a positive impact in the tech world together.