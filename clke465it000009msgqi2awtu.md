---
title: "Day 8 - Basic Git & GitHub for DevOps Engineers"
datePublished: Sat Jul 22 2023 14:37:04 GMT+0000 (Coordinated Universal Time)
cuid: clke465it000009msgqi2awtu
slug: day-8-basic-git-github-for-devops-engineers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1690036507375/fe59bda3-5130-4c91-9940-f12583b4e56c.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1690036612694/7da9771e-8232-405e-a129-24d08ae24646.jpeg
tags: github, git, devops, 90daysofdevops, trainwithshubham

---

### 🌟 **Introduction** 🌟

Welcome to Day 8 of the thrilling #90DaysOfDevOps challenge! Today, we're diving into the exciting world of Git and GitHub. 🚀 Unleash the power of version control as we explore the magic of Git and its significance in software development. Discover the wonders of GitHub, where collaboration and sharing come to life. 📚 In this blog, we'll unveil the beauty of distributed version control and its advantages over centralized systems. Let's get hands-on by installing Git, creating a GitHub account, and mastering repository creation and cloning. 💻🐙 Are you ready to level up your DevOps journey with Git and GitHub? Let's embark on this incredible adventure together! 🌟

### 💾 **What is Git?**

Git is a distributed version control system that helps developers track and manage changes to their code during software development. Imagine Git as a time machine that allows you to save snapshots of your project at different points in time. This way, you can go back to any previous state if something goes wrong or if you want to check the history of your code. 💾🕰️

Let's dive into a real-time example to grasp Git better. Imagine you're working on a group project with teammates, each responsible for different code parts. Without Git, challenges arise:

1. Overwriting Changes: Concurrent edits to the same file may overwrite work, causing conflicts and data loss. 😬🔄
    
2. Tracking Changes: It's tough to monitor who altered what and when hampering progress and bug tracking. 📝🔍
    
3. Collaboration Complexity: Coordinating changes becomes daunting with a shared codebase. 🤝🗂️
    

In summary, Git streamlines collaboration tracks changes effortlessly, and manages code history, making it a must-have tool for developers and projects of all scales. 🚀💻

### 🤝 **What is GitHub?**

GitHub is a web-based platform and service that helps developers collaborate on coding projects and manage their source code. It provides a user-friendly interface to store, share, and track changes to code, making it easier for developers to work together on software development.

Key features of GitHub:

1. **Code Repositories**: GitHub stores code in "repositories" or "repos." Each repo is like a folder where developers keep their code and project files. 🗂️
    
2. **Collaboration**: Multiple developers can work on the same project by "cloning" the repo to their computers, making changes, and "pushing" the changes back to GitHub. 👥
    
3. **Version Control**: GitHub uses a system called "Git," which tracks changes to the code. Developers can go back to previous versions if needed and see who made what changes. 🔀📜
    
4. **Issues and Pull Requests**: Developers can report issues or suggest changes in a project through "issues" and "pull requests." This fosters communication and problem-solving. 📝✉️
    
5. **Community and Learning**: GitHub is not just a code-sharing platform; it's a community. Developers can learn from others' code, contribute to open-source projects, and collaborate on exciting projects. 🌐🤝
    

### 🔍 **What is Version Control? What types of version controls**

Version control is a system that keeps track of changes in files over time so you can go back to specific versions later. It helps you undo changes, compare different versions, and see who made certain changes. 🔍🔄

There are two main types of version control systems:

1. **Centralized Version Control System (CVCS)**: It uses a central server to store all versions of a project's files. Developers check out files from the server, make changes, and check them back in. Examples are Subversion and Perforce. 🏢💻
    
2. **Distributed Version Control System (DVCS)**: Developers clone the entire project repository, including its history, to their local computers. They work independently and can later merge their changes back into the main repository. Examples are Git, Mercurial, and Darcs. 🌐🔧
    

Both systems help teams collaborate, manage changes, and maintain project history effectively. They are valuable tools for developers working on projects with multiple contributors. 🤝🚀

### 🌐 **Why do we use distributed version control over centralized version control?**

We use Distributed Version Control Systems (DVCS) over Centralized Version Control Systems (CVCS) for several reasons:

1. **Offline Work**: With DVCS, developers can work offline and make changes to the code without needing a constant internet connection. They can commit changes locally and later synchronize with the central repository when online. 📶💻
    
2. **Faster Performance**: DVCS allows developers to perform version control tasks quicker since most operations are done locally without relying on a central server. This leads to a smoother and faster development process. ⚡🚀
    
3. **Enhanced Collaboration**: Each developer in a DVCS has a complete copy of the project and its history. This promotes better collaboration as they can work independently and later merge their changes back into the main repository. 🤝🔄
    
4. **More Flexibility**: DVCS allows developers to create multiple branches and work on different features or fixes simultaneously. They can share their changes with specific team members or work on experimental features without affecting the main codebase. 🌿💡
    
5. **Increased Security**: The distributed nature of DVCS means that the project history is stored on multiple servers and computers. This redundancy makes it more resistant to data loss compared to CVCS, where the central server contains the entire history. 🔒🔐
    
6. **Decentralization**: In DVCS, no single point of failure exists, and developers are not dependent on a central server. This decentralization provides more autonomy and reliability to the team. 🌐🏛️
    

Overall, Distributed Version Control offers greater flexibility, speed, collaboration, and security, making it a preferred choice for many development teams in modern software development workflows. 🌟👥🛡️

### 🚀 **Task 1: Install Git**

To get started, we'll install Git on your computer. Git works on Windows, macOS, and Linux. Follow these simple steps:

1. Go to [git-scm.com/downloads](https://git-scm.com/downloads), the official Git website.
    
2. Download the installer that matches your operating system.
    
3. Run the installer and follow the on-screen instructions to finish the installation.
    
4. Once the installation is done, open a terminal or command prompt, and type git --version to make sure Git is installed correctly. You should see the version number displayed.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690032007471/cf166c06-152f-4cee-8b1f-232d367c1d07.png align="left")
    

Great job! Git is now successfully installed on your computer. Let's move on to the next task. 🚀💻

### 🤝 **Task 2: Create a GitHub Account**

GitHub is a popular platform where people store their Git projects and work together on them. If you don't have a GitHub account yet, here's how you can create one:

1. Open your web browser and go to [github.com](http://github.com).
    
2. On the GitHub homepage, click on the "Sign up" button.
    
3. Fill in the required information, like your username, email, and password.
    
4. Choose a plan that suits you (Free or one of the paid options) based on your needs.
    
5. Complete the verification process, which might include solving a CAPTCHA or confirming your email.
    

Once you finish these steps, congratulations! You've successfully made your GitHub account. Now, you can start sharing and collaborating on your projects. 🌟🤝

### 📝 **Exercise 1: Create a New Repository on GitHub**

Let's get started by creating a new repository on GitHub, where we'll keep and organize our code. Follow these simple steps:

1. Open your web browser and visit [github.com](http://github.com).
    
2. Log in to your GitHub account.
    
3. On the GitHub homepage, click the "+" button at the top-right corner, then select "New repository" from the menu.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690033856699/7d578e01-015f-4c83-a488-ee13c694a8a4.png align="center")
    
4. Give your repository a meaningful name.
    
5. You can also add a description to give more details about your repository.
    
6. Choose whether you want the repository to be public or private, depending on your needs.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690033965188/d0af4f49-6ac0-470d-8f4c-1c68d02e171a.png align="left")
    
7. Finally, click the "Create repository" button to create your new repository. That's it! Your central code storage is ready to go. 🎉
    

### 📂 **Exercise 2: Clone the Repository to Your Local Machine**

Our repository is created on GitHub. You can now use the "git clone" command to duplicate the central repository onto your local machine's repository. Here's how you can do it in simple steps:

1. Go to your repository page on GitHub and click on the "Code" button.
    
2. Copy the repository URL.
    
3. Open the terminal or command prompt on your computer.
    
4. Navigate to the directory where you want to save the repository.
    
5. Use the command "git clone" followed by the repository URL you copied. For example: git clone [**https://github.com/your-username/your-repository.git**](https://github.com/your-username/your-repository.git)
    
6. Press Enter, and the repository will be cloned to your local machine.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690034402603/dd3c469b-4624-4e35-b3f1-716d2285537e.png align="center")
    

Great job! 👏 You have successfully cloned the repository to your local machine. Let's proceed to the next exercise. 🚀

### 🔄 **Exercise 3: Make Changes, Commit, and Push**

Now that you have the repository copied to your computer, you can make changes to the files and keep track of those changes. Follow these simple steps:

1. 🚶‍♂️ Move to the repository directory.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690035181555/989522e8-aebb-461e-a23d-a3bff18f0800.png align="left")
    
2. 📄 Create two files using the **touch** command.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690035217079/f956b09f-10ff-4eab-a0a0-d48a846dbb20.png align="center")
    
3. 🔍 Use the command "**git status**" to see the changes you made. It will show the modified files.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690035264978/d2d69d1a-f88e-4a90-a44c-9eb97f603256.png align="center")
    
4. ➕ Use the command "git add" followed by the file names to prepare the tracking changes. For example: "**git add filename.txt**" or "**git add .**" to track all changes. Now check the status and our file is now tracked.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690035325182/e7637cb7-6151-42da-b23d-d1bda3d19fb9.png align="center")
    
5. 💼 Use the command "git commit" to save the changes with a meaningful message describing the modifications. For example: **git commit -m 'Added new files'**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690035432374/0310ac9b-517e-400e-93ae-065d81de7f0b.png align="center")
    
6. 🚀 Finally, use the command "git push" to upload the committed changes back to the repository on GitHub. For example: "**git push origin main**" or "**git push origin master**," depending on the branch name.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690035545008/b03f29b9-5b3a-4525-90c9-bd605550894d.png align="center")
    

By following these steps, you'll successfully make changes to your GitHub repository, commit the changes, and push them back to the remote repository. This process ensures that your code is version-controlled and accessible to collaborators on GitHub. 🚀

### 🎉 **Conclusion** 🎉

Congratulations! You've completed Day 8 of the #90DaysOfDevOps challenge. Today, you gained a solid understanding of Git and GitHub, covering tasks like creating repositories, cloning them locally, making changes, committing, and pushing back to GitHub. These core exercises are crucial for version control and collaborative software development. Keep up the fantastic work! 🎉🚀

Stay in the loop with my latest insights and articles on cloud ☁️ and DevOps 🚀 by following me on Hashnode, LinkedIn ([**www.linkedin.com/in/nishit1907**](http://www.linkedin.com/in/nishit1907)), and GitHub ([**https://github.com/NISHIT-RAJANI**](https://github.com/NISHIT-RAJANI)).

**Thank you for reading!** 🙏 Your support means the world to me. Let's keep learning, growing, and making a positive impact in the tech world together.