# Git Clone & Basic Remote Operations

The `git clone` command creates a copy of an existing Git repository. Let's see it in action:

```sh
# Clone a GitHub repository
> git clone https://github.com/username/repository.git
```

When you clone a repository, Git:

- Creates a copy of all files and history
- Sets up remote tracking branches
- Creates a remote called "origin" pointing to the source repository

Common remote operations include:

```sh
# Pull changes from remote repository
> git pull origin main

# Push your changes to remote repository
> git push origin main

# Merge changes from another branch
> git merge feature-branch
```

Key commands explained:

- `git pull`: Fetches and merges changes from remote repository
- `git push`: Uploads your local commits to remote repository
- `git merge`: Combines changes from different branches

Best practice: Always pull before pushing to avoid conflicts.

## Practice

[Start](practice.md) hands-on exercises with Git remotes.
