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


#  1. Question

*Can you add multiple git remote origins, from different github accounts within the same local machine, for push and pull purposes?*

The answer is YES, you can add it but following the below steps.

If you  get error similar to the below one while checking the remote origin, pushing/pulling the git to remote repo, following the below command,


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
origin	git@github.com:musmantechninja/myfirstrepo.git (fetch)
origin	git@github.com:musmantechninja/myfirstrepo.git (push)

2. Then run below, and then look for the lines similar to the one mentioned below, that says, the key offered and accepted while making the SSH keys,

### Note: The SSH key, offered and accepted should be the one assosiated with the your respective github account that you created while generting the ssh-key pair.

In my case the private key for my respective github account is placed under the file path  /Users/muhammadusman/.ssh/firstrepo but I am seeing the below output when testing the ssh connection using "ssh -vT git@github.com"
 
debug1: Offering public key: /Users/muhammadusman/.ssh/id_ecdsa ECDSA SHA256:FAGcOULC6VSjZebjCqz/hKFfXVJ0C9t+Pj4O1Cw8+UQ explicit agent
debug1: Server accepts key: /Users/muhammadusman/.ssh/id_ecdsa ECDSA SHA256:FAGcOULC6VSjZebjCqz/hKFfXVJ0C9t+Pj4O1Cw8+UQ explicit agent


```
ssh -vT git@github.com
```

##Solution


I have to add the ssh identity of my respective github account's private key and then need to push.

ssh-add /Users/muhammadusman/.ssh/firstrepo


and then use below command,


git remote git@github.com:musmantechninja/myfirstrepo.git main


# 2. FAQ


*Why can't I add the similar pub key to the differnt account to avoid the error mentioned in first question?*

You can't use the same pub key for the diffrent github account.