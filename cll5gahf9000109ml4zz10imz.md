---
title: "Day 12 - Linux and Git-GitHub Cheat Sheet"
datePublished: Thu Aug 10 2023 17:46:08 GMT+0000 (Coordinated Universal Time)
cuid: cll5gahf9000109ml4zz10imz
slug: day-12-linux-and-git-github-cheat-sheet
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1691689481806/a3740051-fd69-4488-a729-42c2cc9a9245.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1691689558804/7484f7d3-8d95-48a1-b523-b0a675e0b5c8.jpeg
tags: linux, github, git, devops, 90daysofdevops

---

## **Linux Cheat Sheet: Essential Commands and Operations**

| **Navigating the File System** |  |
| --- | --- |
| 🗺️ `pwd` | Print working directory |
| 📂 `ls` | List files and directories |
| 🚶‍♂️ `cd` | Change directory |
| ↖️ `cd ..` | Move up one directory |
| 🏠 `cd ~` | Navigate to the home directory |
| 📂 `mkdir` | Create a directory |
| 🚫 `rmdir` | Remove an empty directory |
| 📄 `cp` | Copy files or directories |
| 🔄 `mv` | Move or rename files/directories |
| 🗑️ `rm` | Remove files or directories |

| **File Operations** |  |
| --- | --- |
| 📄 `touch` | Create an empty file |
| 🔍 `cat` | Concatenate and display file content |
| 📜 `more` | Display file content page by page |
| 👀 `less` | Display file content with backward navigation |
| 📰 `head` | Display the beginning of a file |
| 📃 `tail` | Display the end of a file |
| ✍️ `nano` or ✏️ `vim` | Text editors to edit files |

| **Working with Directories** |  |
| --- | --- |
| 🗺️ `pwd` | Print working directory |
| 📂 `ls` | List files and directories |
| 🚶‍♂️ `cd` | Change directory |
| 📂 `mkdir` | Create a directory |
| 🚫 `rmdir` | Remove an empty directory |
| 📄 `cp` | Copy files or directories |
| 🔄 `mv` | Move or rename files/directories |
| 🗑️ `rm` | Remove files or directories |

| **Viewing File Content** |  |
| --- | --- |
| 🔍 `cat` | Concatenate and display file content |
| 📜 `more` | Display file content page by page |
| 👀 `less` | Display file content with backward navigation |
| 📰 `head` | Display the beginning of a file |
| 📃 `tail` | Display the end of a file |
| 🔍 `grep` | Search for patterns in files |
| 🔍 `find` | Search for files and directories |

| **Process Management** |  |
| --- | --- |
| ⚙️ `ps` | Display currently running processes |
| 🔄 `top` | Monitor system processes in real-time |
| ❌ `kill` | Terminate a process |
| ⚰️ `pgrep` | Find process IDs by name |
| ⏯️ `bg` | Move a process to the background |
| ⏏️ `fg` | Bring a background process to the foreground |
| 🔄 `ps aux` | Display detailed process information |

| **Networking and Connectivity** |  |
| --- | --- |
| 🌐 `ifconfig` or 🌐 `ip addr` | Display network interface information |
| 🌐 `ping` | Test network connectivity to a host |
| 🔍 `nslookup` or 🔍 `dig` | DNS query tools |
| 📈 `netstat` | Network statistics and connections |
| 📊 `ss` | Socket statistics |
| 📶 `nc` | Netcat, a versatile networking utility |
| 🚪 `ssh` | Secure shell for remote access |
| 🚢 `scp` | Securely copy files between hosts |
| 📥 `wget` or 📥 `curl` | Download files from the web |

| **Package Management** |  |
| --- | --- |
| 📦 `apt` or 📦 `yum` | Package managers for installation and updates |
| 📦 `apt-get`, 📦 `apt-cache`, 📦 `apt-add-repository` | Ubuntu/Debian package management |
| 📦 `yum`, 📦 `dnf`, 📦 `rpm` | Red Hat-based package management |
| 📦 `dpkg` | Debian package manager |
| 🐍 `pip` | Python package installer |
| 💎 `gem` | RubyGems package manager |
| 📦 `npm` | Node Package Manager for JavaScript |

## **Git and GitHub Cheat Sheet: Key Operations**

| **Git Basics** |  |
| --- | --- |
| 🌱 `git init` | Initialize a new Git repository |
| 📥 `git clone <repository>` | Clone a remote repository to your local machine |
| ➕ `git add <file>` | Stage changes for commit |
| ✅ `git commit -m "message"` | Commit staged changes with a message |
| 📊 `git status` | View the status of your repository |
| 🔄 `git diff` | View the differences between changes |
| 📜 `git log` | View commit history |
| ⏪ `git reset <file>` | Unstage changes |
| ⏩ `git checkout <commit>` | Move to a specific commit |
| 🌳 `git branch` | List all branches |
| ➡️ `git branch <branch>` | Create a new branch |
| 🔀 `git checkout <branch>` | Switch to a different branch |
| 🔄 `git merge <branch>` | Merge changes from one branch into another |
| 🔄 `git pull` | Fetch and merge changes from a remote repository |

| **Remote Repositories** |  |
| --- | --- |
| 🔗 `git remote add <name> <url>` | Add a remote repository |
| 🚀 `git push <remote> <branch>` | Push local changes to a remote repository |
| 📥 `git pull <remote> <branch>` | Fetch and merge changes from a remote repository |
| 📥 `git clone <repository>` | Clone a remote repository to your local machine |
| 🔄 `git fetch <remote>` | Fetch changes from a remote repository |

| **Undo and Discard Changes** |  |
| --- | --- |
| ⏪ `git reset --hard <commit>` | Discard changes and move to a specific commit |
| 🧹 `git clean -f` | Remove untracked files |
| ⏪ `git revert <commit>` | Create a new commit that undoes a specific commit |
| 💼 `git stash` | Temporarily save changes without committing |
| 🧺 `git stash apply` | Apply the most recent stash |
| 🧺 `git stash pop` | Apply and remove the most recent stash |

| **Branch Management** |  |
| --- | --- |
| 🌳 `git branch` | List all branches |
| ➡️ `git branch <branch>` | Create a new branch |
| 🔀 `git checkout <branch>` | Switch to a different branch |
| 🔄 `git merge <branch>` | Merge changes from one branch into another |
| 🗑️ `git branch -d <branch>` | Delete a branch |
| ✏️ `git branch -m <new-name>` | Rename the current branch |

| **GitHub Basics** |  |
| --- | --- |
| 📥 `git remote add origin <repository-url>` | Link local repository to a remote GitHub repository |
| 🚀 `git push -u origin <branch>` | Push changes to GitHub for the first time |
| 📥 `git pull origin <branch>` | Pull changes from GitHub repository |
| 📥 `git clone <repository>` | Clone a GitHub repository to your local machine |
| 🍴 `git fork` | Create a personal copy (fork) of a repository |
| ⚡ `git pull-request` | Create a pull request for changes to be merged |

| **Collaboration and Pull Requests** |  |
| --- | --- |
| 📥 `git fetch origin` | Fetch remote changes without merging |
| 🔀 `git rebase origin/<branch>` | Rebase local changes on top of remote changes |
| 🔀 `git pull --rebase origin <branch>` | Pull remote changes and rebase |
| 🚀 `git push origin <branch>` | Push changes to a remote branch |
| 🚀 `git pull-request` | Create a pull request for changes to be merged |
| 🔀 `git merge <branch>` | Merge changes from one branch into another |

Stay in the loop with my latest insights and articles on cloud ☁️ and DevOps 🚀 by following me on Hashnode, LinkedIn ([**linkedin.com/in/nishit1907**](http://linkedin.com/in/nishit1907)**), and GitHub (**[**github.com/NISHIT-RAJANI**](http://github.com/NISHIT-RAJANI)**).**

**Thank you for reading!** 🙏 Your support means the world to me. Let's keep learning, growing, and making a positive impact in the tech world together.