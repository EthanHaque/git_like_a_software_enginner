# Understanding Git: Foundational Design Principles

## Why Git Was Created

Git was created in 2005 by Linus Torvalds in response to the Linux kernel community's need for a reliable, efficient, and distributed version control system (VCS). Prior to Git, the community relied on BitKeeper, a proprietary VCS that was available to them under a special free license. This arrangement ended when the license was revoked, prompting the search for an alternative solution.

Torvalds evaluated existing open-source VCS options but found them lacking in critical areas such as performance, scalability, and support for distributed workflows. This led him to develop Git with specific design goals:


### Core Objectives
- **High Performance**: Git was engineered to handle large projects like the Linux kernel efficiently. Torvalds emphasized speed, aiming for operations take no more than a few seconds.

- **Data Integrity**: Git employs cryptographic methods to protect the repository's history from both accidental corruption and malicious tampering.

- **Distributed Development**: Git was designed to support distributed workflows. Each developer has a complete copy of the repository, allowing for independent work and reducing reliance on a central server.

- **Support for Non-Linear Development**: Git provides robust branching and merging capabilities, facilitating parallel development and simplifying the integration of changes from multiple contributors.

Git is not the only VCS system available, but it is by far the most popular. See [Mercurial](https://en.wikipedia.org/wiki/Mercurial).

## Key Concepts

### Common Beginner Workflow: `git add`, `git commit`, `git push`

Most developers are first introduced to Git through a simple three-step workflow:

1. `git add`: Stages changes for commit.
2. `git commit`: Records a snapshot of the staged changes.
3. `git push`: Sends local commits to a remote repository.

```bash
git add .
git commit -m "Your message here"
git push
```

To be honest, this workflow can get you very far. However, getting stuck here causes lots of unnecessary anguish as your version control needs become more complex.


### The Staging Area (Index)
Intermediate step between working directory and repository.

- Allows fine-grained control of what gets committed.

```bash
git add file1.txt
git commit -m "feat: bump vesion"
```

### What Is a Git Commit?

A **commit** in Git creates a snapshot of the staged changes and permanently records them in the repository. Each commit becomes a node in your project's history graph.

A commit stores:
- A snapshot of the project's files
- The author and timestamp
- A message describing the change
- A reference to its parent commit(s), forming a chain of history

Each commit is identified by a unique, 160-bit SHA-1 hash, which is calculated from its content and metadata. This ensures integrity—any change to the commit changes its hash.

#### How to Make a Commit

After staging changes:

```bash
git commit -m "fix: change foo to bar"
```

This creates a new snapshot with a pointer to the current state and a link to its parent (the previous commit). Over time, these linked commits form a directed acyclic graph (DAG), representing your project's full history.

#### Viewing Commit History

Use `git log` to inspect commits:

```bash
git log
```

This shows hashes, authors, dates, and messages, helping you understand the evolution of the codebase.


