# git-cheatsheet
* [Links](#links)

## View public key 
```
$ cat ~/.ssh/id_rsa.pub 
```
## Init git repo 
```
$ git init 
```
## Add all files to repo 
```
$ git add -A 
```
## Add remote repo 
```
$ git remote add origin git@bitbucket.org:di_ego/pennyroyal.git 
```
## Commit git 
```
$ git commit -m "Init repo" 
$ git commit -a -m "Improved readme" 
```
* Commits are LOCAL. U need to PUSH to remote repo 
* Be carefull using -a. If new files were added u should git add -A first 
 
## View repo status 
```
$ git status 
```
## Undo changes 
```
$ git checkout -f 
```
## Push changes to remote repo  

For the first time, repo and its refs: 
```
$ git push -u origin --all  
```
Later: 
```
$ git push 
```
## Push changes to Heroku 
```
$ bundle exec rake test 
$ heroku maintenance:on 
$ git push heroku 
$ heroku run rake db:migrate 
$ heroku maintenance:off 
```
## Create new branch 
```
$ git checkout master 
$ git checkout -b modify-readme 
```
## List branches 
```
$ git branch 
$ git branch -av
```
## Create alias for checkout command 
```
$ git config --global alias.co checkout 
``` 
## Rename file with git 
```
$ git mv README.rdoc README.md 
```
## Merge branch 
```
$ git checkout master 
$ git merge modify-readme 
```
## Delete branch 
```
$ git branch -d modify-readme 
$ git branch -D modify-readme #if it hasn’t been merged 
```
## Remove directory from git and local 
You could checkout 'master' with both directories;  
```
git rm -r one-of-the-directories 
git commit -m "Remove duplicated directory" 
git push origin <your-git-branch> (typically 'master', but not always) 
``` 
## Remove directory from git but NOT local 
As mentioned in the comments, what you usually want to do is remove this directory from git but not delete it entirely from the filesystem (local) 

In that case use:  
```
git rm -r --cached myFolder 
```

## Links
* [Pro Git](https://git-scm.com/book/ru/v2)
* [eax.me](https://eax.me/git-commands/)
* [Branching](https://habrahabr.ru/post/106912/)
