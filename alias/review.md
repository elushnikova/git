# git review `$prNumber` `$branch`

Download code from pull request to new local branch and checkout to it.

## Original commands

```bash
git fetch origin pull/$prNumber/head:$branch
git checkout $branch

# E.g.
git fetch origin pull/5/head:alexey
git checkout alexey
```

## Set global alias

```bash
git config --global alias.review '!f() {\
  git fetch origin pull/$1/head:$2 && git checkout $2;\
}; f'
```

## Usage

```bash
git review $prNumber $branch

# E.g.
git review 5 alexey
```

## Remove global alias

```bash
git config --global --unset alias.review
```
