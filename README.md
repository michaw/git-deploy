git-deploy
==========

git deployment script using git-ftp script

This is dependent on the git-ftp script: https://github.com/git-ftp/git-ftp

You must set up a scope in git-ftp config before this deployment script can be used.

To require a particular branch for a scope, use
```git config --add git-ftp.<scopename>.branch <branchname>```
For example: 
```git config --add git-ftp.live.branch master```

This will instruct the deployment script to only allow the specified branch to be deployed to that scope.


To set up preflight requirements (such as ensuring nothing is deployed to the production environment without being on a test branch) you need to set up the preflight branch and the production branch

Set up the preflight branch with: 
```git config --add git-ftp.preflight <branchname>```

and set up the production environment with
```git config --add git-ftp.production.branch <branchname>```
and
```git config --add git-ftp.production.branch <scopename>```


