# A User's Guide to Branching

## Introduction to Branching in Git

Branching in Git lets you create separate lines of development within a project. This means you can work on new features, fix bugs, or experiment without affecting the main codebase.

## Why Branching Is Useful

- **Isolate Work**: Keep changes for a specific task separate from the main project.

- **Work in Parallel**: Multiple team members can tackle different tasks simultaneously without interfering with each other.

- **Safe Experimentation**: Test new ideas without risking the stability of the main project.

- **Organized Collaboration**: Facilitate code reviews and discussions by keeping changes related to a specific feature or fix in their own branch.

## Understanding Branches in Git

In Git, a branch is a pointer to a specific commit, representing a distinct line of development. Since 2020, the default branch is usually named `main`. Previously, it was `master`. Creating a new branch allows you to develop independently from other branches.

## Basic Branching Commands

### Create a New Branch

To create a branch named `feat/new_feature` off of the commit we are currently on:

```bash
git branch feat/new_feature
```


This command creates the branch but doesn't switch to it.

### Switch Between Branches

To switch to the newly created branch:

```bash
git checkout feat/new_feature
```


Alternatively, create and switch to a new branch simultaneously:

```bash
git checkout -b feat/new_feature
```


### View All Branches

To list all branches:

```bash
git branch
```


The current branch is marked with an asterisk (*).

### Rename a Branch

While on the branch you want to rename:

```bash
git branch -m new-branch-name
```


To rename a different branch:

```bash
git branch -m old-branch-name new-branch-name
```


### Delete a Branch

After merging a branch, you can delete it:

```bash
git branch -d feat/merged_branch
```


To force delete a branch, regardless of its merge status:

```bash
git branch -D feat/unmerged_branch
```


## Merging Branches

Once you've completed work in a branch, merge it back into the main branch.

1. Switch to the target branch (e.g., `main`):

   ```bash
   git checkout main
   ```


2. Merge the feature branch:

   ```bash
   git merge feat/completed_feature
   ```


If there are no conflicts, Git will integrate the changes. Otherwise, you'll need to resolve conflicts manually.
