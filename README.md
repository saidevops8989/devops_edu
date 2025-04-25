# devops_edu

How to install git and some basic commands
#
    sudo apt update
    sudo apt install git -y
To check the installed version
#
    git --version
To get help or see what are all cmd
#
    git help
To list branches
#
    git branch
git command used to start a working area
#
    mkdir test
    cd test
    git init
You may view additional help on each command following the syntax git help <command>. For this you must first install git man pages using the command
#
    git help init

Once a git repo is intializes we can see some of the hidden files ls -a ( like .git ) unit we create some file it cannot show anything on git status cmd
we have 3 stage(working area ) (staging area) (commited files)

 <img width="967" alt="Screenshot 2024-10-06 at 8 41 44 PM" src="https://github.com/user-attachments/assets/6199f2b5-7bb1-4aa4-9c83-def79666fdf2">

To create an empty file  and wirite some text to the file
 #
         touch story1.txt
         echo "my  frist line1"
        

To view the status where we are now on those there stage we can use git status cmd
#
        git status
        git ls-files

To add the file to the staging area 
#
        git add story1.txt
        git status
        git ls-files

To commit the file 
#
        git commit -m "added frist story"

        git status
        On branch master
        nothing to commit, working tree clean

Now once we make changes to the story1.txt we can see the file is being tracked but in modified state.

       <img width="517" alt="Screenshot 2024-10-06 at 8 54 33 PM" src="https://github.com/user-attachments/assets/e110ebe4-6c9a-471e-b2e5-b64c71855a46">

       we can use a git cmd to restore as well
#
        git restore story1.txt

Now the file is back to orginal postion and its clean git status
But lets add 2ine and add and commit

#
        echo "secondline" >>stroy1.txt
        git diff
        git add story1.txt
        git diff --staged
        git commit -m "updated friststory"


Now lets add second file we can see the untracked file modified file staging area 

 <img width="522" alt="Screenshot 2024-10-06 at 9 02 17 PM" src="https://github.com/user-attachments/assets/38f728fd-b34a-4b15-8bfa-773ee25422f2">

 #
         echo "line1insecondfile" > story2.txt
         git status
         git add .
         git commit "added story2.txt"


Playing to move file from working area to staging area and staging area to working area

<img width="376" alt="Screenshot 2024-10-06 at 9 10 46 PM" src="https://github.com/user-attachments/assets/6de3cfb8-932d-47e9-bf6a-a30245be2d84">

#
        echo "thirdline" >> story1.txt
        git add story1.txt
        echo "line2insecondfile >>story2.txt
        git status

        git restore --staged story1.txt

        git add story2.txt
        git commit -m "updating story2.txt"

git log is the command to see the commit id date of the commit happened and commit message
#
        git log

we can list the changed files as well using the --name-only
#
        git log --name-only
we can see online of commit log
#
        git log --oneline
To view only last 2 logs we can change the number 2 to 3 4 depending on the logs required.
#
         git log -n 2

Branching in git

<img width="798" alt="Screenshot 2024-10-07 at 5 21 14 PM" src="https://github.com/user-attachments/assets/f2ab67d4-b3a9-4b2d-873f-54946c91358d">

#
        git branch newfeature
        git checkout newfeature

        or it can be done in single cmd
        
        git checkout -b newfeature

        not make some changes to the story1.txt

        git add .

        git commit -m "updated branch"

        not make some changes again to the story1.txt

        git add .

        git commit -m "updated branch secondtime"

        git checkout master

        git merge newfeature

        git log

        git branch -d newfeature

        git branch  ## to see the branch doesn't exists
        

Create a git a ccount and play in GUI 

The current directory which is intialized as git  to sync to remote repos, the below url should be update with your repo url
#
        git remote add origin https://github.com/saidevops8989/test.git

        git push origin master
        
Remote branch push  we can push to the branches as well
#
        git push --set-upstream origin b9


Cloning remote repository Update the url with your git repo url
#
        git clone https://github.com/saidevops8989/test.git


Pulling the changes from the remote branch after cloning
#
        git  fetch origin master

        git show <hashfrom abovecmd>       #this will show what was the changes that was made
         
        git diff origin/master

        git merge origin/master
<img width="549" alt="Screenshot 2025-04-25 at 7 49 57 AM" src="https://github.com/user-attachments/assets/1b2cedde-b10e-416a-94c1-d6ffc7a44e55" />

        
        ABOVE BOTH  COMMANDS CAN BE DONE IN SINGLE CMD with

        git pull origin master


Create a pull request in the GUI create a branch make some changes and then merge the branch to the master


stashing
This functionality is useful when you’ve made changes  that you aren’t ready to commit, but you need to commit one file among two then we need stash one file and commit the otherone
#
        git stash 

        git stash list

        git stash pop

        git stash push story1.txt

        git stash pop stash@{0}


git revert is undo the changes made in the previous commit and a new commit is created without changes made in the other commit.

#
        git log --oneline

        git show 

        git show hashcode

        git revert hashcode

git reset has two types on is soft and hard soft will reset to the previous has but keeps the changes hard reset is completly moving back to the hash mentioned,comit some chages
like commit A commit B commit C we can go abck to commit B 
#
        
        git log --oneline
        
        git reset  hashcode

        git status

        git reset --hard hashcode

git rebase 
create commit A B on master and create a branch on that create commit C D E
when we rease master  with branch then we can see the commits A B C D E
#
        git checkout master

        git rebase branchname

        git log --oneline

git forking copy of an existing git repo that allows the new owner to make changes to the project without effecting the oringial


        

        

        
        

        










        



