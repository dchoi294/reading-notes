# Class 3 Reading Notes

## Git Intro

**Cloning**  
*git clone URL*

- This will create a copy of an existing Git repository from a particular server by using the clone command with a repository's URL.

**Workflow**
*Local Repository Structure*

- Working Directory: The actual files reside here.
- Index: The area used for staging
- Head: Points to the most recent commit

The Life Cycle of File Status

- After you edit a file, Git flags it as modified because of hcnages amde after the previous commit.
- You stage the modified file.
- Then, you commit staged changes.

*Coding*
Check File Status => git status
Tracking and Staging a New File

- Single file => git add filename
- All files => git add .
Committing a File => git commit -m "brief message of changing"
Committing All Changes => git commit -a
Pushing Changes => git push origin master

**Remote Repositories**  
Teams can use remote repositoreis to push information to and pull data from.

*Cloned Repositories*  
Git will automatically give the name "origin" tothe server from which you lconed and the name "master" to your local branch.

[Back to home](../README.md)
