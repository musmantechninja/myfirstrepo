## Generate ECDSA SSH key with 521 bits:
```
ssh-keygen -t ecdsa -b 521 -C "muhammadusman2478910@gmail.com"
```

## List global Git configurations:
```
git config --global --list
```

## Set global Git username:
```
git config --global user.name "Muihammadusman2478"
```

## Set global Git email:
```
git config --global user.email "muhammadusman2478910@gmail.com"
```

## Unset global Git username:
```
git config --global --unset user.name "Usmanatgithub"
```

## Unset global Git email:
```
git config --global --unset user.email "muhammadusman.cloudways@gmail.com"
```

## Initialize a Git repository:
```
git init
```

## Check Git repository status:
```
git status
```

## Stage a specific file for commit:
```
git add README.md
```

## Stage all changes for commit:
```
git add .
```
## Commit changes:
```
git commit -m "first commit"
```

## Rename the default branch to 'main':
```
git branch -M main
```

## Add a remote named 'origin':
```
git remote add origin git@github.com:musmantechninja/myfirstrepo.git
```

## Change the remote URL:
```
git remote set-url origin <correct-remote-url>
```

## Clone a repository:
```
git clone git@github.com:musmantechninja/myfirstrepo.git
```

## Test SSH connection to GitHub:
```
ssh -T git@github.com
```

## Verbose SSH connection to GitHub:
```
ssh -vT git@github.com
```

## List remote repositories:
```
git remote -v
```

## Show details about a specific remote:
```
git remote show origin
```

## Remove a remote named 'origin':
```
git remote remove origin
```

## Display local branches with tracking information:
```
git branch -vv
```

## Push changes to the 'main' branch on 'origin':
```
git push -u origin main
```

## Push changes to the 'main' branch on 'origin2':
```
git push origin2 main
```

## Start SSH agent:
```
eval "$(ssh-agent -s)"
```

## Add a private key to SSH agent:
```
ssh-add /path/to/your/private-key
```

## Remove a specific identity from SSH agent:
```
ssh-add -d /path/to/private-key
```

## Remove all identities from SSH agent:
```
ssh-add -D
```

## List Local Branches:

```
git branch
```
Use this command to list all local branches in your repository.

## List Remote Branches:

```
git branch -r
```
Use this command to list remote branches.


## List both local and remote branches.
```
branch -a
```

The git **branch -a** command is used to list all branches in a Git repository, including both local and remote branches.



## Create a New Branch:


```
git branch new-feature
```

Use this command to create a new branch named "new-feature."

## Create and Switch to a New Branch:


```
git checkout -b bug-fix
```
Use this command to create and switch to a new branch named "bug-fix."

## Rename a Branch:

```
git branch -m old-branch-name new-branch-name
```
Use this command to rename an existing branch.

## Delete a Local Branch:

```
git branch -d obsolete-branch
```
Use this command to delete a local branch after merging.

## Force Delete a Branch:


```
git branch -D feature-to-delete
```
Use this command to forcefully delete a branch, even if changes are not merged.

## Show Branches with Last Commit Info:

```
git branch -v
```
Use this command to see a list of branches along with the last commit information.

## Show Merged and Unmerged Branches:

```
git branch --merged
```

```
git branch --no-merged
```
Use these commands to show branches that are either merged or not merged into the current branch.

## Set Upstream Branch:


```
git branch -u origin/main
```
Use this command to set the upstream branch, linking the current local branch to a remote branch.


## Show Current Branch:


```
git branch --show-current
```

Use this command to display the name of the currently checked-out branch.

## Create a New Branch from a Specific Commit:


```
git branch new-branch-name <commit-hash>
```
Use this command to create a new branch starting from a specific commit.



## Show the Upstream Branch:


```
git branch -vv
```
Use this command to display local branches along with their upstream tracking.


#####Example:
Suppose you have a local branch named main, and it is tracking a remote branch called origin/main. You can use the following command to see the upstream tracking relationship:

```
git branch -vv

```

```
* main       c9f8b2a [origin/main] Latest commit on main
  feature-branch   2a1b3c4 [origin/feature-branch: behind 3] Feature branch changes
```

In this example output:

The * main line indicates that you are currently on the main branch.
c9f8b2a is the commit hash of the latest commit on the main branch.
[origin/main] indicates that main is tracking the remote branch named origin/main.
feature-branch is another local branch, and it is tracking the remote branch origin/feature-branch.
2a1b3c4 is the commit hash of the latest commit on the feature-branch.
[origin/feature-branch: behind 3] indicates that the local feature-branch is behind the remote by 3 commits.
This command is useful for quickly checking the status of local branches in relation to their remote counterparts, including information about commits and tracking status.



#  1. Question

**Can you add multiple git remote origins, from different github accounts within the same local machine, for push and pull purposes?**

The answer is YES, you can add it but following the below steps.

If you  get error similar as below one, while checking the remote origin, pushing/pulling the git to remote repo, following the below command,


```
muhammadusman@FQMQWK6N65 firstrepo % git remote show origin                      
ERROR: Repository not found.
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.



git push git@github.com:musmantechninja/myfirstrepo.git main  
ERROR: Repository not found.
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.

```

## Trouble-Shooting steps,

1. Check the remote origin following the below command and note down the remote origin, output.

```
git remote -v 
```

In my case,

origin	git@github.com:musmantechninja/myfirstrepo.git (fetch)
origin	git@github.com:musmantechninja/myfirstrepo.git (push)

2. Then run below command, and then look for the lines similar to the one mentioned below, that says, the key offered and accepted while making the SSH keys,

##### Note: The SSH key, offered and accepted should be the one assosiated with the your respective github account that you created while generting the ssh-key pair.

```
ssh -vT git@github.com
```

In my case the private key for my respective github account is placed under the file path  /Users/muhammadusman/.ssh/firstrepo but I am seeing the below output when testing the ssh connection using "ssh -vT git@github.com"
 
debug1: Offering public key: /Users/muhammadusman/.ssh/id_ecdsa ECDSA SHA256:FAGcOULC6VSjZebjCqz/hKFfXVJ0C9t+Pj4O1Cw8+UQ explicit agent
debug1: Server accepts key: /Users/muhammadusman/.ssh/id_ecdsa ECDSA SHA256:FAGcOULC6VSjZebjCqz/hKFfXVJ0C9t+Pj4O1Cw8+UQ explicit agent




###Solution


I have to add the ssh identity of my respective github account's private key and then need to push.

```
ssh-add /Users/muhammadusman/.ssh/firstrepo
```

and then use below command,


git remote git@github.com:musmantechninja/myfirstrepo.git main


##### Note: If you still face the same issue, run below to restart the ssh-agent and then add the ssh-identity again and then push it again.

```
eval "$(ssh-agent -s)"
```

# 2. Question


**Why can't I add the similar pub key to the differnt account to avoid the error mentioned in first question?**

You can't use the same pub key for the diffrent github account, as it will give error that key is already in use.


 

