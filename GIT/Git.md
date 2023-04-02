# Git Introduction: 
###############################
Git is a content tracker it saves all our changes and also it is ditributed version control system. (We can go back in time with out losing any new changes.)

# Git Repositories: 
1. Local Repository -It's on your own machine, you have direct access to it. \
   Local Repository has consistes of 3 stages. 
   a)Working Area - It consists of all your active changes. 
   b)Staging Area - It contains new changes which are going to committed soon. 
   c)Commited Area - It contains all your commited files. 
2. Remote Repository -Centralize server

# Install Git
https://www.atlassian.com/git/tutorials/install-git 

git --version -- to check the current version of git.

Install GIT on the system.
# sudo apt update
# sudo apt install git
# sudo git --version
What's the git command used to Show various types of objects -- git show
What's the git command used to List, create, or delete branches? -- git branch
What's the git command used to Download objects from another repository? -- git fetch
What's the git command used to start a working area? --git init

# Intialize a GIT Repository
 # git init (Move to the project folder and run git init)
   when the file is created for the first time it is in working area and the state of the file is untracked. 
 # git add file.txt (to add files to the staging area)
   We can check the file status using " Git status"  the file status is ready to commit. 
 # git commit -m "This is the first commit of file.txt" 
 # git status ( Nothing will show to commit , unless we create a new file. )
 
 #Example
**echo "Line1" >Story1.txt** **
git status will tell you the story1.txt file is under untracked state. 
# git add story1.txt
git status will tell you the story1.txt file is in staging area and ready to commit. 
Now we will commit the file, but before commit git should know who you are. 
# git config user.name "vsingam9"
# git config user.email "vsingam9@gmail.com"
# git commit -m " This is the first commit of story1.txt" ( A commit stores the copy of a file in it current state)
 If the file get corrupted we can restore the file later using restore option. 
Now if we run the git status command the working are will be clean. that means there is nothing to commit. 

            C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT>echo "line1" >story1.txt

            C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT>git status
            On branch main
            Your branch is up to date with 'origin/main'.

            Untracked files:
              (use "git add <file>..." to include in what will be committed)
                    story1.txt

            nothing added to commit but untracked files present (use "git add" to track)

            C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT>git add story1.txt

            C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT>git status
            On branch main
            Your branch is up to date with 'origin/main'.

            Changes to be committed:
              (use "git restore --staged <file>..." to unstage)
                    new file:   story1.txt


            C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT>git commit -m "added line1"
            [main b062a31] added line1
             1 file changed, 1 insertion(+)
             create mode 100644 GIT/story1.txt

            C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT>git status
            On branch main
            Your branch is ahead of 'origin/main' by 1 commit.
              (use "git push" to publish your local commits)

            nothing to commit, working tree clean

            C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT>

 



 
