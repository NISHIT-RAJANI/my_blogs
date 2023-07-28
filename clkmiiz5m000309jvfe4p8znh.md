---
title: "Day 11 - Advanced Git & GitHub for DevOps Engineers Part 2"
datePublished: Fri Jul 28 2023 11:41:07 GMT+0000 (Coordinated Universal Time)
cuid: clkmiiz5m000309jvfe4p8znh
slug: day-11-advanced-git-github-for-devops-engineers-part-2
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1690544372994/652f0bd0-a633-4970-813c-f1d1d899a76f.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1690544457088/eb491986-d5ed-42d8-ba69-fae1b61b593f.jpeg
tags: github, git, 90daysofdevops, day11, trainwithshubham

---

### 🌟 **Introduction** 🌟

Welcome to Day 11 of the thrilling #90DaysOfDevOps challenge! In today's blog post, we delve into some powerful Git techniques and explore the concepts of Git Stash and Cherry-pick. Additionally, we'll unravel the art of resolving merge conflicts, a crucial skill for seamless collaboration. Get ready to learn about Stashing and Applying Changes, mastering the Rebase command, and crafting effective commit messages. Join us as we unravel the magic of Cherry-picking and optimizing features in your projects. Let's embark on this exciting journey of version control and make your DevOps experience even more remarkable! 🚀😊

### 🔒 **What is Git Stash?**

Imagine you are working on a coding project, and suddenly your team asks you to fix a critical bug in another part of the code. You don't want to commit your incomplete changes, as it might create issues in the main codebase. 🐛

Here comes **Git Stash** to the rescue! 🎉

Git Stash is like a secret box where you can hide your unfinished changes safely. When you use "git stash," Git saves your current changes and reverts your workspace to a clean state, as if you never started making those changes. 📦

Once you've fixed the bug, you can easily unstash your changes and continue where you left off, with all your work intact! 🧩 It's a super handy feature for developers, allowing them to switch tasks smoothly and keep their codebase clean and organized. 🧹

### 🍒 **What is Cherry-pick?**

In Git, "cherry-pick" is like hand-picking a specific commit from one branch and applying it to another branch.

Imagine you have two branches in your project, and there's a bug fix or a cool feature in one branch that you want to add to another branch without merging the whole branch. 🐞

Here's where cherry-pick comes to the rescue! 🎉

You can cherry-pick the specific commit from one branch and apply it to another branch. It's like plucking a cherry from one tree and placing it on another tree! 🍒🌳

Cherry-pick is a nifty tool to selectively bring in changes from one branch to another, making it easier to manage code and collaborate with your team. 👩‍💻👨‍💻

### 🔄 **How to resolve merge Conflicts?**

Merge conflicts can happen when you try to combine different branches, and Git doesn't know which changes to keep. This can occur when you're merging or rebasing branches that have gone in different directions.

When a conflict occurs, Git will let you know which files have conflicts. You can use the "git status" command to see the list of conflicted files. 😮

Next, you can use the "git diff" command to see the differences between the conflicting versions and understand what needs to be resolved. 👀

Now comes the fun part! You get to manually edit the conflicting parts in the files, choosing which changes to keep and which to discard. Once you've made the necessary adjustments, you use the "git add" command to tell Git that you've resolved the conflicts. 🛠️

After resolving all the conflicts, you can continue with the merge or rebase process with confidence! 🚀

By resolving merge conflicts, you can ensure that your code is in sync and ready to be shared with the rest of the team. 👩‍💻👨‍💻

### 📋 **Task 1: Stashing and Applying Changes**

In this task, our focus will be on branches, and we'll explore how to utilize the "**git stash**" command to save changes temporarily without committing them. Simply follow these steps: 🌟

1. Create a new branch 🌿 using the below command:
    
    ```plaintext
    git checkout -b dev
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690539009399/f6d1f848-1bfc-4abe-880f-52407fab8756.png align="center")
    
2. Make some changes to the files 📝 in **dev** branch.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690539155701/0c0b6bbc-4064-4835-9191-f18e64ead1e1.png align="center")
    
3. In the middle of your work, your team urgently requests you to handle an important task in the main branch. To handle this situation without losing your progress, you can utilize the "**git stash**" command to save your changes without committing them.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690539288337/03644b21-8ed2-4562-ac9d-9b20457d160d.png align="center")
    
4. Use following the command to switch to the **main** branch and proceed with important tasks.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690539534154/6ac6633b-bde4-4d8f-83a2-8657f2f737f3.png align="center")
    
5. Now that our crucial task is completed, let's switch 🔙 to the dev branch to continue our work. We'll use the "git stash pop" command to retrieve the changes we stashed earlier and apply them on top of the new commits.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690539767936/bffb0869-069c-46a1-a32c-0298814ff442.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690539790036/e61621d3-f823-457a-bfd0-58fa4a5f3e96.png align="center")
    

### 📋 **Task 2: Rebase and Commit Messages**

In this task, we'll be working on the day-10 version01.txt file in the development branch and carrying out a rebase operation. Follow these steps:

1. 📝 Open the `version01.txt` file in the development branch. add the line: "**After bug fixing, this is the new feature with minor alteration.**"
    
    Commit this change with the message: "**Added feature2.1 in development branch.**"
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690540962852/714c92b2-311f-4b4c-8398-21a61c61abce.png align="center")
    
2. 📝 Add another line in version01.txt: "**This is the advancement of the previous feature.**"
    
    Commit this change with the message: "**Added feature2.2 in development branch.**"
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690541099333/564f7d5f-05ae-4811-8a35-83295d4e2d8a.png align="center")
    
3. 📝 Add one more line in version01.txt: "**Feature 2 is completed and ready for release.**"
    
    Commit this change with the message: "**Feature2 completed.**"
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690541217824/ee223a2b-0ec9-47a8-8898-fb64cff9273c.png align="center")
    
4. 🚀 Create prod branch and use **git rebase** to include all the commits from the dev branch into the prod branch.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690541428259/32b50319-e827-448f-bcd9-e067356bf986.png align="center")
    

### 📋 **Task 3: Cherry-picking and Optimizing Features**

In this task, we'll learn about cherry-picking a specific commit from one branch to another and making additional changes to it. Follow these steps:

1. 🚀 Switch to the production branch. And cherry-pick the commit "Added feature2.2 in development branch" using the below command.
    
    ```plaintext
    git cherry-pick <commit-hash>
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690542164818/9394ca2d-0ef4-43d8-a485-35bf7d15a5c2.png align="center")
    
2. ✏️ Add the following lines after "This is the advancement of the previous feature" in version01.txt file:
    
    ```plaintext
     Added few more changes to make it more optimized.
    ```
    
3. 📝 Commit this change with the message "Optimized the feature."
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690542487636/1d559fd9-ae04-4c07-88bd-562746c251bc.png align="center")
    

### 🎉 **Conclusion** 🎉

Congratulations on completing Day 11 of the #90DaysOfDevOps challenge! In this session, we delved into advanced Git techniques like stashing, cherry-picking, and rebasing. Git Stash enables us to save changes temporarily without committing, Cherry-Pick empowers selective commit transfers between branches, and mastering conflict resolution enhances collaboration. The step-by-step guide covered stashing and applying changes, while rebase helped clean up commit history. Leveraging cherry-pick, we optimized features. These powerful Git tools streamline workflows and make collaboration seamless. Keep exploring and practicing, as Git holds immense potential for DevOps engineers. Stay excited for more challenges ahead! 💪😊🚀

Stay in the loop with my latest insights and articles on cloud ☁️ and DevOps 🚀 by following me on Hashnode, LinkedIn ([**linkedin.com/in/nishit1907**](http://linkedin.com/in/nishit1907)**), and GitHub (**[**github.com/NISHIT-RAJANI**](http://github.com/NISHIT-RAJANI)**).**

**Thank you for reading!** 🙏 Your support means the world to me. Let's keep learning, growing, and making a positive impact in the tech world together.