_This is a coursework on git taught by Udacity | Completed in August 2020_

# Git Tutorial

This repo contains a list of useful git commands as taught by the free online Udacity [course](https://www.udacity.com/course/version-control-with-git--ud123).

<p align="center"><img src="git.jpeg" height= "200"/></p>

## Version Control

### Terminology

A dictionary of terms can be found [here](ud123-git-keyterms.pdf).

**Source code manager (SCM)**
:   Git is a  or version control system (VCS) which means a tool that manages different versions of source code. Git can be downloaded from [here]( https://git-scm.com/).

**Commit**
:   saves your project's files and any information about them

**Repository**
:   directory which contains project work as well as hidden files which are used to communicate with Git.

**Working Directory**
:   The files visible in my computer's file system or where .git file is placed. Different from the concept of *current working directory*. 

**Checkout**
:   when the content in the repository has been copied to the Working Directory.

**Staging Area/Index**
:   A file in the Git directory that stores information about what will go into the next commit. Files on the Staging Index are poised to be added to the repository.

**SHA** 
:   is an ID number for each commit, it is a 40-character string composed of characters and stands for "Secure Hash Algorithm". 

**Branch** 
:   A new line of development that diverges from the main line of development. This line of development can continue without altering the main line. 

## Configuring Git

Git can be configured by using the `git config` command.

For example:

```
# sets up Git with name and email
git config --global user.name "<Your-Full-Name>"

git config --global user.email "<your-email-address>"

```

## Creating a Repo

Use `git init` to create a new, empty repo in the current directory. Git does this by adding a .git directory which contains files to keep track of everything.  

## Cloning a Repo

Use `git clone` to create an identical copy of an existing repository. 

```
git clone <path-to-repository-to-clone> <optional-name-of-directory>
```

## Checking status of Repo

The `git status` command displays which files have been changed/added in directory that is different from the repo.

> Use the git status command after any other command to understand how Git works


The`git log` command shows the commits submitted into the repo.

> git log prints the list of commits using the `less` command in shell. Use spacebar to scroll one page down, `b` to scroll one page up, and `q` to quit.

> One option is to use the `git log --oneline` to display each commit as one line with just the first letters of the SHA and the commit message.

> `git log --stat` shows the files that have been changed in the commit as well as the number of lines that have been added or deleted. 

> `git log -p` can be used to display the actual changes (locations and codes) made to a file.


The `git show` command will only show the latest or one commit (if SHA is provided). The output is the same as the `git log -p` command. 

> `git show` can add the `--stat` , `-p`, and `-w` flags to show number of files changed, difference with old file, and to ignore changes to whitespace.

## Adding files to the Stage Index

The `git add <file1> <file2>` command add files from the Working Directory to the staging index. 

> Use `git add .` to stage everything in the the current directory. The period refers to the current directory including all nested files and directories.

## Committing files

The `git commit` command take file from the staging index and save them in the repository. 

> **The goal is that each commit has a single focus**. Each commit should record a single-unit change. Each commit should make a change to just one aspect of the project. A commit shouldn't include unrelated changes. That way, if it turns out that one change had a bug and we had to undo it, we don't have to undo the other change too. 

> `git commit` will open the code editor to prompt for a commit message if the `-m` flag is not used.

> When adding commit messages, explain what the commit does but do not explain why or how the changes are made!. Do not use the word and, if you have to use "and" break the changes into separate commits. Be consistent in how you write commit messages!

`git diff` displays the changes that have been made but haven't been committed yet. Output is similar to `git log -p` command. 

The `.gitignore` file is used to tell Git about the files Git should not track. Create `.gitignore` file in the same directory `.git` is in and add file names inside the `.gitignore` file to make sure that a file isn't committed to the project!

> `.gitignore` can use the concept called globbing which allows the use of special characters to match patterns. E.g. `*` matches 0 or more characters, `?` matches 1 character, `[abc]` matches a or b or c, `**` matches nested directories - `a/**/z` matches a/z, a/b/z, a/b/c/z.
