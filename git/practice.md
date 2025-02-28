# Git Remote Practice

## Objective

In this practice, you will:

1. Clone a remote repository.
2. Create a new branch named after your NetID.
3. Start the branch from a specific commit based on your NetID.
4. Practice pushing, pulling, and merging.

---

## Step 1: Clone the Repository

First, clone the remote repository from GitHub:

```sh
git clone https://github.com/gyunkai/git-playground.git
cd git-playground
```
## Step 2: Find Your Starting Commit

Look at the last digit of your NetID:
- If your NetID ends in an odd number (1, 3, 5, 7, 9), use the commit tagged as odd.
- If your NetID ends in an even number (0, 2, 4, 6, 8), use the commit tagged as even.

## Step 3: Create Your Branch

Create a new branch from your assigned commit:

```sh
# Switch to your assigned commit
git checkout <odd/even>

# Create and switch to your new branch
git checkout -b <your-netid>
```

For example, if your NetID is abc123 and ends in 3:
```sh
git checkout odd
git checkout -b abc123
```