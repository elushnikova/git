# git trim

Show branches that don't exist at remote `origin` anymore.

## Sample output

```bash
clear-counter  012345678 [gone] fix: Allow user to clear counter value
404-page       9abcdef01 [gone] feat: Add 404 page
```

## Original commands

```bash
git remote prune origin
git branch -v | grep gone
```

## Set global alias

```bash
git config --global alias.trim '!git remote prune origin && git branch -v | grep gone'
```

## Usage

```bash
git trim
```

## Remove global alias

```bash
git config --global --unset alias.trim
```
