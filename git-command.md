# Git 筆記  
*some git command*
## Set Config  
Set up **user name** and **user email** with following command.s 
```  
$ git config --global user.name "Forrest Liao"
$ git config --global user.email Forrest_Liao@xxxx.com
```  

If you need to set up developer information under a specific project, go into the particular project’s folder and set up with the following command.
   
```  
$ git config user.name "Forrest Liao"
$ git config user.email Forrest_Liao@xxxx.com
```  

## Modify Remote Repository 
Clone remote repository and modify it.
```  
git clone {repository}
git check --track -b {branch} origin/{branch}
//modify
git add -A
git commit -m "Information"
git push
git checkout master
git pull
git merge {branch}
git push
```