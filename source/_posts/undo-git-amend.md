---
title: undo git amend
description: undo a git commit --amend
date: 2022-07-19 15:16:11
tags:
  - git
categories:
  - [git]
  - [issue]
---

Sometimes one may want to undo a git amend. In my case, I push the commit to the remote, and then did an amend on the local side, which cause conflict. The reason is that git commit --amend creates a new commit and detaches the previous commit, and when you push to the remote there will be a conflict since it finds two different commits.

To undo amend:

1. find the `<hash>` of the original commit by running `git reflog`
2. run `git reset --mixed <hash>` to reset the commit to the original state

Difference between --hard, --soft, --mixed in `git reset`:

- --hard: reset the commit to the original state, throw away all changes
- --soft: reset the commit to the original state, but keep the changes in the working tree
- --mixed: reset the commit to the original state, but keep the changes in the working tree, and keep the changes in the index

## Reference

- <https://dev.to/flyingdot/git-magic-1-undo-git-amend-196g>
- <https://www.howtogeek.com/devops/how-does-git-reset-actually-work-soft-hard-and-mixed-resets-explained/#:~:text=1%20git%20reset%20--soft%2C%20which%20will%20keep%20your,files%20the%20same%20but%20unstages%20the%20changes.%20>
