---
title: "Day 3 Task: Basic Linux Commands"
datePublished: Mon Jul 17 2023 05:52:32 GMT+0000 (Coordinated Universal Time)
cuid: clk6g8bsm001e09laa0b9gpxv
slug: day-3-task-basic-linux-commands-1
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1689572727938/de08943e-0478-43d3-b12d-e2cd1416a9f3.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1689573095550/1ffe3635-9b8e-4cb7-af0f-7843303561e0.jpeg
tags: linux, linux-for-beginners, linux-commands, 90daysofdevops, tws

---

## **Introduction** 🌟

Welcome back to Day 3 of the thrilling #90DaysOfDevOps challenge! Today, we'll explore the wonders of Linux commands, like magical keys unlocking every DevOps engineer's potential! With these tools, navigating your Linux system becomes as easy as exploring a map. 🚀🗺️💻 Get ready for a tech-packed journey! Together, we'll unravel the mysteries of essential Linux commands, discovering hidden treasures that elevate your skills. Excitement fills the air as we dive into this epic DevOps adventure! Let's go! 🌟💻

## **1\. To view what's written in a file** 👀

To view the contents of a file in Linux, you can use the "**cat**" command. For example, let's say you have a file named "example.txt" To view what's written in this file, open your terminal and write **cat example.txt**:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689536839401/dab74e0c-2f89-4918-b004-5aab6bf0bdb6.png align="left")

Also we can use "less" or "more" instead of "cat" to view files as they offer better text navigation. "Cat" shows all content at once, while "less" and "more" allow scrolling and analyzing large files more easily.

## **2\. To change the access permissions of files** 🔒

Changing the access permissions of files in Linux is done using the "**chmod**" command, which stands for "change mode." 🚪

In Linux, every file has three types of permissions: read (r), write (w), and execute (x). These permissions can be set for three different categories of users: the file's owner (u), the group (g) the file belongs to, and others (o) who are not the owner or part of the group.

To change the permissions, we use a combination of letters and symbols. For example:

* "**chmod u+rwx example.txt**" grants read, write, and execute permissions to the file owner.
    
* "**chmod go-r example.txt**" revokes read permission from the group and others.
    

Here's an example:

Let's say we have a script file named "[script.sh](http://script.sh)" that we want to make executable only for the owner and read-only for others. We would use the following command:

```plaintext
chmod u+x,go-w script.sh
```

In this command:

* "u+x" adds execute permission to the owner.
    
* "go-w" removes written permission from the group and others.
    

After running this command, the owner of "[script.sh](http://script.sh)" will be able to execute it, while the group and others will only have read access.

## **3\. To check which commands you have run till now** 📜

To check the commands you have run in the current terminal session in Linux, you can use the "history" command. 📜

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689536717214/bd6803ba-258a-4b45-969e-a1e795dfac22.png align="left")

## **4\. To remove a directory/ Folder** 🗑️

Removing a directory or folder in Linux is done using the "**rmdir**" or "**rm**" command. 🗑️

The "**rmdir**" command is used specifically to remove empty directories. For example:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689537382826/f0bf89c4-4375-4771-af2f-e7abddf6d62b.png align="left")

The "rmdir" removes an empty "example" directory, while "**rm -r**" deletes directories with content and files. For example

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689537708599/a38481e4-1e05-4165-8a7f-59c5662f23aa.png align="left")

Be cautious with "rm -r" to delete "demo" and its contents without confirmation, leading to permanent data removal. Double-check directories to avoid accidental data loss. Use commands responsibly! 🛡️🗑️🔍🧹

## 5\. To create a fruits.txt file and to view the content 📄

To create a "fruits.txt" file in Linux, you can use the "**touch**" command. 📄

For example:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689538207515/5bfb050b-7297-4e89-8696-8ce6547ab0a9.png align="left")

This command will create an empty file named "fruits.txt" in the current directory.

Next, to view the content of the "fruits.txt" file, you can use the "cat" command. 🐱

For example:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689538273385/bdbd5423-1ef0-4318-9326-e368d01fd79f.png align="left")

## **6\. Add content in fruits.txt (One in each line) - Apple, Mango, Banana, Cherry, Kiwi, Orange, Guava**🍏🍇🍌🍒🥝🍊🍈

To add content to the "fruits.txt" file, you can use a text editor or the "**echo**" command to append each fruit on a new line. Here's an example using the "echo" command:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689538423377/80a49a8c-6670-4961-9121-f4e690572c3c.png align="center")

This command adds each fruit on a separate line in the "fruits.txt" file. You can then use the "cat" command to view the contents of the file:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689538453930/d1ccd9a3-2688-4811-bdd1-48abf12172b2.png align="left")

Now your "fruits.txt" file is filled with delicious fruits! 🍎🥭🍌🍒🥝🍊🍏 Enjoy!

## **7\. To Show only top three fruits from the file** 🔝

To display only the top three fruits from the "fruits.txt" file, you can use the "**head**" command with the "**\-n**" option, specifying the number of lines you want to see. In this case, we want to see the first three lines, which represent the top three fruits in the file. 🍎🥭🍌

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689538651149/c2feed8f-dd65-465a-a9ca-3ecf5b6340a4.png align="left")

## **8\. To Show only bottom three fruits from the file** 🔻

To display only the bottom three fruits from the "fruits.txt" file, you can use the "tail" command with the "-n" option, specifying the number of lines you want to see from the end of the file. In this case, we want to see the last three lines, which represent the bottom three fruits in the file. 🥝🍊🍏

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689538771525/294621a7-959f-446d-9e71-dfecf7934b2b.png align="left")

## **9\. To create another file Colors.txt and to view the content** 🌈

To create a new file called "Colors.txt" in Linux, you can use the "touch" command followed by the desired filename. This command will create an empty file named "Colors.txt" in the current directory. Now, to view the content of the file, you can use the "cat" command:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689538966069/e3269c90-9fc3-46c3-8c5a-7e732b4f1caf.png align="left")

## **10\. Add content in Colors.txt (One in each line) - Red, Pink, White, Black, Blue, Orange, Purple, Grey** 🌹💗⚪⚫🔵🍊💜🔳

To add the specified content to the "Colors.txt" file with each color on a separate line, you can use the following command:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689539165625/192f93ab-3bfd-4c02-acdc-8f87f3efc654.png align="center")

🌈🎨 This command will add the colors 🌹 Red, 💗 Pink, ⬜ White, ⬛ Black, 🔵 Blue, 🍊 Orange, 💜 Purple, and 🔳 Grey to the "Colors.txt" file, with each color on its line. If you view the content of the file using the `cat` command:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689539209725/d584b2c7-1064-403a-a449-a3aef576d911.png align="left")

## **11\. To find the difference between fruits.txt and Colors.txt file** 🍏🌈🔄

To find the difference between the contents of two files, such as "fruits.txt" and "Colors.txt," you can use the "**diff"** command. Here's an example:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689539397864/775f8224-ef7e-4b03-8285-9b98fceeaa8b.png align="left")

🔍🍎📄🎨 This command will compare the contents of "fruits.txt" and "Colors.txt" files. If there are any differences between the two files, the `diff` command will show them in the output.

With the `diff` command, you can easily spot the variations between two files and manage your data more efficiently. 📊👀

## Conclusion 🎉

🎉🚀 Congratulations on mastering essential Linux commands! 📜💻 You've gained valuable skills in file interactions, permissions, and command analysis. From creating files to exploring their contents, you've become proficient in various Linux aspects. 📄📁 By using commands like "ls," "chmod," and "rm," you're now a Linux command-line pro! "Less" and "more" help you read files effortlessly. 📝👓 You've even created "fruits.txt" and "Colors.txt" and learned to display top and bottom items with "head" and "tail." The "diff" command aids in identifying file differences. 🍏🍇🍒 Keep practicing and exploring as your Linux adventure thrives! 💪💡 Embrace the command line's power and discover new possibilities in the vast Linux world. 🌐🐧 Happy DevOps exploring! 🌟🚀🔧

Stay in the loop with my latest insights and articles on cloud ☁️ and DevOps 🚀 by following me on Hashnode, LinkedIn ([www.linkedin.com/in/nishit1907](http://www.linkedin.com/in/nishit1907)), and GitHub ([https://github.com/NISHIT-RAJANI](https://github.com/NISHIT-RAJANI)).

**Thank you for reading!** 🙏 Your support means the world to me. Let's keep learning, growing, and making a positive impact in the tech world together.