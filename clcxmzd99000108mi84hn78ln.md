# Introduction To Git

---

---

# What is GIT?

Git is a free and open-source distributed version control system, which is designed to handle everything from small to very large projects with speed and efficiency.

## So Why Git? What are the advantages?

### Imagine a scenario without using Git.

There is a large project and 100 developers are working on the project.

* Developers used to submit their codes to the central server without having a copy of their own.
    
* Any changes made to the source code were not known to the other developers.
    
* There was no communication between any of the developers.
    

### Now, let's analyze the scenario after using Git.

* Every developer has an entire copy of the code on their local system.
    
* Any change made to the source code can be tracked by others.
    
* There is regular communication between the developers.
    

---

### **Uses of Git.**

* Git is used to track changes in the source code.
    
* Distributed version control tool used for source code management.
    
* Allows multiple developers to work together.
    
* Supports non-linear development because of its thousands of parallel branches.
    

### Features of Git.

* Free and open-source
    
* Tracks history
    
* Supports non-linear development
    
* Creates backup Scalable
    
* Supports collaboration
    
* Branching is easier
    
* Distributed development.
    

### Git WorkFlow.

**In Git, the workflow is mainly divided into three areas-:**

* **Working directory -** This is the area where you modify your existing files.
    
* **Staging area (Index) -** In this, the files in your working directory are staged and snapshots are added.
    
* **Git directory or repository -** It is basically where you perform all the changes that need to be made i.e. perform commits to a branch, checkout a branch, make changes etc.
    

### Installation in Windows/Linux/Mac OS.

**Install Git on Windows:-**

* Download the latest version of Git from here.
    
* After starting the installer, follow the command on the screen and press Next to complete the installation.
    
* Open Command Prompt and run the following command to configure Git on your PC using your username and email.
    

```bash
$ git config --global user.name "username"

$ git config --global user.email "user_emails@interviewbit.com"
```

**Install Git on Linux -**

* You can install Git on Linux using the command apt-get.
    

```bash
$ sudo apt-get update
$ sudo apt-get install git
```

* Configure your username and email using the following command:
    

```bash
$ git config --global user.name "user_name"
$ git config --global user.email "user_email@interviewbit.com"
```

**Install Git on Mac OS -:**

* Download the latest version of Git from here.
    
* Open the installer and follow the instructions.
    
* Now since Git is installed, open a command line and configure your username and user email.
    

```bash
$ git config --global user.name "user_name"
$ git config --global user.email "user_email@interviewbit.com"
```

---

## Git Clone.

git clone is a command which is used to clone or copy a target repository.

**How to clone a repository?**

* Open GitHub and navigate to the target repository which needs to be cloned.
    
* Under the repo name, click on the tab Clone or Download.
    
* An option named Clone with HTTPS appears.
    
* Copy the Clone URL. Open a command line and use the command: git clone &lt;repo\_URL&gt;
    
* In this way, a clone of the target repository can be made.
    

**Clone a specific branch from the repository.**

A very useful feature of the git clone is that it allows cloning a specific branch of the target repository without having to clone the entire repository. To clone a specific branch, you need to use the command -b to specify the branch. The following command is used:

```bash
git clone -b <Branch_name> <Repo_URL>
```

---

## Git Branch.

* A branch in Git is used to keep your changes until they are ready.
    
* You can do your work on a branch while the main branch(main) remains stable. After you are done with your work, you can merge it into the main branch.
    

**For creating a new branch, the following command is used :**

```bash
git branch <branch_name>
```

**Git Switch Branch:**

Using the git checkout command, we can switch from one branch to another. Command:

```bash
git checkout <branch_name>
```

---

## Create Remote Branches.

Git doesn’t allow creating a new and isolated branch on a remote repository. But, if you to make a branch remote, we can push an existing local branch.

The steps to create a remote branch are as follows:

* Create a local branch and switch to that branch.
    
* Push in the local branch.
    
* **Note:** origin is the default name of the remote.
    
* Now, if someone wants to fetch some information, one can simply run:
    

```bash
git fetch

git checkout <branch_name>
```

---

## Delete Branches.

Once the work is done on a branch and merged with the Main branch, one can delete the branch.

The following command is used to delete branches:

```bash
git delete -d <branch_name>
```

> Note: This command deletes a copy of the branch, but the original branch can still exist in remote repositories.

**To delete remote branches, use the following command:**

```bash
git push origin --delete <branch_name>
```

---

## GIT Status.

**git status** is mainly used to display the state of the staging area and the repository. It helps us to track all the changes made and point out untracked files.

Command:

```bash
git status
```

---

## Git Commit.

Git commit is used to record all the changes in the repository. The git commit will commit all the changes and make a commit-id for the same for tracking down the changes made.

The command git commit creates a commit-id to track down changes and commits all the changes to the git repository.

Command:

```bash
git commit
```

**git commit -m**

The -m along with the command lets us write the commit message on the command line.

Command:

```bash
git commit -m "Commit message"
```

**git commit -am**

The -am along with the command is to write the commit message on the command line for already staged files.

Command:

```bash
git commit -am "Commit message"
```

**git commit -amend**

The amend is used to edit the last commit. In case we need to change the last committed message, this command can be used.

Command:

```bash
git commit -amend
```

**git rm**

rm stands for remove. It is used to remove a collection of files. The git rm command is used to remove or delete files from the working tree and index.

Command:

```bash
git rm <file_name>
```

---

## Git Merge.

Git merge is a command that allows you to merge branches from Git. It preserves the complete history and chronological order and maintains the context of the branch.

we can create different features by branching from the main branch and how we can merge the newly created features after the final review to the main branch.

The command **git merge** is used to merge the branches.

```bash
git merge <branch_name>
```

---

## GIT Rebase.

Git Rebase is a process of combining a sequence of commits to a new base commit.

* The primary reason for rebasing is to maintain a linear project history.
    
* When you rebase, you ‘unplug’ a branch and ‘replug’ it on the tip of another branch(usually main).
    
* The goal of rebasing is to take all the commits from a feature branch and put them on the main branch.
    
* The following rebase command is used for rebasing the commits:
    

```bash
git rebase <branch_name>
```

---

## Git Fetch.

**Git Fetch** only downloads the latest changes into the local repository. It downloads fresh changes that other developers have pushed to the remote repository since the last fetch and allows you to review and merge manually at a later time using **Git Merge**. As it doesn’t change the working directory or the staging area, it is safe to use.

The working of the command git fetch. It fetches all the latest changes that have been made in the remote repository and lets us make changes accordingly.

Command:

```bash
git fetch <branch_name>
```

---

## Git Stash.

Sometimes in large codebases, there might be some cases when we do not want to commit our code, but at the same time don’t want to lose the unfinished code. This is where git stash comes into play. The git stash command is used to record the current state of the working directory and index in a stash.

It stores the unfinished code in a stash and cleans the current branch from any uncommitted changes. Now, we can work on a clean working directory.

If in the future, we again need to visit that code, we can simply use the stash and apply those changes back to the working repository.

With the command **git stash**, we can temporarily stash the changes we have made on the working copy and can work on something else. Later, when needed, we can **git stash** pop and again start working on it.

**How do stash changes in Git?**

The syntax for stashing is as follows:

```bash
git stash
```

Suppose, you are working on a website and the code is stored in a repository.

Now let's say, you have some files named design.css and design.js. Now you want to stash these files so that you can again use them later, while you work on something else.

Therefore, later you can use the **git stash list** command to view all the changes.

**Drop Stash**

In case, you no longer require a stash, you can delete it with the following command:

```bash
git stash drop <stash_id>
```

If you want to delete all the stashes, simply use:

```bash
git stash clear
```

---

## Git-Ignore.

At times, there are some files that we might want Git to ignore while committing. For example, private files or folders containing passwords, APIs etc. These files are user-specific and hence, we can ignore these using the **.gitignore**.

**.gitignore** is generated automatically inside the project directory and ignores the files to get committed to the repositories.

**How to use the .gitignore?**

Follow the below steps to use add the files you want Git to ignore.

* Open your project directory on your PC.
    
* Create a **.gitignore** file inside it.
    
* Inside the **.gitignore** write the names of all the files you want Git to ignore.
    
* Now add the **.gitignore** in your repository.
    
* Now, if you check the status of your repo, you will see, all the files which were written in the **.gitignore** file have been ignored.
    

---

## Advanced Git Concepts.

### git pull --rebase

Git rebase is used to rewrite commits from one branch to another branch. To combine unpublished local changes with the published remote changes, a **git pull** is performed.

With git **pull --rebase**, the unpublished changes will be again applied to the published changes and no new commit will be added to history.

### git merge --squash

The **squash** along with git merge produces the working tree. It indexes in the same way as that of the real merge but discards the merge history.

Command:

```bash
git merge --squash origin/main
```

When to use **git merge --squash**?

1. When you have merged main into your branch and resolved conflicts.
    
2. When you need to overwrite the original commits.
    

### git reflog

The **reflog** records every change that is made in the repository. Apart from this, if some branch is lost from the repo, the recovery can be done using this command.

Command:

```bash
git reflog
```

### git revert

Revert simply means to undo the changes. Therefore, it is an undo command in Git. Unlike traditional undo operations, the revert command does not delete any data. git revert is a commit operation, as it undoes the specified commit.

Command:

```bash
git revert
```

**Options:**

**Revert commit:**

This option is used to revert a commit.

Command:

```bash
git revert <commit_id>
```

**Edit commit message before reverting commit:**

In case, we want to edit the commit message before reverting, -e is used for the same.

Command:

```bash
git revert -e <commit_id>
```

### git bisect

Git bisect is a git tool used for debugging. Suppose, you have a large codebase and some commit causes a bug, but you are not sure of which commit causes it.

Git bisect goes through all the previous commits and uses binary search to find the bugged commit.

The **git bisect** command is used to find the bisect position as shown. It bisects (divides) your history between the good and the bad commit range. It then moves through every commit id between this range and at each snapshot it allows you to test the code.

It is applied as follows:

* **git bisect start** - Starts the bisect
    
* **git bisect good v1.0** - Mention the last working commit.
    
* **git bisect bad** \- Mentioning that the current commit has a bug.
    
* It will return the commit which causes the bug and one can debug the issue efficiently.
    

### git blame

git blame is used to know who/which commit is responsible for the latest changes in the repository. The author/commit of each line is visible through this.

Command:

```bash
git blame <file_name>
```

This command shows the commits which are responsible for changes in all lines of code.

### git cherry-pick

Choosing a commit from one branch and applying it to another is known as **cherry-picking** in Git.

Following are the steps to **cherry-pick** a commit:

* Visit the branch you want to apply to commit and use the following command:
    

```bash
git switch master
```

* Run the following command:
    

```bash
git cherry-pick <commit_id>
```

---

# Conclusion

So, we learned how Git makes managing large software codebases easier, how you can commit changes, clone the repository, how branches work and many git commands that reduce the burden from the lives of developers.