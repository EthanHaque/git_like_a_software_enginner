# Resolving Merge Conflicts in Git

## Introduction

In Git, a **merge conflict** occurs when changes from different branches cannot be automatically combined. This usually happens when two branches modify the same line or when one deletes a file the other edits. Knowing how to resolve conflicts is essential in collaborative workflows.

## Scenario: Simulating a Merge Conflict

Let’s walk through a conflict resolution example.

1. **Initialize a Repository:**

   ```bash
   mkdir git_merge_conflict_demo
   cd git_merge_conflict_demo
   git init
   ```

2. **Create a File and Make the First Commit:**

   ```bash
   echo "Initial content" > example.txt
   git add example.txt
   git commit -m "feat: add example.txt with initial content"
   ```

3. **Create and Switch to a Feature Branch:**

   ```bash
   git checkout -b feat/update_example_text
   ```

4. **Edit the File and Commit in the Feature Branch:**

   ```bash
   echo "Change from feat/update_example_text" > example.txt
   git commit -am "feat: modify example.txt in feat/update_example_text"
   ```

5. **Switch to Main and Make a Conflicting Change:**

   ```bash
   git checkout main
   echo "Change from main branch" > example.txt
   git commit -am "feat: modify example.txt in main"
   ```

## Merging and Hitting a Conflict

Try merging the feature branch into `main`:

```bash
git merge feat/update_example_text
```

You’ll see output like:

```
Auto-merging example.txt
CONFLICT (content): Merge conflict in example.txt
Automatic merge failed; fix conflicts and then commit the result.
```

## Resolving the Conflict

1. **Check for Conflicts:**

   ```bash
   git status
   ```

   Output will show:

   ```
   both modified: example.txt
   ```

2. **Edit the File to Resolve the Conflict:**

   The file will look like:

   ```
   <<<<<<< HEAD
   Change from main branch
   =======
   Change from feat/update_example_text
   >>>>>>> feat/update_example_text
   ```

   Decide what to keep. For example:

   ```
   Change from main branch
   Change from feat/update_example_text
   ```

   Then delete the conflict markers.

3. **Mark It as Resolved:**

   ```bash
   git add example.txt
   ```

4. **Commit the Merge Resolution:**

   ```bash
   git commit -m "fix: resolve merge conflict in example.txt"
   ```
