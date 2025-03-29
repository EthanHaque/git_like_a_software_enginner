## Bonus Git Tips

Here are a few extra tips and tricks to make your Git workflow faster and more pleasant.

### 1. Use Git Aliases to Save Time

Typing out long Git commands repeatedly can get tedious. Git aliases let you define short forms for commonly used commands.

You can add these to your `~/.gitconfig` under the `[alias]` section:

```ini
[alias]
    a = add
    c = commit --verbose
    ca = commit --verbose --amend
    cam = commit --verbose --amend --no-edit
    cm = commit -m
    co = checkout
    cob = checkout -b
    d = diff
    lol = log --graph --decorate --pretty=oneline --abbrev-commit
    lola = log --graph --decorate --pretty=oneline --abbrev-commit --all
    pl = pull
    ps = push
    s = status
```

> These are some of my personal, useful aliases.

**Examples**:
- `git co` → switch branches
- `git cam` → amend last commit without changing the message
- `git lol` → view commit history as a graph

---

### 2. Reuse Commits with Cherry-Pick

Want to apply a specific commit from another branch?

```bash
git cherry-pick <commit-hash>
```

Useful when you want to port a fix without merging the whole branch.

---

### 3. Clean Up Local Branches

After merging branches, delete them to keep things tidy:

```bash
git branch -d feature/some-branch
```

To delete all local branches that have been merged into the current branch (usually `main`), you can run:

```bash
git branch --merged | grep -vE '^\*|main' | xargs -n 1 git branch -d
```

### Explanation:
- `git branch --merged`: lists branches that are fully merged.
- `grep -vE '^\*|main'`: excludes the current branch (`*`) and `main`.
- `xargs -n 1 git branch -d`: deletes each listed branch.

> Always double-check that you're not deleting important branches. I'm lazy so I do this, but I probably wouldn't recommend doing this unless you really understand what's going on.


To clean up remote-tracking branches that no longer exist:

```bash
git fetch --prune
```
---

### 4. Recover Lost Work with `git reflog`

Accidentally deleted a branch or commit? Use `git reflog` to view the history of your HEAD and branch movements:

```bash
git reflog
```

You'll see a list of recent actions, like checkouts, commits, rebases, and resets. Each entry has a reference like `HEAD@{3}`.

To recover a lost commit or branch:

```bash
git checkout HEAD@{3}
# or create a branch from it
git checkout -b recovered-branch HEAD@{3}
```

> Reflog is especially useful after a mistaken `reset --hard`, `rebase`, or branch deletion.

---

### 5. Use `stash` for Quick Context Switching

Temporarily save uncommitted work:

```bash
git stash
```

Then get back to it later:

```bash
git stash pop
```

---

### 6. Add `.gitignore` Early

Prevent clutter in your repo by ignoring build files, logs, IDE configs, etc. You can use templates from [https://gitignore.io](https://gitignore.io) to get started.

