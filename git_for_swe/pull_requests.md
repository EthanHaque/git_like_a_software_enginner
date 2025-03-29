## Creating Pull Requests in Git

A **pull request (PR)** is a way to propose changes from one branch into another—typically from a feature branch into `main`—on Git-based platforms like GitHub, GitLab, or Bitbucket. It facilitates code review, discussion, and approval before merging, helping maintain code quality and collaboration.

### Pull Requests and Merges

While a **merge** is the underlying Git operation that integrates code, a **pull request** is a platform-level feature that wraps that process in a workflow. A PR allows:

- Reviewing code changes before they’re merged
- Discussing improvements or concerns
- Running tests and checks automatically
- Linking related issues or work items

### Example: Creating a Pull Request on GitHub

#### 1. Fork and Clone the Repository (if needed)

```bash
git clone https://github.com/your-username/repo-name.git
cd repo-name
```

#### 2. Create a New Branch

```bash
git checkout -b feat/add-search-bar
```

#### 3. Make and Commit Your Changes

```bash
# Edit files as needed
git add .
git commit -m "feat: add search bar to homepage"
```

#### 4. Push the Branch to GitHub

```bash
git push origin feat/add-search-bar
```

#### 5. Open the Pull Request

1. Go to the original repository on GitHub.
2. Click the **Pull Requests** tab → **New Pull Request**.
3. Select your branch (`feat/add-search-bar`) as the compare branch, and `main` (or another target) as the base.
4. Review the diff, add a descriptive title and message, then click **Create Pull Request**.

#### 6. Review and Merge

- Teammates can comment, request changes, or approve.
- Once approved, click **Merge pull request** and **Confirm**.
- Optionally delete the branch to keep things clean.


For more, see: [GitHub Docs: Creating a pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)
