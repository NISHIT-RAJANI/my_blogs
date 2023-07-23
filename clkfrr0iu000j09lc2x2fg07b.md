---
title: "Day 9 - Deep Dive in Git & GitHub for DevOps Engineers"
datePublished: Sun Jul 23 2023 18:24:55 GMT+0000 (Coordinated Universal Time)
cuid: clkfrr0iu000j09lc2x2fg07b
slug: day-9-deep-dive-in-git-github-for-devops-engineers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1690136526178/2ce84e2f-d516-4f0a-b3c5-1ced278f04e2.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1690136689499/c82104a6-b85a-449f-a5c4-de8d5cc7c941.jpeg
tags: github, git, devops, 90daysofdevops, trainwithshubham

---

## 🌟 **Introduction** 🌟

Welcome to Day 9 of the #90DaysOfDevOps challenge, where we'll delve into the world of Git and its significance in modern software development. Today, we'll explore crucial concepts such as the difference between the Main Branch and Master Branch, and we'll demystify the distinctions between Git and GitHub. 🌟 Additionally, we'll learn how to create a new repository on GitHub and understand the disparities between local and remote repositories. In a hands-on exercise, we'll connect our local repository to GitHub, create a new file, add content to it, and push our local commits to the remote repository. 🚀 Let's equip ourselves with essential Git knowledge to enhance our development workflow and collaboration in the tech world! 💻🤝

## 💾 **What is Git, and why is it important?**

Git is a powerful and essential tool for developers, acting as a time machine 🕰️ that saves snapshots of projects at different points in time. This enables easy tracking of changes and the ability to go back to previous states if needed. Git facilitates efficient collaboration among team members, preventing overwrites and ensuring the safety of code. Developers can merge changes seamlessly and identify specific contributors, fostering effective teamwork 🚀💻.

Git offers a distributed version control system, allowing independent work and synchronization with a central repository like GitHub 🤝. It provides flexibility, faster performance, and enhanced security. Git empowers developers with efficient version control, instilling confidence in making changes and collaborating seamlessly 💪🔀.

## 🔀 **Difference between Main Branch and Master Branch?**

The difference between the "Main" branch and the "Master" branch is in their names and historical context in version control systems like Git. In the past, "Master" was commonly used as the default branch where main development work took place. However, to promote more inclusive language, many platforms and communities have shifted towards using "Main" instead of "Master."

Both "Main" and "Master" branches serve the same purpose: they are the primary branches where developers collaborate, and the latest stable code is maintained. The choice between the names depends on the preferences and conventions of the development team or organization. Nowadays, "Main" is gaining popularity as the default branch name, reflecting the industry's efforts to adopt more diverse and inclusive practices. 🌐🔄

## 🤝 **Difference between Git and GitHub?**

Let's see the difference between Git and GitHub in simple terms:

Git 🌐: Git is like a magic time machine for developers. It helps them keep track of changes they make to their code while they are working on a project. So, imagine you are writing a story, and you want to save different versions of it at different stages. Git allows developers to do just that for their code. It helps them save snapshots of their code at different points in time. This way, if something goes wrong or if they want to see how their code looked before, they can easily go back to any previous version. Git is a tool that works on your own computer, and it doesn't need the internet to do its magic!

GitHub 🐙: Now, imagine you want to share your story with your friends and work on it together. GitHub is like a cool website where you can upload your story and invite your friends to read, edit, and add their own parts to it. It's a platform that uses Git's magic to store your code and make it accessible online. So, instead of keeping your code only on your computer, you can save it on GitHub and collaborate with others. It's like having a virtual writing club where everyone can contribute to the story and work together.

## 🚀 **How do you create a new repository on GitHub?**

Let's get started by creating a new repository on GitHub, where we'll keep and organize our code. Follow these simple steps:

1. Open your web browser and visit [**github.com**](http://github.com).
    
2. Log in to your GitHub account.
    
3. On the GitHub homepage, click the "+" button at the top-right corner, then select "New repository" from the menu.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690033856699/7d578e01-015f-4c83-a488-ee13c694a8a4.png?auto=compress,format&format=webp align="left")
    
4. Give your repository a meaningful name.
    
5. You can also add a description to give more details about your repository.
    
6. Choose whether you want the repository to be public or private, depending on your needs.
    

## 📂 **Difference between a local and a remote repository?**

Local Repository 🏠: A local repository is a copy of your project that is stored on your computer. It contains all the files, code, and version history of your project. When you work on your project, you make changes to the files in your local repository. Git tracks these changes and allows you to save snapshots of your code at different points in time. This way, you can go back to previous versions if needed or see the history of your project.

Remote Repository 🌐: A remote repository is a copy of your project that is stored on a server or an online platform like GitHub, GitLab, or Bitbucket. It serves as central storage for your project, where you can share your code with others and collaborate with a team. When you want to share your code or collaborate with others, you push your local changes to the remote repository. This way, others can see your changes, contribute their changes, and work together on the project. Remote repositories make it easy for developers to collaborate on projects and keep the code in a secure and centralized location.

## 🔗 **How to connect local to remote?**

To link your local repository with a remote repository on GitHub, adhere to the following steps:

1. Create a new repository on GitHub, as described earlier.
    
2. On your local computer, locate the directory that houses your Git repository using either the command line or a Git client.
    
3. Integrate the URL of the remote repository into your local repository by executing the command:
    
    ```plaintext
     git remote add origin <remote_repository_url>
    ```
    
    Replace `<remote_repository_url>` with the URL of your remote repository on GitHub.
    
4. Verify the connection between your local and remote repositories using the command:
    
    ```plaintext
     git remote -v
    ```
    
    This will display the remote repository URL associated with your local repository.
    

## 📋 **Tasks 1:**

### **• Set your username and email address**

Setting your username and email address in Git is essential for identifying you as the author of commits and contributions in your projects. This information helps Git keep track of who made changes to the code. 👤📧

To set your username and email address, you need to use the following Git commands in the command line or Git client:

```plaintext
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

Replace "Your Name" with your actual name and "[**your@email.com**](mailto:your@email.com)" with your email address. The `--global` flag ensures that these settings are applied globally to all your Git repositories on the computer. 🌐🔧

By providing your username and email address, Git can accurately attribute your contributions, making it easier for other developers to recognize your work in collaborative projects. 🚀🤝

## 📋 Task 2:

### **• Create a repository named "DevOps" on GitHub.**

Go to the GitHub website and sign in to your account.

Use the instructions provided earlier to make a new repository called "Devops" on GitHub.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690134265178/83e8ac87-9d6e-4570-b80b-ca43da2d62f2.png align="center")

### **• Connect your local repository to the repository on GitHub**

Go to the folder on your computer where you want to create the local repository.

🚀 Start a new Git repository by running the command:

```plaintext
git init
```

💻 Include the remote repository's URL in your local repository with the command:

```plaintext
git remote add origin <remote_repository_url>
```

🔗 Replace `<remote_repository_url>` with the URL of your "Devops" repository on GitHub.

✅ To ensure that your local and remote repositories are connected, check the remote repository's URL with:

```plaintext
git remote -v
```

👀 This command should display the URL of the remote repository linked to your local repository.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690134657704/cd841736-4eab-4c67-bcb4-f28598ed17cb.png align="center")

### **• Create a new file in Devops/Git/Day-02.txt & add some content to it**

In your local repository, make a new file called "Day-02.txt" inside the "DevOps/Git" folder. 📝

Include some content in the file, like this: 📄

```plaintext
Welcome to DevOps
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690134942431/c244f7df-1401-4b93-9bbd-613b649a81bf.png align="center")

### **• Push your local commits to the repository on GitHub**

🔍 Use the command "**git status**" to see the changes you made. It will show the modified files.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690135057830/c16fa592-d90e-4d4a-ac15-e9dcd6efb5f6.png align="center")

➕ Use the command "git add" followed by the file names to prepare the tracking changes. For example: "**git add filename.txt**" or "**git add .**" to track all changes. Now check the status and our file is now tracked.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690135238245/07cc386f-4616-41be-9e7e-eb39bedc2e19.png align="center")

💼 Use the command "git commit" to save the changes with a meaningful message describing the modifications. For example: **git commit -m 'Added new files'**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690135777106/9e189d28-b221-4d55-a1dc-8a8fca5d5ea8.png align="left")

🚀 Finally, use the command "git push" to upload the committed changes back to the repository on GitHub. For example: "**git push origin main**" or "**git push origin master**," depending on the branch name.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690135727433/03401408-e76c-48b4-a924-a2d4ee556f17.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690136616722/b70b1a49-9891-4804-aa41-ff04de6be57d.png align="center")

## 🎉 **Conclusion** 🎉

Congratulations! You've completed Day 9 of the #90DaysOfDevOps challenge. In this blog post, we covered essential steps in utilizing Git and GitHub for version control. After creating a repository on GitHub and connecting it to the local repository, we successfully added a new file and pushed changes to GitHub. We delved into the significance of Git as a version control system and explained the difference between the main and master branches. Additionally, we clarified the dissimilarity between Git and GitHub, emphasizing their respective roles. Understanding the difference between local and remote repositories, we seamlessly connected them to facilitate efficient collaboration. With these insights, you can now confidently manage your projects with Git and GitHub, enhancing your development journey. 🚀💻

Stay in the loop with my latest insights and articles on cloud ☁️ and DevOps 🚀 by following me on Hashnode, LinkedIn ([**linkedin.com/in/nishit1907**](http://linkedin.com/in/nishit1907)**), and GitHub (**[**github.com/NISHIT-RAJANI**](http://github.com/NISHIT-RAJANI)**).**

**Thank you for reading!** 🙏 Your support means the world to me. Let's keep learning, growing, and making a positive impact in the tech world together.