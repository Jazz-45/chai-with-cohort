# Git for Beginners

If you read the previous blog, _Why Version Control Exists: The Pendrive Problem_, you already understand **why** developers needed a system like Git.

In this blog, we will focus on **what Git is**, **how it thinks**, and **how to use it with essential commands** in a beginner-friendly way.

---

## What is Git?

Git is a **distributed version control system** used by developers to track changes in source code over time.

In simple words, Git helps you:

- Keep a history of your code
- Know what changed and when
- Work safely with multiple developers
- Go back to older versions if something breaks
    

Git is the **most widely used version control system** in the software industry today.

---

## How Does Git Track Code Internally?

To understand Git better, let’s think like a developer who is trying to **build Git from scratch**.

### The Core Problem

If we want to track changes in code, we must answer one basic question:

**Where do we store the changes?**

As developers, our first thought might be:

- A database
- Some external server
    

But thinking more simply, code itself is just **text**.

So instead of storing entire files again and again, we can:

- Store differences between versions
- Save snapshots at specific points in time
    

Even a simple text file could theoretically log changes.

Now another question arises.

**Where should this tracking data live?**

If it lives outside the project, tracking becomes messy.  
So the best place is **inside the project itself**.

---

## Git’s Solution: The `.git` Folder

Git solves this problem by creating a hidden folder named `.git` inside your project directory.

This folder:

- Stores the complete history of your project
- Tracks changes
- Keeps metadata about commits, branches, and files
    

When you run `ls`, you may not see it.  
When you run `ls -a`, you will see `.git`.

This is how Git keeps everything organized without interfering with your actual code.

---

## When Should Git Track Changes?

Another important question Git had to solve was:

Should changes be tracked:

- Character by character?
- Line by line?
- Automatically every few seconds?
    

Git gives **full control to the developer**.

You decide:

- What to track
- When to save changes
- Which changes matter
    

This is done using Git’s **staging and commit workflow**.

---

## Git’s Simple Workflow

Git works in three main steps:

1. You make changes in your files
2. You select which changes you want to save
3. You permanently record those changes
    

This is done using:

- Working Directory
- Staging Area
- Repository
    

You can modify many files, but only the files you **stage** will be saved in the next commit.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1768492154109/af4c9b0d-d2f6-481a-8c31-88710e7906ce.png)

---

## Git Basics and Core Terminologies

### Repository

A repository is a project folder that Git is tracking.  
Once Git is initialized, the folder becomes a Git repository.

---

### Commit

A commit is a **saved checkpoint** of your code.  
Each commit represents a meaningful change.

Think of it like:

> “Save progress with explanation.”

---

### Branch

A branch allows you to work on features independently without affecting the main code.

For beginners:

- You can think of a branch as a separate timeline of changes

---

### HEAD

HEAD is a pointer that tells Git **where you are currently working** in the commit history.

Usually, HEAD points to the latest commit.

---

## Essential Git Commands

Now let’s look at the most important Git commands that every beginner must know.

---

### `git init`

This command initializes Git in your project.

What it does:

- Creates the `.git` folder
- Starts tracking the project
    

After this, your folder becomes a Git repository.

---

### `git status`

This command tells you the current state of your project.

It shows:

- Modified files
- Staged files
- Untracked files
    

This is the **most used Git command** while working.

---

### `git add`

This command moves changes to the **staging area**.

You are telling Git:

> “These changes are ready to be saved.”

`git commit`

This command permanently saves staged changes into Git history.

Each commit should describe **what and why**, not just “update”.

---

### `git log`

This command shows the history of commits.

You can see:

- Commit IDs
- Author 
- Date
- Commit messages
    

This is how Git remembers everything.

---

## A Simple Git Workflow Example

1. Create a project folder
2. Run `git init`
3. Create or modify files
4. Check status using `git status`
5. Stage changes using `git add`
6. Save changes using `git commit`
7. View history using `git log`
    

This is the **basic Git cycle** used daily by developers.

---

## Why Git is So Powerful

Git does not just save files.  
It saves **intent, history, and collaboration context**.

Mistakes are reversible.  
Changes are traceable.  
Collaboration becomes safe.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1768492306083/40a616c2-79e8-4e39-a71a-07de08f49c0c.png)

---

## What Comes Next

Now you know:

- What Git is
- Why Git is used
- How Git tracks changes
- How to use essential Git commands
    

But one question remains.

**What exactly is inside the** `.git` folder?  
How does Git store commits, branches, and history internally?

That is what the **next blog** will explore.