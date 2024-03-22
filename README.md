# Febin
1.Setting Up and Basic Commands

Step to initialize a new Git repository, create a new file, add it to the staging area, and commit 

the changes with an appropriate commit message

Step1: Intialize a New Git Repository

 Open the terminal or command prompt.

 Create a Directory mkdir student

 Navigate to the directory where you want to initialize the Git repository cd student

 To initialize a new Git repository, use the following command: git init This will create a new, 

empty Git repository in the current directory.

Step 2: Create a New File

 Create a new file in the repository by using text editor. For example, if you want to create a file 

named "vi example.txt", This command creates an empty file named "example.txt" in the 

current directory.

 After creating the file, add it to the staging area.

Step3: Add the File in to Staging Area

The staging area is where we specify which changes we want to include in the next commit. Use the 

following command to add the file to the staging area: git add example.txt This command git add

"example.txt" to the staging area.

Step4: Commit the changes

Commit the changes with an appropriate commit message. A commit is like a snapshot of the current 

state of the repository. Use the following command to commit the changes: git commit -m "Add 

example.txt file" Replace "Add example.txt file" with a meaningful commit message that explains 

the purpose of the commit.

GIT COMMANDS:

 git –version //This command to check the version
 mkdir foldername eg: mkdir demo
 cd demo 
 git init
 git status
 git add demo.txt
 git commit -m “commiting text file”
 git config user.name “ ” 
 git config user.email “ ”
 git config --global user.name “ ” //To link with git hub account ,git hub username & password
 git config –global user.email “ ” //This command sets the author name and email address 

respectively to be used with your commits.




2.Creating and Managing Branches

Create a new branch named "feature-branch." Switch to the "master" branch. Merge the 

"feature-branch" into "master."

Commands:

Step1:Create a new branch named “feature-branch”

 git branch feature-branch //This will create new branch called feature-branch

 git checkout feature-branch

This command creates a new branch named "feature-branch" and switches to it.

Step2 : Switch to the "master" branch

 git checkout master

Switch back to the "master" branch:

This command switches back to the "master" branch.

Step3: Merge the "feature-branch" into "master."

 git merge feature-branch

This command will merge the changes from "feature-branch" into the "master" branch.

After completing these steps, your "feature-branch" changes will be integrated into the "master" 

branch.

git status //it will check the status

git push origin master





3. Creating and Managing Branches

Commands to stash your changes, switch branches, and then apply the stashed 

changes

Step1:Stash your changes:

 git stash This command will temporarily save your changes, allowing you to switch branches 

without committing them. Git will revert your working directory and staging area to the last 

commit, giving you a clean state to switch branches.

Step2:Switch branches:

 git checkout <branch-name> Replace <branch-name> with the name of the branch you 

want to switch to. This command allows you to move to a different branch in your Git 

repository.

Step3: Apply the stashed changes:

 git stash apply This command reapplies the most recent stash you created. It will restore your 

previously stashed changes, allowing you to continue working on them.

 If you have multiple stashes, you can apply a specific stash by using its index. First, list the 

stashes using the command git stash list. Then, apply a specific stash by index using the 

command: git stash apply stash@{<index>} Replace <index> with the index number of the 

stash you want to apply.

Additionally, if you want to remove the stash after applying it, you can use the command

 git stash drop followed by the stash's index or git stash drop stash@{<index>}.

It's worth noting that stashing is useful when you want to switch branches without committing 

your changes. It allows you to work on multiple branches while keeping your changes separate 

and easily applicable when needed.

Commands:

git branch feature-branch2
git status
vi sample.txt
git add sample.txt
git checkout feature-branch2
git log –oneline 
git stash
git stash list
git stash apply


5. Collaboration and Remote Repositories

Fetch the latest changes from a remote repository and rebase your local branch onto the updated 

remote branch.

Step1:Ensure that you are in the working directory of your local repository.

Run git fetch origin to fetch the latest changes from the remote repository. Replace origin with the 

name of your remote repository if it is different.

Check out the branch you want to rebase onto the updated remote branch. For example, if you want to 

rebase your feature-branch onto the updated master branch, run git checkout feature-branch .

Step2:Run git rebase origin/master , where origin/master is the remote branch you want to rebase 

onto. This command replays your commits on top of the updated remote branch.

If there are any conflicts during the rebase process, Git will pause the rebase and display the 

conflicting files. You need to resolve the conflicts manually by editing the conflicting files.

After resolving the conflicts, use git add <file> for each resolved file to stage them for the rebase.

Once all conflicts have been resolved and files have been staged, continue the rebase process by 

running git rebase –continue . This will apply the next commit on top of the updated remote branch.

If there are any further conflicts, repeat steps 5-7 until the rebase is successfully completed.

After the rebase is complete, you may need to force push your updated branch to the remote repository 

if you have already pushed the previous commits.

Use git push -f origin feature-branch to force push the updated branch. Be cautious with this step, as it 

rewrites the history and can cause issues for other collaborators.

The local branch is now rebased onto the updated remote branch.

Commands step-by-step:

git fetch origin
git checkout feature-branch
git rebase master/origin feature-branch(Resolve any conflicts if prompted)
git add <resolved-file> (Stage each resolved file)
git rebase –continue (Repeat steps 4-5 if necessary)
git push -f origin feature-branch





6. Collaboration and Remote Repositories

Write the command to merge "feature-branch" into "master" while providing a custom commit 

message for the merge

Step1:First, ensure that you are currently on the "master" branch. You can switch to the "master" 

branch using the following command: git checkout master

Step2: Initiate the merge of the "feature-branch" into "master" by using the following command:

git merge feature-branch This command will merge the changes from the "feature-branch" into the 

"master" branch.

At this point, Git will try to automatically merge the changes. If there are any conflicts (i.e., conflicting 

changes in the same files), Git will notify you and prompt you to resolve the conflicts manually. You 

can use a text editor or a specialized merge tool to address the conflicts.

Once you have resolved the conflicts, you can proceed with the merge. Git will create a new commit to 

represent the merge. 

Step3:To provide a custom commit message for the merge, use the following command: git commit -

m "Custom commit message for merging feature-branch into master" Replace "Custom commit 

message for merging feature-branch into master" with your desired commit message. Make sure to 

provide a meaningful message that accurately describes the purpose of the merge.

After entering the command, Git will create the merge commit with the provided custom commit 

message. This commit represents the merge of the changes from the "feature-branch" into the "master" 

branch.

You have successfully merged the "feature-branch" into the "master" branch while providing a custom 

commit message for the merge.

Merging branches is a crucial step in collaboration, as it brings together different sets of changes from 

various branches into a single branch, such as "master." It allows different team members to work on 

separate features or bug fixes and later integrate them into the main branch.

Commands:

git commit –m “custom commit message”
