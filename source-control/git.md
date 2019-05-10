# git

## Revert actions

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
