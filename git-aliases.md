# Contents

- [git brief](#git-brief) - show brief git log
- [git publish \$branch](#git-publish-branch) - publish `$branch` to `origin`
- [git master](#git-master) - checkout to `master` and pull changes from `origin`
- [git trim](#git-trim) - show branches that don't exist at `origin`
- [git review \$pr \$branch](#git-review-pr-branch) - download code from pull request to new local branch.

Learn more at [Git documentation](https://git-scm.com/book/en/v2/Git-Basics-Git-Aliases).

Check what aliases you already have with this command:

```bash
# Get alias entries
git config -l | grep alias
```

# git brief

Show brief git log with commit SHA and message first line only.

[Back to contents](#contents)

```bash
# Sample output
0123456 chore: Open dev server to LAN
ef01234 feat: Add detail tabs
56789ab feat: Add 404 page
```

```bash
# Original command
git log --oneline --no-decorate
```

```bash
# Set global alias
git config --global alias.brief 'log --oneline --no-decorate'
```

```bash
# Usage
git brief
```

```bash
# Usage: show last 10 commits
git brief -10
```

```bash
# Remove global alias
git config --global --unset alias.brief
```

# git publish `$branch`

Publish `$branch` to remote `origin`.

[Back to contents](#contents)

```bash
# Original command
git push -u origin $branch
```

```bash
# Set global alias
git config --global alias.publish 'push -u origin'
```

```bash
# Usage
git publish $branch
```

```bash
# Remove global alias
git config --global --unset alias.publish
```

# git master

Checkout to `master` branch and pull changes from remote `origin`.

[Back to contents](#contents)

```bash
# Original commands
git checkout master
git pull
```

```bash
# Set global alias
git config --global alias.master '!git checkout master && git pull'
```

```bash
# Usage
git master
```

```bash
# Remove global alias
git config --global --unset alias.master
```

# git trim

Show branches that don't exist at remote `origin` anymore.

[Back to contents](#contents)

```bash
# Sample output
clear-counter  012345678 [gone] fix: Allow user to clear counter value
404-page       9abcdef01 [gone] feat: Add 404 page
```

```bash
# Original commands
git remote prune origin
git branch -v | grep gone
```

```bash
# Set global alias
git config --global alias.trim '!git remote prune origin && git branch -v | grep gone'
```

```bash
# Usage
git trim
```

```bash
# Remove global alias
git config --global --unset alias.trim
```

# git review `$pr` `$branch`
Download code from pull request to new local branch.

[Back to contents](#contents)

```bash
# Original command
git fetch origin pull/$pr/head:$branch

# E.g.
git fetch origin pull/5/head:alexey
```

```bash
# Set global alias
git config --global alias.review '!f() {\
  git fetch origin pull/$1/head:$2;\
}; f'
```

```bash
# Usage
git review $pr $branch

# E.g.
git review 5 alexey
```

```bash
# Remove global alias
git config --global --unset alias.review
```