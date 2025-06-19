# Git Basics and Workflow

## Initial Setup

### 1. Initialize a Git Repository
```bash
# Create a new directory for your project
mkdir my-project
cd my-project

# Initialize a new Git repository
git init
```

### 2. Clone a Repository
```bash
# Clone a repository from GitHub
git clone https://github.com/username/repository.git

# Clone a specific branch
git clone -b branch-name https://github.com/username/repository.git
```

### 3. Configure Git
```bash
# Set your name globally
git config --global user.name 'John Doe'

# Set your email globally
git config --global user.email 'johndoe@example.com'

# Verify configurations
git config --global --list
```

## Remote Repositories Management

### 4. Manage Remote Repositories
```bash
# View existing remote repositories
git remote -v

# Add a new remote repository
git remote add origin https://github.com/username/repository.git

# Pull code from repository
git pull origin 'branch-name'

git pull origin ravi

# Remove an existing remote repository
git remote remove origin
```

### 5. Push Code to Remote Repository
```bash
# Push to a specific branch (first time)
git push -u origin feature-branch

# Force push (use with caution!)
git push -u origin master --force
```

## Branch Management

### 6. Create and Switch Branches
```bash
# Create and switch to a new branch
git checkout -b feature-login

# Push code to newly created branch
git add .
git commit -m "Your commit message"
git push origin 'your-branch-name'

# Verify That the Branch Is Pushed
git branch -r
or
git ls-remote --heads origin

# If you want to track this branch in future commits, set it as upstream
git push --set-upstream origin 'your-branch-name'

# Switch to an existing branch
git checkout develop

# Switch back to main branch
git checkout main
```

### 7. Delete a Branch
```bash
# Delete a local branch
git branch -d feature-login

# Delete a remote branch
git push origin --delete feature-login
```

## Working with Changes

### 8. Stash Changes
```bash
# Temporarily save uncommitted changes
git stash

# List all stashes
git stash list

# Apply the most recent stash
git stash pop

# Apply a specific stash
git stash apply stash@{0}
```

### 9. Fetch and Merge Branches
```bash
# Fetch latest changes from a remote branch
git fetch origin develop

# Merge changes from another branch
git merge develop
```

### 10. Commit and Push Changes
```bash
# Stage all changes
git add .

# Stage specific files
git add file1.txt file2.js

# Commit with a descriptive message
git commit -m "Add login functionality"

# Push changes to main branch
git push origin main
```

## Advanced Git Commands

### Check Code Differences
```bash
# Fetch latest changes
git fetch origin

# Compare differences between branches
git diff main..feature-branch

# Compare differences for a specific file
git diff main..feature-branch -- src/login.js
```

### List Files in a Branch
```bash
# List all files in a specific branch
git ls-tree -r main --name-only
```

### Revert a Commit
```bash
# Revert to a previous commit
git revert <commit-hash>

# Save work before reverting
git stash
git revert <commit-hash>
git stash pop
```

## Fine-Grained Personal Access Token (PAT)

### Generating a GitHub PAT
1. Go to GitHub Settings
2. Navigate to Developer settings > Personal access tokens
3. Create a new Fine-grained token
4. Set required permissions (read/write repository access)
5. Use the token instead of a password during git push/pull

### How to use fine grane token
```bash
# clone your repo
git clone <your-fine-grane-token>@<youre-repo-id>

# for example
git clone https://github_pat_11BJQ5VUQ0zYt84o8vdJRZ_C2lgUKcHDMmxj8U2ImT4UAoEy1DjC2F5HhDnMG@github.com/mok/dummyrepo.git

# then save your changes
git add .

# commit your change
git commit -m 'your remark'

# push your changes
git push <your-fine-grane-token>@<youre-repo-id>

# for example
git push https://github_pat_11BJQ5VUQ0zYt84o8vdJRZ_C2lgUKcHDMm1DjC2F5HhDnMG@github.com/mok/dummyrepo.git

```

## For Private Repo

For private repositories, you'll need to authenticate properly. Here are the steps:
First, generate a Personal Access Token (PAT) from GitHub:
Go to GitHub.com → Settings → Developer Settings → Personal Access Tokens → Tokens (classic)
Generate new token (classic)
Give it a name and select the necessary scopes (at minimum: repo)
Copy the generated token
Then use these commands, replacing YOUR_USERNAME and YOUR_TOKEN:
```bash

# Remove existing remote if any
git remote remove origin

# Add remote with authentication
git remote add origin https://YOUR_USERNAME:YOUR_TOKEN@github.com/motionofknowledge/04011998.git

# Add and commit your files
git add .
git commit -m "Initial commit: Love Story Gallery with mobile and desktop views"

# Befor pushing check .gitignore file and make sure to not push node_module file and other importent file like .env etc.
git rm -r --cached <YOUR FOLDER NAME OR FILE NAME WITH EXTENSION>
git commit -m "Remove native files from tracking as per .gitignore"

# Push to main branch
git branch -M main
git push -u origin main

# Push to main branch forcefully
git push -u origin main --force
git push -f


```



## Best Practices
- Always pull before you push
- Write clear, descriptive commit messages
- Use feature branches for development
- Regularly sync your local repository
- Be cautious with force push

## Troubleshooting
- If you encounter merge conflicts, resolve them manually
- Use `git status` to understand the current state of your repository
- `git log` helps you track commit history

## Contributing
Please read our contribution guidelines before submitting a pull request.

## License
This project is licensed under the MIT License.
