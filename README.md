# Git & GitHub Notes 

- Git is version control system which allows you to create checkpoints of your codebase basically, if you mess up or break your app / website in later stages you can spawn back to your previously "working" checkpoint easily.
- GitHub is a service which streamlines the Git workflow by giving it GUI
- GitHub allows people to contribute and merge different files they've been working on in one main file.
- Maintains the project history, which person made which change, when so on and so forth.
- Allows to share your project around the world.

- 🟥 means line was deleted
- 🟩 means line was added

# Git Lingo 

- **Untracked files** - not saved
- **staging area** - the untracked files are prepared to be commited / saved in the git history.
- **staged files** - files prepared (having no untracked changes) to be commited (saved).
- **head** - head points to the barnch where the commits and works is going to be saved/ committed at.
- **push** - 
- **pull** -
- **merge / merging** - to merge the feature / prototype branch into another branch ( which may be main/ master )
- **main / master branch** - this can be the branch which is in production (working code resides inside main branch.)
- **remote repository** - repository which is hosted online like on github, gitlens, gitkraken etc.
 
# Command Line Snips 

- To check if git is installed or not : **git** : list of all commands will showup 
- To Setup the Github :  
- 🔺cmd : **cd** - change directories (file/folder)
- 🔺cmd : **ls** - lists all the files in current(ly open) directory (folder)
- 🔺cmd : **mkdir** - make directory - creates a folder
- 🔺cmd : **cd <nameoffolder>** - goes / open that folder
- 🔼 git : **git init** - initialises (starts) the git repository - initialize a git repo inside the project folder.
            this creates a hidden folder (.git)
- 🔺cmd : **ls -a** : shows all the hidden files. basically shows all the dot files, generally dotfiles are hidden.
- 🔺cmd : **touch <filename>** //works only for unix/linux based OS - macOS
- 🔼 git : **git status** - lists untracked / unsaved files to which changes are made. (this files are not tracked in the history of the project, basically on the git.)
- 🔼 git : **git add** - this git command add the changes made in current / working directory / folder to the staging area. basically prepares the untracked (unsaved) changes to be saved (commited).
- - **git add . (dot)** - **adds all** the unsaved changes made in the current project directory to the staging area (to take a snapshot of them)
  - **git add <filename>** - adds the changes made in a particular file which is mentioned in the cmd.
- 🔼 git : **git status** - again lists untracked / unsaved files to which changes are made. (this files are not tracked in the history of the project, basically on the git.)
- - files in 🟥 have untracked changes.
  - files in 🟩 do not have any unsaved changes. they are ready on stage and ready to be saved (commited)
- 🔼 git : **git commit -m "you can add comments in double quotes"** - saves the staged files to the history.
- 🔼 git : **git restore --staged <filename>** removes particular file from staging area (keep the stage clear for others)
- 🔼 git : **git log** - shows all the commits along with the information about the author (person who commited the file), time, date of commit.
- 🔺cmd : **rm -rf <filename>** - deletes the mentioned file from folder. 
- 🔼 git : **git status** - shows that the files is deleted - now further commit with a message that file is deleted.
- 🔼 git : rolling back to the specific commit - **git reset <commit ID>** - this removes all the commits commited after that specific commit.

## image example : 
- ![image](https://github.com/user-attachments/assets/4a0b303b-7629-45e5-b0b7-c84402ba741b)
- if i rollback to the yellow commit, the highlighted commits will be uncommited (basically they will get reverted/ rolled-back / removed)
- fue471ufh173hfk173hdy1613hr is the commit code. and this is important to be able to revert back.

- 🔼 git : **git stash** - Git stash temporarily shelves or stashes changes made to your working copy so you can work on something else, and come back and re-apply them later on.
- 🔼 git : **git stash** - This allows you to move the staged files to the back stage so that you can work on another files meanwhile. later you can call them from the backstage to the stage and commit them easily.
- git stash is used when you worked on a file ABC and prepared it to be committed but you want to work on another file XYZ first & commit XYZ then atfer that commit the previous file ABC.
- currently on stage : ABC
- wants to work on XYZ first : send ABC to backstage using git stash so that stage is clear
- work on XYZ, stage XYZ, commit XYZ.
- bring ABC back : **git stash pop** brings back the backstage files.
- 🔼 git : **git stash pop** - brings back all the stashed files from the backstage to the main stage again.
- 🔼 git : **git stash clear** - deletes the files from the backstage, deleted files can't be restored.  
- 🟩 github : create a repository on github - this gives a URL to the repository when made.
  
- _we will need to attach the GitHub repo URL to our local project folder right ?_

- 🔼 git : **git remote add origin <URL-to-the-github-repository>** - remote = online/not local, add = adding new url, origin = name-of-the-url
- 🔼 git : **git remote -v** - shows all the links / URLs attached.
- 🔼 git : **git push origin branchname** - all the changes, staging and commiting happens offline on our local device, if we need all the changes to be shown on the github, we will need to **push** all the files, commmits and changes to github from our local git.


# _what are branches and how to work with branches_ ?


- whenever working on new features, fixing bugs always create a new separate branch and work in new branch.
- never commit on main / master branches.

- 🔼 git : **git branch <branchname>** : this creates a branch named as <branchname>
- **head** - head points to the barnch where the commits and works is going to be saved/ committed at.
  
- _there are so many people who are working on the same project simultaneously._
- changing the heads
- 🔼 git : The "checkout" command can switch the currently active branch - but it can also be used to restore files.
- 🔼 git : **git checkout <branchname>** - changes the head to <branchname>
- 🔼 git : **git merge <branchname>** - this commits the <?> to the current branch.

## basic workflow : how will i merge branch ABC to branch XYZ ? 

- 1st navigate to the branch XYZ using **git checkout XYZ** / (Switch to the target branch (the one you want to merge into))
- 2nd use **git merge ABC** (Merge the source branch into it)

## done !~

pushing new changes (files and offline commits) to the remote repository (online repos - github, gitlab, gitkraken)

- 🔼 git : **git push <targetURL> <targetBranch>** - pushes local commits to the targetted remote repo (URL) and to targetted branch.
done all the changes made in local repo is pushed to the online / remote repository on your service provider of choice.

## A few tips:
- If there are no conflicts, Git will auto-merge.
- If there are conflicts, Git will ask you to resolve them before you can complete the merge.
- After merging, if you're collaborating with others, don’t forget to push.


# working with existing remote repos on gitServces : 




