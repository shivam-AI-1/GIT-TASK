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














