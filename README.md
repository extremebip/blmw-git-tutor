# Project

## Overview

This is a simple Job Listing Website adapted from Traversy Media React Crash Course [[link](https://www.youtube.com/watch?v=LDB4uaJ87e0)] but using TypeScript instead of JavaScript.

This project shows an example of incremental addition & changes using simple commit & push into a single branch. This method is best used if you're the sole developer working on a repository since this is a simple way to keep version changes throughout your development. If you have another developer collaborating as well, this method still can be used. However, you need to watch out for merge conflict. Once you get to three developers or more, it might be better to separate branches based on features or developers.

## .gitignore

This file is used to ignore files & directories from being tracked by git. It uses string pattern matching to find which files & directories to be ignored. There are some special characters that you can use, for example wildcard (*) is used to match any string and exclamation (!) is used to re-include matches that has been ignore in previous lines.

In this project, the file `src/jobs.json` is used for development database and therefore, any changes made to this file shouldn't be tracked git. You can start by adding `jobs.json` to the `.gitignore` file. Any further changes you make will no longer be tracked by git.

## Stashing Changes

This command is used to temporarily changed files into a separate branch called stash. Stashes are structured in a stack, where the newest stash will be applied first if you decide to reapply your stash. To use stash, first create `test.txt` inside the working directory. Then, run these commands:

```console
git add test.txt
git stash
```

Your `test.txt` will disappear from your directory and be stored in the stash. You can check all stashes you have by running:

```console
git stash list
```

Now, to reapply the stash's changes into your directory and deleting the stash simultaneously, run this command:

```console
git stash pop
```

Your `test.txt` will appear in your working directory. Keep in mind that applying stash into your working directory is the same as merging another branch into your current branch. If you don't modify the same files as in your stash, git will do a fast-forward merge. If yes, then you will have resolve the merge conflicts first.


## Resetting changes

You can reset one or more commits that you already have in your branch by running git reset command. Depending on the given flag, the changed files will either be put into staging area or deleted entirely. There are two flags that are mainly used. First is the `--soft` flag which put your changed files from commit(s) into your staging area. To do this, you need to make a commit for `test.txt`, then run git reset soft command.

💡 Tips: you can use `HEAD~n` into git reset to reset *n* commits from your current commit.

```console
git add test.txt
git commit -m "Test"
git reset --soft HEAD~1
```

You'll see that `test.txt` will be put into staging area. Now for the dangerous flag which is `--hard`. Unlike soft flag, hard flag will delete all the changed files from resetted commits. So unless you know what you're doing, it is advisable to avoid this command. Like before, we'll make a commit `test.text` then run git reset hard on that commit.

```console
git add test.txt
git commit -m "Test"
git reset --hard HEAD~1
```

As you can see, the file `test.txt` is removed from existence.

## Next step

Now, we will move on to how you can merge your branches. Run this command to switch to that branch:

```console
git checkout 2-branching/first
```