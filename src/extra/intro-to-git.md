# Introduction to Git
Git is a [version control system](https://www.atlassian.com/git/tutorials/what-is-version-control) (VCS) which allows you to handle changes to code over time. The key difference between a VCS and just saving your file is that a VCS will allow you to "go back in time" and edit things in the past, whereas saving only usually allows you to go back to the last time you saved.

```admonish note title="Installing Git"
During the installation of git, you can generally follow the defaults. However, when it asks you to select a text editor, you should *not* use the default suggestion of Vim unless you know what you're doing. Select another program such as Notepad++.

To install git, follow the instructions on [Git SCM's Installing Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) guide.

When you have finished installing, you should restart your terminal to ensure the changes take effect.
```

## What is a commit?
A commit is a version of your code at a single point in time. The way git handles commits is by tracking *changes*, so your commits can be thought of as a series of changes over time. 

| Commit # | Addition                | Deletion | Total File                         |
|----------|-------------------------|----------|------------------------------------|
| 1        | Hello World             |          | Hello World                        |
| 2        | , my name is John Smith |          | Hello World, my name is John Smith |
| 3        | Doe                     | Smith    | Hello World, my name is John Doe   |

### Google Drive Example

### Commit Flow
1. No changes
2. Changes (unstaged)
3. Changes (staged)
4. Committed 

## Basic Usage

## What is a branch?

## What is remote?

## Git Command Reference
### Basic Commands 
The basic commands below you are required to know, and should be able to describe their usage on a quiz.

git init
git add
git commit
git log
git status
git reset

### Additional Commands
The following additional commands are not required for this course, but you will need them regularly and you may find it useful to understand them.

git stash
git stash pop
git revert
git branch
git checkout
