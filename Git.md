# Setup git server

https://linuxize.com/post/how-to-setup-a-git-server/

# Create a repository on remote server
- Log into your server via SSH
- In a convenient location, create a new directory ending with the .git extension (production.git, for example)
- Enter the new directory
- Run this command inside the directory:  
```sh
git init --bare
```
- Go back to your local repository
- Enter your working directory and run this command, submitting the “name-of-repo” with something relevant for your project and “userna5” with your cPanel or SSH username and “destination” with the host domain or IP:  
```sh
 git remote add name-of-repo userna5@desination:/home/userna5/production.git
```
- Having successfully added a remote repository, this command will push the contents of your local repository up to the remote repository:  
```sh
git push name-of-repo main  
```
“master” being the name of the branch (we will discuss branches later, but, for now, using the master branch exclusively is fine)  
Unless you are using SSH keys, you will be prompted for a password

# Auto publish a node program on repository server

You might have to run 
```sh
git --git-dir=/home/ubuntu/git_repositories/myProgram.git -checkout main
```
due to the fact that git changed default branch name  

In folder /home/ubuntu/git_repositories/myProgram.git/hooks create file post-receive and chmod it +x  
contents should be like

```sh
#!/bin/sh
git --work-tree=/opt/myProgram --git-dir=/home/ubuntu/git_repositories/myProgram.git -checkout main -f
git --work-tree=/opt/myProgram --git-dir=/home/ubuntu/git_repositories/myProgram.git -checkout -f
cd /opt/myProgram
npm install
```

# misc
## rename master to main
```sh
git branch -m master main
```

# Setup on GitHub
create empty with correct name on github   
add a empty repository with correct name on github   
```sh
git remote add origin https://github.com/AndreasGrip/gWinston.git
git push -u origin main
```
