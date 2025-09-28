# tgc-project-easter
This repo houses the Tiny Games Club community project for the month of October (2025): https://www.skool.com/tiny-games-club-8687/group-gaming-project-pitch.

## Workflow - First Time Setup
1. `git clone git@github.com:AndrewMatzureff/tgc-project-easter.git					# Clone project repo into a new folder, "tgc-project-easter", within the current directory.`
2. `cd tgc-project-easter															# Change current directory to the root of the newly-cloned repo.`
3. [Install Git Large File Storage](https://docs.github.com/en/repositories/working-with-files/managing-large-files/installing-git-large-file-storage) (if it has not already been installed on your system) in order to properly and efficiently track large asset files.
4. `git lfs install																	# Set up the current local repository to use Git LFS.`
5. Ready to contribute!

## Workflow - Make a Change (create a brand new feature branch)
1. `git switch mainline																# Ensure you have the main branch checked out.`
2. `git pull --rebase																# Fetch and apply ("pull") the latest changes from the remote while "rebasing" any of your local committed changes on top of the changes that were pulled in as if you had made your local changes based on the present state of the remote repo (now you know you are working with the latest changes at least for right now).`
3. `git checkout -b <feature-branch-name> -t										# Create and switch to a new branch ("-b <feature-branch-name>") which is set up to track mainline ("-t") as this branch's target ("upstream") to pull in new changes.`
4. Make a change to some resource: `<filename>`.
5. `git add <filename>																# Stage <filename> for commit.`
6. `git commit -m "Example: Enable <feature> in <filename>"							# Commit all staged file changes to a new point in the history of your local branch and include a simple commit message ("-m").`
7. `git switch mainline && git pull --rebase										# Ensure we still have the latest changes before we create a CR/PR (optional).`
8. `git switch <feature-branch-name> && git pull --rebase							# Apply the latest changes before we create a CR/PR (optional for if we pulled in any remote changes; you may need to resolve merge conflicts after this step).`
9. `git push -u origin <feature-branch-name>										# Create new remote feature branch ("-u origin <feature-branch-name>") and upload ("push") our local changes to it.`
10. Find your commit on [GitHub](https://github.com/AndrewMatzureff/tgc-project-easter) and then open a new pull request (code review) to merge your changes from `<feature-branch-name>` into `mainline`!

## Workflow - Make a Change (update an existing feature branch)
1. `git switch mainline																# Ensure you have the main branch checked out.`
2. `git pull --rebase																# Fetch and apply ("pull") the latest changes from the remote while "rebasing" any of your local committed changes on top of the changes that were pulled in as if you had made your local changes based on the present state of the remote repo (now you know you are working with the latest changes at least for right now).`
3. `git switch <feature-branch-name>												# Switch to an existing branch ("-b <feature-branch-name>") which is set up to track mainline ("-t") as this branch's target ("upstream") to pull in new changes.`
4. Make a change to some resource: `<filename>`.
5. `git add <filename>																# Stage <filename> for commit.`
6. `git commit --amend --no-edit													# Apply all staged file changes directly to the latest commit of your local branch ("--amend") while preserving the existing commit message ("--no-edit").`
7. `git switch mainline && git pull --rebase										# Ensure we still have the latest changes before we create a CR/PR (optional).`
8. `git switch <feature-branch-name> && git pull --rebase							# Apply the latest changes before we create a CR/PR (optional for if we pulled in any remote changes; you may need to resolve merge conflicts after this step).`
9. `git push -u origin <feature-branch-name>										# Update the remote feature branch with your amended commit.`
10. Find your commit on [GitHub](https://github.com/AndrewMatzureff/tgc-project-easter) and then open a new pull request (code review) to merge your changes from `<feature-branch-name>` into mainline!

## Workflow - Add New Asset Type to Git Large File Storage
`git lfs track "*.mp3" "*.png"														# Track MP3 sounds and PNG images in Git LFS (makes storage more efficient and code reviews more straightforward by simplifying file diff presentation).`
`git add .gitattributes && git commit -m "Track .MP3 and .PNG assets in Git LFS"	# Commit your Git LFS changes to your local branch.`

## Workflow - Helpful Tools
`git config --global alias.lol "log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit" # Creates an alias in your global git config which you can use (from any of your local repos) to display a concise, intuitive, pretty-formatted visual representation of your working tree by running: "git lol"!