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

            PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> cat story1.txt
               line1
               line2
  Now the story1.txt fiel updated with line2, if we think that updated accidentally and we would like to restore previous file , we can do that. 
            PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git restore story1.txt
            PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> cat story1.txt
            "line1"
            PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT>git status
                  On branch main
                  Your branch is ahead of 'origin/main' by 1 commit.
                    (use "git push" to publish your local commits)

                  nothing to commit, working tree clean
                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT>
  Now the working is clean, let's assume we are knowingly updated a file, we will follow the same process stage, commit the file.
  
                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> echo "line2" >>story1.txt
                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> cat story1.txt
                  line1
                  line2
                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git status
                  On branch main
                  Your branch is ahead of 'origin/main' by 1 commit.
                    (use "git push" to publish your local commits)

                  Changes not staged for commit:
                    (use "git add <file>..." to update what will be committed)
                    (use "git restore <file>..." to discard changes in working directory)
                          modified:   story1.txt

                  no changes added to commit (use "git add" and/or "git commit -a")
                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git add story1.txt
                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git commit -m "Updated first story"
                  [main 06c4068] Updated first story
                   1 file changed, 0 insertions(+), 0 deletions(-)
                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git status
                  On branch main
                  Your branch is ahead of 'origin/main' by 2 commits.
                    (use "git push" to publish your local commits)

                  nothing to commit, working tree clean
                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT
  below we have added line3 to story1.txt file and line1 to story2.txt file. 
                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> echo "line3" >>story1.txt
                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> echo "line1" > story2.txt
                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git status
                  On branch main
                  Your branch is ahead of 'origin/main' by 2 commits.
                    (use "git push" to publish your local commits)

                  Changes not staged for commit:
                    (use "git add <file>..." to update what will be committed)
                    (use "git restore <file>..." to discard changes in working directory)
                          modified:   story1.txt

                  Untracked files:
                    (use "git add <file>..." to include in what will be committed)
                          story2.txt

                  no changes added to commit (use "git add" and/or "git commit -a")
                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT>

if we want to commit them together we can do this. 
                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git add .
                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git status
                  On branch main
                  Your branch is ahead of 'origin/main' by 2 commits.
                    (use "git push" to publish your local commits)

                  Changes to be committed:
                    (use "git restore --staged <file>..." to unstage)
                          modified:   story1.txt
                          new file:   story2.txt

                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git commit -m "Added second story and updated first story"
                  [main 6b8ba14] Added second story and updated first story
                   2 files changed, 0 insertions(+), 0 deletions(-)
                   create mode 100644 GIT/story2.txt
                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git status
                  On branch main
                  Your branch is ahead of 'origin/main' by 3 commits.
                    (use "git push" to publish your local commits)

                  nothing to commit, working tree clean
                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT>
                  
if we want to commit them individually we can follow this. 
# git add story1.txt
# git status ( story1.txt will be in staging area and story2.txt will be untracked state)
# git commit -m "Updated first story"
# git add stroy2.txt
# git status ( story2.txt will be in staging area)
# git commit -m "Added second story"
Note: Make each commit attomic 

               PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> echo "line4" >>story1.txt
               PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git add story1.txt
               PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> echo "djfjdfljlsd" >story1.txt
               PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git status
               On branch main
               Your branch is ahead of 'origin/main' by 3 commits.
                 (use "git push" to publish your local commits)

               Changes to be committed:
                 (use "git restore --staged <file>..." to unstage)
                       modified:   story1.txt

               Changes not staged for commit:
                 (use "git add <file>..." to update what will be committed)
                 (use "git restore <file>..." to discard changes in working directory)
                       modified:   story1.txt

               PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT>
In this above example we have updaed file story1.txt with line4 and staged , and then accidentally overwriten the same file, when we check the git status it will show file status as modified and staged. 
Here we can restore the staged file using below command 
# git restore story1.txt 

                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git restore story1.txt
                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git status
                  On branch main
                  Your branch is ahead of 'origin/main' by 3 commits.
                    (use "git push" to publish your local commits)

                  Changes to be committed:
                    (use "git restore --staged <file>..." to unstage)
                          modified:   story1.txt

                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT>
                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> cat story1.txt
                  line1
                  line2
                  line3
                  line4
                  PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT>
# example     
                        PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git status
                        On branch main
                        Your branch is ahead of 'origin/main' by 3 commits.
                          (use "git push" to publish your local commits)

                        Changes to be committed:
                          (use "git restore --staged <file>..." to unstage)
                                modified:   story1.txt

                        Changes not staged for commit:
                          (use "git add <file>..." to update what will be committed)
                          (use "git restore <file>..." to discard changes in working directory)
                                modified:   story2.txt

                        PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git restore --staged story1.txt
                        PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git status
                        On branch main
                        Your branch is ahead of 'origin/main' by 3 commits.
                          (use "git push" to publish your local commits)

                        Changes not staged for commit:
                          (use "git add <file>..." to update what will be committed)
                          (use "git restore <file>..." to discard changes in working directory)
                                modified:   story1.txt
                                modified:   story2.txt

                        no changes added to commit (use "git add" and/or "git commit -a")
                        PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT>
                  
In this above example we want to stage story2.txt first hence we restored the story1.txt file to staging area from commited area. 
                        PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git add story2.txt
                        PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git commit -m "Updated second story"
                        [main 41e6102] Updated second story
                         1 file changed, 0 insertions(+), 0 deletions(-)
                        PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git status
                        On branch main
                        Your branch is ahead of 'origin/main' by 4 commits.
                          (use "git push" to publish your local commits)

                        Changes not staged for commit:
                          (use "git add <file>..." to update what will be committed)
                          (use "git restore <file>..." to discard changes in working directory)
                                modified:   story1.txt

                        no changes added to commit (use "git add" and/or "git commit -a")
                        PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT>            
 Let's say another use case we have created a file called notes.txt 
 
                       
                        PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> echo "my story ideas" > notes.txt
                        PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git status
                        On branch main
                        Your branch is ahead of 'origin/main' by 4 commits.
                          (use "git push" to publish your local commits)

                        Changes not staged for commit:
                          (use "git add <file>..." to update what will be committed)
                          (use "git restore <file>..." to discard changes in working directory)
                                modified:   story1.txt

                        Untracked files:
                          (use "git add <file>..." to include in what will be committed)
                                notes.txt

                        no changes added to commit (use "git add" and/or "git commit -a")
                        PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git add .
                        PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git status
                        On branch main
                        Your branch is ahead of 'origin/main' by 4 commits.
                          (use "git push" to publish your local commits)

                        Changes to be committed:
                          (use "git restore --staged <file>..." to unstage)
                                new file:   notes.txt
                                modified:   story1.txt

                        PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT>
                        PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> echo "notes.txt" >.gitignore

                        PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> cat .gitignore
                        notes.txt
                        PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT> git status
                        On branch main
                        Your branch is ahead of 'origin/main' by 4 commits.
                          (use "git push" to publish your local commits)

                        Changes to be committed:
                          (use "git restore --staged <file>..." to unstage)
                                modified:   story1.txt

                        Untracked files:
                          (use "git add <file>..." to include in what will be committed)
                                .gitignore
                                notes.txt

                        PS C:\Users\cbmivsi\Desktop\SINGAM\MY GIT\GIT>                           

