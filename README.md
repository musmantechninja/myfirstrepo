## Generate ECDSA SSH key with 521 bits:
```
ssh-keygen -t ecdsa -b 521 -C "muhammadusman2478910@gmail.com"
```

## List global Git configurations:
```
git config --global --list
```

# Set global Git username:
```
git config --global user.name "Muihammadusman2478"
```

# Set global Git email:
```
git config --global user.email "muhammadusman2478910@gmail.com"
```

# Unset global Git username:
```
git config --global --unset user.name "Usmanatgithub"
```

# Unset global Git email:
```
git config --global --unset user.email "muhammadusman.cloudways@gmail.com"
```

# Initialize a Git repository:
```
git init
```

# Check Git repository status:
```
git status
```

# Stage a specific file for commit:
```
git add README.md
```

# Stage all changes for commit:
```
git add .
```
# Commit changes:
```
git commit -m "first commit"
```

# Rename the default branch to 'main':
```
git branch -M main
```

# Add a remote named 'origin':
```
git remote add origin git@github.com:musmantechninja/myfirstrepo.git
```

# Change the remote URL:
```
git remote set-url origin <correct-remote-url>
```

# Clone a repository:
```
git clone git@github.com:musmantechninja/myfirstrepo.git
```

# Test SSH connection to GitHub:
```
ssh -T git@github.com
```

# Verbose SSH connection to GitHub:
```
ssh -vT git@github.com
```

# List remote repositories:
```
git remote -v
```

# Show details about a specific remote:
```
git remote show origin
```

# Remove a remote named 'origin':
```
git remote remove origin
```

# Display local branches with tracking information:
```
git branch -vv
```

# Push changes to the 'main' branch on 'origin':
```
git push -u origin main
```

# Push changes to the 'main' branch on 'origin2':
```
git push origin2 main
```

# Start SSH agent:
```
eval "$(ssh-agent -s)"
```

# Add a private key to SSH agent:
```
ssh-add /path/to/your/private-key
```

# Remove a specific identity from SSH agent:
```
ssh-add -d /path/to/private-key
```

# Remove all identities from SSH agent:
```
ssh-add -D
```
