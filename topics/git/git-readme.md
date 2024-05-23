# Useful git commands

## Local git setup
```
git config --global --list
git config --gobal user.name "your_github_username"
git config --global user.email "your_github_email"
git config --global push.autoSetupRemote true
```

## Git branch commands
### List available branch
```
git branch
```

### Create a new branch
```
git checkout -b <new_branch_name>
```

### Switching branch
```
git switch <desire_branch_name>
```

## Pushing to remote (Github)
```
git status
git init
git add .
git commit -m "your message"
git branch
git remote add origin https://github.com/yourusername/your-repo.git
git push origin <your branch>
```
or
```
git clone https://github.com/yourusername/your-repo.git
git status
git branch
git add .
git commit -m "your message"
git push origin <your branch>
```

## Branch Deletion
### Local git branch
```
git branch -d <branch_name_to_be_deleted>
```
### Remote Github branch
```
git push origin --delete <branch_name_to_be_deleted>
```

## Adding rule
1. Settings --> Branches --> Add Rule
2. Fill the branch name in "Branch name pattern"
3. Select the required rule