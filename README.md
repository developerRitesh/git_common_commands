
# Basic Operations
`git  init`    (initialising git)

`git add index.html`   (we can also add multiple files like `git add one.html two.html three.html four.html` )

`git status`

`git  commit  -m "whatever message you  may  like"`   

`git push origin branchname`  

# Branching
`git branch`

`git checkout -b feature`

`git push origin feature`


# Fetching branch from origin 

`git fetch --all`

`git branch -r`

`git switch remotebranch`

# deleting branch

`git branch -d branchname`  (if it show error like : The branch 'branchname' is not fully merged use `git branch -D ab`)

`git push origin -d "branchname` 



# what to do if wrong file added ,how to  remove a file  from git , or  how to remove a commit    

removing files in git  :  `git reset HEAD index.html` 

note : the above command will reset command git add index.html , if you will do  git  status , this file will be again shown with the changes that you  made .The abpve command do not make changes to file and your code will not  be deleted . 

removing files in git and deleting the  changes also  :  

`git reset HEAD index.html`  (and then) 
`git checkout index.html`

reverting a commit  : `git reset --soft 62634b7af806e9af53a039497c025fdde73841e4` 

the above commit  id will not be of commit  you want to delete , this  is  the commit  id of previos commit that you want to  move . the command will keep this commit and delete all commit afterward .

also  not commit  will  be deleted  but  not the content . 

completly  deleting a commit and all the changes to the files   : `git reset --hard 62634b7af806e9af53a039497c025fdde73841e4` 

this command will  delete  the commit  and all the  content with it .


# sending changes  to  remote repo 

remember if you know  that you will  need to  send your changes to remote server , NEVER START YOUR WORK WITHOUT GIT PULL . Nahi to merge conflicts aaengi hi ,jo fir solve ni hoti . so first step  even before  starting your work is  git pull .  

`git  commit  -m "whatever message you  may  like"`   (this is the last step of commit)

after you  have commited your code  

`sudo git push origin main`

`Username for 'https://github.com': youruserrname`

`Password for 'https://riteshprajapati3.14@gmail.com@github.com':YOURPASSWORD`

# receiving changes from live 

fetch all changes to live : `git pull origin main`

to check which file will come in git pull :  `git fetch origin main && git diff --name-only main origin/main`

#  revert the git to  last  working status

git checkout 09f0a0d1e322daa445a9ac923f38c30e048cbccb

when fixed then move the head to master by 

git checkout master

git pull origin master


#  handling the merge conflict  

#  merge branch to master
first move to master branch , you should be on the branch in which you want to merge another branch 
git merge new-branch

#  stash
stash is used to store temporary change , this is usefull in file conflictions , we can store our local changes in tenporary area , just like we take bacnup of files so they dont get overwrite , we can use git stash instead 


to see all the files present in the stash 

git stash list --stat
or 
git stash list

to add specific files to stash 
git stash -- fileone.txt files2.txt

to see last stashed changes.
git stash show -p stash@{0}

to apply last stash.
git stash apply stash@{0}

Delete Stashed Changes
git stash drop STASH-NAME

To clear the entire stash, run the command
git stash clear




