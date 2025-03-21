# Git - good to knows

## How do you update commit messages?
1. Changing the message of older or multiple commit messages
2. If you need to amend the message for multiple commits or an older commit, you can use interactive rebase, then force push to change the commit history.
3. On the command line, navigate to the repository that contains the commit you want to amend.
4. Use the `git rebase -i HEAD~n` command to display a list of the last `n` commits in your default text editor.
```
# Displays a list of the last 3 commits on the current branch
$ git rebase -i HEAD~3
The list will look similar to the following:

pick e499d89 Delete CNAME
pick 0c39034 Better README
pick f7fde4a Change the commit message but push the same commit.

# Rebase 9fdb3bd..f7fde4a onto 9fdb3bd
#
# Commands:
# p, pick = use commit
# r, reword = use commit, but edit the commit message
# e, edit = use commit, but stop for amending
# s, squash = use commit, but meld into previous commit
# f, fixup = like "squash", but discard this commit's log message
# x, exec = run command (the rest of the line) using shell
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
# Note that empty commits are commented out
```

5. Replace `pick` with `reword` before each commit message you want to change.
```
pick e499d89 Delete CNAME
reword 0c39034 Better README
reword f7fde4a Change the commit message but push the same commit.
Save and close the commit list file.
```
6. In each resulting commit file, type the new commit message, save the file, and close it.
https://docs.github.com/en/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/changing-a-commit-message
