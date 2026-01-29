
# Inside Git : How it Works Internally

If you have followed the journey so far, you already know:

- **Why version control exists** (the pendrive problem)
- **How to use Git basics and essential commands** 

In this blog, we go one level deeper.

We will not learn new commands here.  
Instead, we will understand **what Git is actually doing behind the scenes**.

The goal is simple:

> Build a clear mental model of Git.

---

## Why Look Inside Git?

Most beginners use Git like a magic tool:

- `git add`
    
- `git commit`
    
- `git log`
    

It works, but it feels mysterious.

Understanding Git internally helps you:

- Debug issues with confidence
- Understand why commands behave the way they do
- Stop memorizing and start reasoning
    

Everything we discuss in this blog lives inside one place.

---

## What Is the `.git` Folder?

When you run `git init`, Git creates a hidden folder named `.git` inside your project.

This folder is **the heart of Git**.

Your actual code lives outside `.git`.  
Git’s entire logic, history, and tracking live **inside** `.git`.

If you delete this folder, your project becomes a normal folder again.

---

## Why Does the `.git` Folder Exist?

Git needs a place to store:

- History of changes
- Commits
- Branch informatio
- File snapshots
- Metadata
    

Instead of using an external database, Git stores everything as **files and folders**.

This makes Git:

- Fast
- Portable
- Reliable
- Easy to copy
    

---

## High-Level Structure of the `.git` Folder

You do not need to memorize every file, but you should understand the purpose.

Conceptually, `.git` contains:

- Objects (actual data)
- References (pointers)
- Configuration
- Logs
    

The most important directory is `objects`.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1768544146880/470caf55-bdd0-4c64-975c-cd0386127ca9.png)

---

## Git Objects: The Building Blocks

Git internally works with **objects**.  
There are three main types you must understand.

---

### Blob (Binary Large Object)

A **blob** represents the **content of a file**.

Important points:

- Blob stores file content only
- File name is not stored here
- Same content always produces the same blob
    

If two files have identical content, Git stores only one blob.

---

### Tree

A **tree** represents a **directory structure**.

It maps:

- File names → blobs
- Folder names → other trees
    

Think of a tree as:

> A snapshot of a folder at a point in time.

---

### Commit

A **commit** ties everything together.

A commit contains:

- A reference to a tree
- A reference to the parent commit
- Author information
- Commit message
- Timestamp
    

A commit does **not** store file content directly.  
It points to a tree, which points to blobs.

---

## Relationship Between Commit, Tree, and Blob

The hierarchy looks like this:

Commit  
→ Tree  
→ Blob(s)

This design allows Git to:

- Reuse unchanged data
- Save space
- Track history efficiently
    

---

## How Git Tracks Changes

Git does **not** track files the way you see them.

It tracks:

- Content
- Snapshots
- Relationships between objects
    

When a file changes:

- A new blob is created
- Only changed data is stored
- Old blobs remain untouched
    

This is why Git is fast and reliable.

---

## What Happens During `git add`

When you run `git add`:

1. Git reads the file content
2. Creates a blob object
3. Stores it inside `.git/objects`
4. Updates the staging area
    

At this stage:

- Changes are **prepared**
- Nothing is saved permanently yet
    

Staging is Git asking:

> “Are you sure you want to record this?”

---

## What Happens During `git commit`

When you run `git commit`:

1. Git creates a tree from staged files
2. Creates a commit object
3. Links it to the previous commit
4. Moves HEAD to the new commit
    

Now the snapshot is **permanent**.

Nothing is ever overwritten.  
Git only adds new objects and pointers.

---

## How Git Uses Hashes

Every Git object is identified by a **hash**.

This hash is:

- Generated from object content
- Unique
- Deterministic
    

Why hashes matter:

- Same content → same hash
- Any change → new hash
    

This guarantees:

- Data integrity
- Tamper detection
- Reliable history
    

If even one character changes, the hash changes.

---

## Why This Design Is Powerful

Because of this internal structure:

- Git can detect corruption
- History cannot be silently modified
- Collaboration is safe
- Rollbacks are reliable
    

Git is not just tracking files.  
It is tracking **truth**.

---

## Building the Right Mental Model

Instead of thinking:

> Git saves files

Think:

> Git saves snapshots made of objects, linked by hashes

Once this clicks:

- Commands make sense
- Errors become understandable
- Git stops feeling random
    

---

## How This Connects to What You Already Know

- `git add` prepares objects
    
- `git commit` records relationships
    
- `git log` walks through commit pointers
    
- HEAD is just a reference to a commit
    

Everything traces back to `.git`.

---

## What You Should Take Away

You do not need to memorize Git internals.

You only need to remember:

- `.git` is the database
- Objects store content
- Commits link history
- Hashes ensure integrity
    

This understanding will help you far more than memorizing commands.