---
title: "Day 10 - Advanced Git & GitHub for DevOps Engineers Part 1"
datePublished: Wed Jul 26 2023 19:40:12 GMT+0000 (Coordinated Universal Time)
cuid: clkk4re8c000109msawkr9ow8
slug: day-10-advanced-git-github-for-devops-engineers-part-1
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1690400092443/3b877eaf-a9b1-4d2b-963c-077a33118507.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1690400403405/68afbcd1-e904-4ef7-b988-df33053cc26c.jpeg
tags: github, git, devops, 90daysofdevops, trainwithshubham

---

### 🌟 **Introduction** 🌟

Welcome to Day 10 of the exciting #90DaysOfDevOps challenge! Today we're delving into Git's interesting world and its potent features. Git is a tool that facilitates developer collaboration, allows them to track changes, and allows them to efficiently manage their code. We'll discuss the ideas of branching, reverting, resetting, and merging in this blog. These methods are crucial for fostering cooperation and guaranteeing the security of our code. So let's get ready to learn about branch creation, committing changes, and rolling back code. We'll also learn how to seamlessly integrate our work by merging and rebasing. So let's start this Git adventure together while you're strapped in! 🚀💻🌟

### 🌿 **Git Branching and Its strategy**

Imagine you and your team are working on a web application, and you have a Git repository set up to manage the codebase. The default branch is usually called "master" or "main," which represents the stable version of your application. 🌿

Now, you want to add a new feature to the application, let's say a user login system. Instead of making these changes directly in the "master" branch, you create a new branch called "feature/login." 🚀

```plaintext
git checkout -b feature/login
```

Now you have switched to the "feature/login" branch, and you can make all the necessary changes to implement the user login system without affecting the main codebase. 💻

While you are working on the "feature/login" branch, your teammate is also working on a different feature, such as adding search functionality. They create a branch called "feature/search" to work on this task.🔍

```plaintext
git checkout -b feature/search
```

Both of you can work independently without interfering with each other's code changes. This way, the "master" branch remains stable, and you can continue to release updates without any disruption. 🤝

Once you have completed the login feature, you can merge the changes back into the "master" branch.

```plaintext
git checkout master
git merge feature/login
```

Now, the main branch has the new login feature, and you can deploy it to the production server. At the same time, your teammate has completed the search feature and merged it into the "master" branch as well.

Git branching strategies can also help in managing releases and bug fixes. For example, if you discover a critical bug in the "master" branch, you can create a hotfix branch to address the issue without affecting ongoing development. 🔧

```plaintext
git checkout -b hotfix/bug-fix
```

Once the bug is fixed, you merge the hotfix branch back into the "master" branch and any other active branches.

```plaintext
git checkout master
git merge hotfix/bug-fix
```

### 🔄 **Git Revert and Reset**

Git Revert: 🔙 When you make a mistake in your code and want to undo a specific commit without erasing its history, you can use Git Revert. It creates a new commit that undoes the changes made in the specified commit. This means that the commit you want to revert will still exist in the history, but the changes it introduced will be removed in a new commit. It's like going back in time and undoing a mistake without altering the past. 🕰️

Git Reset: 🔄 Git Reset, on the other hand, is a more powerful command that allows you to move the current branch to a specific commit. It has different modes like "soft," "mixed," and "hard." The "soft" mode keeps the changes from the commits you reset as staged changes, the "mixed" mode keeps them as unstaged changes and the "hard" mode discards them completely. In simple terms, Git Reset helps you to reset the branch to a previous state and removes the commits after that point. 🌱

### 🔀 **Git Merge and Rebase**

Git Merge: 🤝 Imagine you and your team are working on a group project. Each team member is responsible for a specific feature. Git Merge is like getting everyone's work together at the end of the day and combining it into a single document. It takes the changes from different branches and brings them into the main branch, creating a cohesive codebase. It's like teamwork, where everyone contributes their part, and the project becomes more complete and robust. 🌟👨‍💻👩‍💻

Git Rebase: 🚀 Think of Git Rebase as time travel! When you use Git Rebase, it's like going back in time to the point where you branched off and replaying your changes on top of the latest work. It's like updating your project to the most recent version and integrating your improvements smoothly. This keeps your commit history clean and organized, just like maintaining a clear timeline of project progress. But be cautious, as time travel can be tricky; you may encounter conflicts that need to be resolved. 🕰️

### 📋 **Task 1: Branching, Committing, and Restoring**

🌟 In this task, we'll explore how to create a new branch 🌿, make changes with various messages 📝, and restore a file to an earlier version ⏪. Just follow these simple steps:

1. 🚀 Create a new branch named "dev" from the main branch and verify the change using the command "git checkout dev".
    
    ```plaintext
    git checkout -b dev
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690393896070/0c31566c-d095-4543-8035-677b1359c565.png align="center")
    
2. 📝 Create a new text file named version01.txt and fill it with the following content:
    
    ```plaintext
     "This is the first feature of our application."
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690394246250/bf698866-9e14-4509-8764-6ff867adc812.png align="right")
    
3. 📂 Use the "git add" command followed by the file names to prepare the tracking changes. Then commit this change with the message "Added new feature."
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690394461178/81ee0d0b-7961-439c-9555-da84092a926c.png align="center")
    
4. 📤 Push the `dev` branch to the remote repository using the command:
    
    ```plaintext
     git push origin dev
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690394629895/e06ac9f3-6158-48bd-b955-6a9dd14a666f.png align="center")
    
5. 🔄 Make additional commits to the dev branch by updating the version01.txt file and commit this change with the message "Making the following changes: ...".
    
    ```plaintext
     This is the bug fix in the development branch
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690396653326/1fe8b5d6-bba2-47fa-9a84-2bab12ae7bf5.png align="center")
    
6. 🔄 Perform this step two additional times, including the provided content, and commit each change with relevant messages.
    
    ```plaintext
     This is gadbad code
    ```
    
    ```plaintext
    This feature will gadbad everything from now.
    ```
    
7. 🔙 Revert the version01.txt file to a previous state with the content "This is the bug fix in the development branch."
    
8. 📜 Using the "git log --oneline" command, find the &lt;commit&gt; information and identify the commit you want to reset to.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690397079809/dd0680b3-1eb5-4871-ad96-5ce451ac2317.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690397532063/c07d1393-a97b-4bd9-adfd-f7ad5dbf4ac7.png align="center")
    

### 📋 **Task 2: Branching, Merging, and Rebasing**

In this task, we will explore the concepts of branches, merging, and rebasing. To get started, follow these steps:

1. 🚀 Let's merge the "**dev**" branch with the "**main**" branch. First, check the commits on the "dev" branch by using "**git checkout dev**" 👩‍💻. Then, switch back to the "main" branch and check its commits as well 🌿. Now, execute the "git merge dev" command to combine the commits and observe the results.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690398196023/74f07b52-cb84-402f-a875-33e765a17fa5.png align="center")
    
2. Now, execute the "**git merge dev**" command to combine the commits and observe the results.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690398255957/1b74f16e-16cb-4860-8073-47fbc5f35f3c.png align="center")
    
3. 🔄 As a practice, perform a `git rebase` operation to see the difference it makes. Describe the differences you observe 🔄.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690398567880/74c5688e-3960-4c08-8248-723be3cc7ae4.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690398595067/84b51133-d99e-4e48-9aa6-58d72d30241d.png align="center")
    

In this sequence of commands, the "dev" branch is checked out, and a new text file named "version01.txt" is created with specific content 📝. The changes to the file are staged and committed with an appropriate message 💬. After inspecting the commit history on the "dev" branch, the working branch is switched to "main," and a rebase is performed. The rebase incorporates the commits from "dev" onto "main," resulting in an updated commit history on the "main" branch. This process showcases the interplay between branches, merging changes, and how Git allows developers to manage code development seamlessly.

> **Notes**: Git merge combines changes from one branch into another, creating a new merge commit. Git rebase moves the commits of one branch on top of another, creating a linear history. Merge preserves the original commit history, while rebase provides a cleaner, linear commit graph for easier project tracking.

### 🎉 **Conclusion** 🎉

Congratulations on completing Day 10 of the #90DaysOfDevOps challenge. Today, we delved into advanced Git techniques like branching, merging, and reverting, vital for effective collaboration and version control in software projects. Don't miss Day 11, where we'll continue our Git and GitHub journey for DevOps Engineers in the second part of this topic. Stay tuned! 🚀👩‍💻

Stay in the loop with my latest insights and articles on cloud ☁️ and DevOps 🚀 by following me on Hashnode, LinkedIn ([**linkedin.com/in/nishit1907**](http://linkedin.com/in/nishit1907)**), and GitHub (**[**github.com/NISHIT-RAJANI**](http://github.com/NISHIT-RAJANI)**).**

**Thank you for reading!** 🙏 Your support means the world to me. Let's keep learning, growing, and making a positive impact in the tech world together.