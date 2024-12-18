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
