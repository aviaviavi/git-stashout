# git-stashout

A custom `git checkout` command to automatically manage a per-branch stash so you
can easily switch between branches without having to either make WIP commits
every time or manually stash and pop your changes.

If you often find yourself working on multiple branches and switching between
them, you might be familiar with a workflow such as:

- Do some work on branch-a
- Not ready to commit, but need to switch to branch-b
- `git stash && git checkout branch-b`
- Do some work on branch b
- Not ready to commit, but need to switch to branch-a
- `git stash && git checkout branch-a && git stash pop stash@{1}`

If this workflow sounds familiar to you, it's where `git-stashout` shines!

## Installing

1. Put `git-stashout` somewhere in your `PATH`
2. [Optional] Source `git-stashout-completion` to get branch completion when
   typing the branch name

## Using

```shell
$ git stashout <branch>
```

This will stash your current changes, and checkout `<branch>`. If `<branch>` had
a previous stash from `stashout`, it will be popped off the stash list so you
can resume your progress. Now you have easy task switching without needing to
amend your WIP commits!
