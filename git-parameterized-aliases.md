# git review `$pr` `$branch`
Download code from pull request to new local branch and checkout to it.

[Back to contents](#contents)

```bash
# Original commands
git fetch origin pull/$pr/head:$branch
git checkout $branch

# E.g.
git fetch origin pull/5/head:alexey
git checkout alexey
```

```bash
# Set global alias
git config --global alias.review '!f() {\
  git fetch origin pull/$1/head:$2 && git checkout $2;\
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