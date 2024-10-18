# Branching & Merging

As you may notice, you are checking out into one of the branch inside a `2-branching` directory. There are several branches that we will use in this practices to show you several methods of moving commits from one branch to another branch.

## Merge Commit

This is the simplest method of merging changes between branches. Merge commit works by specifying which branch you want to merge with your current branch, then git will create a new commit that will have two commit parents, one to your latest commit in the current branch and one to the other branch. Then, the all files from commits starting from where both branches diverge up until this commit merge will be added into this current branch. To start, checkout to second branch then merge the first branch into the second branch.

```console
git checkout 2-branching/second
git merge 2-branching/first
```

If you tried the commands above, git is unable to merge two branches. This is because when merging, it is possible for some files to have merge conflicts. Merge conflicts are situation where different developers make different changes into a same line in a same file. You need to resolve these merge conflicts first before the merging can be completed.

In real project, please **communicate** with developers whose changes are affected by these merge conflicts to resolve them together.

## Cherry Pick

Other than merging, you can also get commits from other branch by cherry-picking. Cherry-picking means that you take all changed files from your chosen commits, then create a new commit with the same messages (you can edit it as you need to) in your current branch. To start, checkout to the third branch, then cherry pick a commit labelled `B` in the second branch.

```console
git checkout 2-branching/third
git cherry-pick 15840531
```

As you can see, the new commit will have the same changed files as in the commit in the second branch. However, this creates a new commit with different commit SHA than the cherry-picked commit.

## Rebase

This is another method of merging two branches other than using merge commit. Rebasing is an action to move or combine a sequence of commits to new base commits. Rebasing needs a base as the parameter. Base can be a name of a branch or a commit SHA. The main purpose of using rebasing instead of merge commit is to keep your git history to be linear. Linear history is easier to skim through and to find commits that yield bugs. To start, you can run these commands:

```console
git checkout 2-branching/fourth
git rebase 2-branching/third
```

As you can see, the history on `2-branching/fourth` will follow `2-branching/third` and the original commits on the current branch will be re-created.

Another powerful tool you can use with rebase is interactive rebase, where you can have more control over how you rebase your commits. To start, checkout to the fifth branch and add `-i` flag when you're running interactive rebase.

```console
git checkout 2-branching/fifth
git rebase -i 2-branching/third
```

This will bring up git rebase interactive editor. There will be a list of commits and an action that you can do to each commit. The list is ordered from the oldest commit at the top and the latest commit on the bottom. You can change the order of the commit, change the message of the commit, squash with previous commit, delete the commit, and much more. The default editor when you install git is usually vim, so if you're more familiar with other editor, you can check this article here:

https://www.kevinkuszyk.com/2016/03/08/git-tips-2-change-editor-for-interactive-git-rebase/

## Next step

Now we'll move on how you can utilize a feature in Github called Pull Request to request merging changes from current branch to target branch.

```console
git checkout 3-pull-request
```