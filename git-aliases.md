# Contents

- [git publish \$branch](#git-publish-branch) - publish `$branch` to `origin`
- [git master](#git-master) - checkout to `master` and pull changes from `origin`
- [git review \$pr \$branch](#git-review-pr-branch) - download code from pull request to new local branch for review.

Learn more at [Git documentation](https://git-scm.com/book/en/v2/Git-Basics-Git-Aliases).

Check what aliases you already have with this command:

```bash
# Get alias entries
git config -l | grep alias
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

# git review `$pr` `$branch`

Download code from pull request to new local branch for review.

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
