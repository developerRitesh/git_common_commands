
# how to start git 
`git  init`    (initialising git)

`git add index.html`   (here we are adding a file to git , this way we can multiple files )

`git  commit  -m "whatever message you  may  like"`   (this is the last step of commit)


# common operations 

addding files in git  :  `git add index.html` 

addding multiple files in git in one command :  `git add one.html two.html three.html four.html`

check the difference in file from the last commit : `git diff  one.html`

show  all  git commits : `git log`

show  all  git brancgs : `git branch`

check files in staging area : `git status`


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

to see all the files present in the stash 
git stash list --stat

to add specific files to stash 
git stash -- fileone.txt files2.txt

