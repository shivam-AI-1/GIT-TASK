# Task 1 : Install and configure Git

## step 1 : Install Git

## step 2: Configure Git : 

Once Git is installed, Connect it with your username and email to track your contributions.

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

## step 3: Verify your connection

to check your configuration settings run

```bash
git config --list
```




# Task 2: Initialize a Repository

### step 1: Create a new project folder 
First, create a new folder where your project will be stored. You can name it whatever you like. For example, we'll create a folder named `MyProject`.

```bash
mkdir new_folder
```
### step 2: go inside the new folder using the cd command

```bash
cd new_folder
```

### step 3:Initialize a git repository 
To initialize Git in your project folder, run the following command:
```bash
git init
```
This command sets up an empty Git repository in the MyProject folder





# Task 3: Create a File and Make Multiple Commits


### Step 1: Create a New File and Add Content

First, create a new file named README.md with the following content:

```bash
echo "My First Project" > README.md
```

### Step 2: Stage the File

We need to stage the file. Staging means telling Git that you want to include this file in the next commit.

```bash
git add README.md
```

### Step 3: Commit the File

After staging the file,commit the to Git repository 

```bash
git commit -m "Initial commit: Added README.md" 
```
The -m option allows you to provide a message for the commit. 

### Step 4: Make Changes to the File

Add another change to README file 

```bash
echo "Added a description" >> README.md 
```

### step 5: Stage and commit the changes:

Once you've made the changes, you need to stage and commit them again.

```bash
git add README.md
git commit -m "Updated README with a description"
```







# Task 4: Check Status and Log

### Step 1: Check the repository’s current status:-

The `git status` command provides information about the state of your working directory and staging area

To check the current status of your repository, run:

```bash
git status
```


### Step 2: View commit history in detail:

To view commit history use :-

```bash
git log --oneline --graph --decorate
```

## What does git log --oneline --graph --decorate do?
`git log:` This command shows the history of all commits (changes) made in your project.

`--oneline:` This makes the log display each commit in a single line. You'll see a short version of the commit ID (hash) and the commit message.

`--graph:` This adds a simple, visual tree (graph) to show the branches and how they are connected, like a flowchart of your commits.

`--decorate:` This shows the names of branches, tags, or other references, so you can see which commit is currently the latest or where a branch is pointing.








# Task 5: Create and Clone a Repository

### Step 1: Create a repository on Github

1. Login to your account in Github 
2.  In the upper-right corner, click on the **+** icon, then select **New repository**.
3.   Name your repository `example-repo`.
4.    Click **Create repository**.

### Step 2: Clone the Repository Locally

Once your GitHub repository is created, you need to clone it to your local machine to start working with it.

**Open your terminal (or Git Bash) and navigate to the directory where you want to clone the repository.**

Run the following command to clone the repository:
```bash
git clone http://codinggita.com/example-repo
```










# Task 6: Understanding the Git Workflow

### Step 1: Make changes to a file in the working directory

create a new file called `workflow.md` and add some content to it:

```bash
echo "Workflow example" > workflow.md
```

### Step 2: Stage the File

Before committing the file to the repository, you need to stage it using the git add command.

```bash
git add workflow.md
```

### Step 3: Commit the File to the Repository

Once the file is staged, you can commit it to the local repository with a commit message.

```bash
git commit -m "Added workflow example"
```



# PART 2: WORKING WITH REPOSITORIES-


## TASK 7: Branching and Merging-

### step 1: Create a New Branch for a Feature:
To create a new branch for a feature, use the following commands:
```bash
 git branch feature-login
```

Swtich to newly created branch by using  `checkout`
```bash
git checkout feature-login
```

Alternatively we can create and swtich to other branch using 
```bash
git checkout -b feature-login
```

This command creates a new branch called feature-login and switches to it, where you'll add your feature

### Step 2: Add a new file and commit changes:

create a new file and commit it to the feature-login branch. 

```bash
echo "Login Page" > login.html 
```

then we add the file to the stagin area that is to comitted by using 

```bash
git add login.html
```


Commit the changes with a descriptive message:

```bash
git commit -m "Added login page"
```


### Step 3: Merge the feature branch into main

it's time to merge it back into the main branch.

1. Switch to the main branch:
```bash
git checkout main
```


2. Merge the feature-login branch into main:

```bash
git merge feature-login
```






## task 8:  Handling Merge Conflicts

### Step 1: Create two branches:

`Merge conflicts` occur when Git cannot automatically resolve changes made to the same part of a file in different branches

Start by creating two branches:
```bash
git branch branch-A
git branch branch-B
```
### Step 2: Modify the Same Line in Both Branches

1. Switch to branch-A and edit README.md:
```bash
git checkout branch-A
echo "This is branch-A content" > README.md
git add README.md
git commit -m "Added content from branch-A"
```

2. Switch to branch-B and edit the same line in README.md

```bash
git checkout branch-B
echo "This is branch-B content" > README.md
git add README.md
git commit -m "Added content from branch-B"
```


### Step 3: Merge branch-A into main

1. Switch to the main branch:

```bash
git checkout main
```

2. Merge branch-A into main:

```bash
git merge branch-A
```

At this point, the changes from branch-A are successfully merged into main.


### Step 4: Attempt to Merge branch-B into main

1. While on the main branch, merge branch-B


```bash
git merge branch-B
```
This will result in a merge conflict because both branch-A and branch-B modified the same line in README.md.

## Step 5: Resolve the Merge Conflict

Stage the resolved file:

```bash 
git add README.md
```

commit the resolved file:

```bash
git commit -m "Resolved merge conflict between branch-A and branch-B"
```




# Task 9: Renaming and Deleting Branches-

## Renaming a branch :-

To rename an existing branch:

```bash
git branch -m old-branch-name new-branch-name
```

-m: This flag stands for "move" or "rename."

## Deleting a Branch
To delete a branch that is no longer needed:

```bash
git branch -d branch-name
```
-d: This deletes the branch only if it has been fully merged into the current branch or its parent.






# Part 3: Advanced Git Operations

## Task 10: Using Git Stash


### Step 1: Make Changes Without Committing-

Create a file in your working Directory 
```bash
echo "Temporary work" >> temp.md
```
## Step 2: Stash the Changes-

git stash is a Git command used to temporarily save (stash) changes in your working directory that you don't want to commit yet.

Save your uncommitted changes (both staged and unstaged) in a stash:

```bash
git stash 
```

### Step 3: View Stashed Changes
Check the list of all stashes saved in your repository:


```bash
git stash list
```

### 4. Apply Stashed Changes

Reapply the most recent stash to your working directory without removing it from the stash list:


```bash
git stash apply
```

### 5. Drop the Stash After Applying

Remove the applied stash from the stash list:

```bash
git stash drop

```







## Task 11: Rewriting History with Interactive Rebase

### Step 1: Create multiple commits:

Start by creating three separate commits to demonstrate the process:


**Create the first commit**
```bash
echo "Commit 1" > file1.txt && git add file1.txt && git commit -m "Commit 1"
```

**Create the second commit**

```bash
echo "Commit 2" > file2.txt && git add file2.txt && git commit -m "Commit 2"
```

**Create the third commit**
```bash
echo "Commit 3" > file3.txt && git add file3.txt && git commit -m "Commit 3"
```

### Step 2: Start an interactive rebase

To combine the last three commits into one, use the following command:
```bash
git rebase -i HEAD~3
```
This opens an interactive editor displaying the last three commits.

**To squash commits, replace the word pick with squash for the second and third commits:**
```bash
pick <hash1> Commit 1
squash <hash2> Commit 2
squash <hash3> Commit 3
```

Save and close the editor.






# Task 12: Cherry-Picking Commits

### 1. Create a New Branch

Before cherry-picking, create a new branch to work on:

```bash 
git checkout -b cherry-pick-example
```
This switches to a new branch named cherry-pick-example.

### 2. Cherry-pick a specific commit from another branch:

To cherry-pick a specific commit:

```bash
git cherry-pick <commit-hash>
```

Replace `commit-hash` with the hash of the commit you want to apply.






# Task 13: Tagging Commits

**Tagging in Git is used to mark specific points in your commit history, often for marking release versions (e.g., v1.0, v2.0).**

#### Step 1: Tag the Current Commit

To tag the latest commit:
```bash
git tag -a v1.0 -m "Version 1.0 release"
```

`v1.0`: The name of the tag.

`-m "Version 1.0 release"`: A message describing the purpose of the tag.

`-a`:Annotated tags store additional information , such as The tagger's name, Email , The date the tag was created, A message describing the tag's purpose.

### Step 2:Push the tag to the remote repository:
After creating a tag locally, you need to push it to the remote repository:

``` bash
git push origin v1.0
```

This pushes the tag v1.0 to the remote repository.


# Task 14: Working with Remote Repositories

### Step 1: Add a remote repository:

To link your local repository to a remote one, use the `git remote add` command.

```bash
git remote add <name> <repository-url>
```

`origin:` The default name for the remote repository.
`repository-url:` The URL of the remote repository (e.g., GitHub, GitLab).


### Step 2: Push your changes to the remote repository:


After adding the remote, push your changes to it using git push.

```bash
git push origin main
```

`origin:` Refers to the remote repository added earlier.
`main:` The branch to which you are pushing changes.






# Task 15: Forking and Contributing


## Step 1: Fork a Repository on GitHub
1. Navigate to the repository you want to contribute to on GitHub.
2. Click the **Fork** button at the top-right of the page.
3. Select your GitHub account to create a copy of the repository in your account.

## Step 2: Clone the Forked Repository Locally
After forking the repository, clone it to your local machine to start working on it.

```bash
git clone <forked-repo-url>
```

## Step 3: Create a New Branch for Your Changes

This helps to keep the main branch clean and organized.

```bash
git checkout -b fix-typo
```
## Step 4: Make Changes and Commit

After switching to your new branch, make the necessary changes to the files, and commit them.

```bash
echo "Typo fixed" >> README.md
git add README.md
git commit -m "Fixed a typo"
```

## Step 5: Push Your Changes to the Forked Repository

Once your changes are committed, push them to your remote forked repository on GitHub.

```bash
git push origin fix-typo
```

## Open a Pull Request (PR)

1. Go to your forked repository on GitHub.
2. You will see a Compare & Pull Request button. Click it.
3. Provide a meaningful title and description for your changes.
4. Submit the pull request to the original repository.








# Task 17: Git Ignore

## Step 1: Create a .gitignore file:

To create a .gitignore file that ignores specific files (like node_modules/), you can use the following command:

```bash
echo "node_modules/" > .gitignore
```

This will create a .gitignore file and add node_modules/ to it, which tells Git to ignore the node_modules directory.

## Step 2: Add files and ensure ignored files are not staged:

After creating the .gitignore file, you can add the files in your repository, but files listed in .gitignore (like node_modules/) will not be staged. To add the files that are not ignored, use:

```bash
git add .
```
This will add all files that are not ignored by .gitignore to the staging area.











































































