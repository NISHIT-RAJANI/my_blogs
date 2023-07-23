---
title: "Day 4 : Basic Linux Shell Scripting for DevOps Engineers"
seoTitle: "Shell Scripting DevOps: Automate, Customize, and Enhance Your Linux"
seoDescription: "Learn how to use shell scripting to automate, customize, and enhance your Linux systems. Basics of shell scripting and its significance for DevOps engineer."
datePublished: Tue Jul 18 2023 05:20:02 GMT+0000 (Coordinated Universal Time)
cuid: clk7uidqk000i09leaxrffie0
slug: day-4-basic-linux-shell-scripting-for-devops-engineers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1689656318247/9a550dc2-758d-406a-a366-e168fb447589.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1689657182124/3898ee60-0112-46c1-b348-b8307c6b2adf.jpeg
tags: shell-scripting, shell-script, 90daysofdevops, tws, linux-shell-scripting

---

### **Introduction** 🌟

Welcome to Day 4 of the thrilling #90DaysOfDevOps challenge! 🌟 Today, we'll dive into the basics of Linux shell scripting and its significance for DevOps engineers. Shell scripting is a powerful skill that empowers you to automate tasks, manage system settings, and supercharge DevOps workflows. 💻🚀 Let's jump right in and master the essentials of shell scripting together! 👨‍💻📝

### **What is Shell Scripting for DevOps?** 📜💻

In simpler terms, shell scripting involves writing a set of commands in a file that the shell interpreter can execute. The shell acts as a bridge between the user and the operating system, interpreting and running those commands. 📝💻🔍

For DevOps engineers, shell scripting is essential for automating repetitive tasks, configuring systems, managing infrastructure, and coordinating various tools and processes. It empowers professionals to create personalized workflows, automate deployments, monitor system health, and more. 🛠️🚀📊

With shell scripting, you can:

1. Automate tasks: Save time and reduce errors by automating repetitive tasks through scripts. ⏰🤖
    
2. Customize workflows: Tailor workflows to your specific needs using shell scripts. 🎨📋
    
3. Configure systems: Manage system settings, install software packages, and set up environments with shell scripts. ⚙️🔧
    
4. Integrate tools and processes: Seamlessly integrate different tools and processes into cohesive pipelines using shell scripts, enabling efficient collaboration and automation. 🔄🔗🤝
    

Let's dive into the world of shell scripting and unlock its full potential for your DevOps journey! 🚀💡🌟

### **What is** `#!/bin/bash`**? Can we write** `#!/bin/sh` **as well**❓

The #!/bin/bash (shebang) is like an instruction that tells the computer which interpreter to use when running the script. In this case, it specifies using the Bash shell, which is a popular choice for running scripts on Linux. 💻🚀

Alternatively, you can use #!/bin/sh, which refers to the system's default shell. It might be Bash or a different compatible shell, depending on the system. 🔄🐚

Keep in mind that Bash has more advanced features than the basic /bin/sh. If your script needs those features, it's better to use #!/bin/bash to make sure everything works smoothly. 🛠️👍

### **Writing a Shell Script to Print a Message** 📝🖨️

To get started, let's try a basic example of a shell script that displays a message. Begin by creating a new file using **nano** editor, such as [task1.sh](http://task1.sh), and include the code provided below: 📝

```plaintext
#!/bin/bash
echo "I will complete the #90DaysOfDevOps challenge"
```

In this script, the line starting with **#!/bin/bash** specifies that the script should be interpreted using Bash. The echo command is then used to print the message "I will complete the #90DaysOfDevOps challenge" on the terminal when the script is run. 📜

To make it executable use the command "**chmod 700** [**task1.sh**](http://task1.sh)," and then run it with "**./**[**task1.sh**](http://task1.sh)" in the terminal. The message should appear on the terminal when executed. 🚀👩‍💻

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689657019662/44cb78ae-f7cb-453c-9a8a-52ae0826694e.png align="left")

### **Taking User Input and Printing Variables** 📥🔤

Shell scripting provides the ability to engage with users and dynamically handle input. Let's explore an example script that accepts user input, saves it in a variable, and displays the variable's value.

```plaintext
#!/bin/bash

# Prompt the user for their name
read -p "Enter your name: " name

# Print a greeting message with the user's name
echo "Hello, $name! Welcome to the shell scripting world!"
```

This Bash script prompts the user for their name, reads the input, and stores it in the "name" variable. Then, it prints a greeting message with the user's name. 😊

To use this script, save it in a file (e.g., [task2.sh](http://task2.sh)), make it executable using the command "**chmod 700** [**task2.sh**](http://task2.sh)", and run it using ./[script.sh](http://script.sh) in the terminal. You will be prompted to enter your name, and the script will greet you with a personalized message based on the input provided. 📝👋

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689617400041/31b4f6c5-b384-4401-b317-6e87d3516fe0.png align="left")

### **Using If-Else Statements in Shell Scripting** 🔄

Using "if else" in Shell Scripting let's compare two numbers and execute different codes based on the comparison result. Here's an example:

```plaintext
#!/bin/bash

# Read user input and store it in the variable 'num1'
read -p "Enter the first number: " num1

# Read user input and store it in the variable 'num2'
read -p "Enter the second number: " num2

# Compare the two numbers
if [ $num1 -eq $num2 ]; then
    echo "Both numbers are equal."
elif [ $num1 -lt $num2 ]; then
    echo "$num1 is less than $num2."
else
    echo "$num1 is greater than $num2."
fi
```

🔢 This Bash script prompts the user to enter two numbers and stores them in variables 'num1' and 'num2', respectively. It then compares the numbers using an "if else" structure. If the numbers are equal, it displays "Both numbers are equal." If 'num1' is less than 'num2', it shows "$num1 is less than $num2." Otherwise, it prints "$num1 is greater than $num2."

To utilize the script, save it with a .sh extension like "[task3.sh](http://task3.sh)," grant execution permissions with "**chmod 700** [**task3.sh**](http://task1.sh)," and execute it using "./[task3.sh](http://task3.sh)" in the terminal. 💻

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689617894222/1254671b-a7aa-4712-879a-f773dc0d7e14.png align="left")

### **Conclusion** 🎉

In conclusion, shell scripting empowers DevOps professionals to automate, customize, and interact with their Linux systems. With the right knowledge and skills, you can create efficient scripts that save time and enhance productivity. So, embrace the power of shell scripting and unlock new possibilities in your DevOps journey! 🌟💻🚀

Stay in the loop with my latest insights and articles on cloud ☁️ and DevOps 🚀 by following me on Hashnode, LinkedIn ([www.linkedin.com/in/nishit1907](http://www.linkedin.com/in/nishit1907)), and GitHub ([https://github.com/NISHIT-RAJANI](https://github.com/NISHIT-RAJANI)).

**Thank you for reading!** 🙏 Your support means the world to me. Let's keep learning, growing, and making a positive impact in the tech world together.