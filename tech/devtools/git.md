# `git`

## Common

- `git -C repo-dir <command>` - Execute git command in a different directory 

## Undo

Cmd | Description
-- | --
`git reset --hard` | Reset back to last commit, discarding changes
`git reset --soft HEAD~1` | Undo one commit, leaving changes
`git reset --hard HEAD~1` | Undo one commit, discarding changes
`git commit --amend` | Change last commit message

## GitHub

### Checkout remote pull request

`git fetch <remote> pull/<id>/head:<local_branch_name>` and checkout.

Example:

`git fetch origin pull/1/head:pr1`
`git checkout pr1`

## Submodules and Subtrees

- https://nering.dev/2016/git-submodules-vs-subtrees/
- https://www.atlassian.com/git/tutorials/git-subtree

## Extended

- https://gerrit-review.googlesource.com/Documentation/intro-user.html
- https://www.mediawiki.org/wiki/Gerrit/Tutorial
- https://gerrit.googlesource.com/git-repo/
- https://source.android.com/setup/develop/repo
- https://github.com/mixu/gr