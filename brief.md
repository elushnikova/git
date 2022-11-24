# git brief

Show brief git log with commit SHA and message first line only.

## Sample output

```bash
0123456 chore: Open dev server to LAN
ef01234 feat: Add detail tabs
56789ab feat: Add 404 page
```

## Original command

```bash
git log --oneline --no-decorate
```

## Set global alias

```bash
git config --global alias.brief 'log --oneline --no-decorate'
```

## Usage

```bash
# Show all commits
git brief

# Show last 10 commits
git brief -10
```

## Remove global alias

```bash
git config --global --unset alias.brief
```
