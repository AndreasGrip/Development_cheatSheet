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
git push name-of-repo master  
```
“master” being the name of the branch (we will discuss branches later, but, for now, using the master branch exclusively is fine)  
Unless you are using SSH keys, you will be prompted for a password