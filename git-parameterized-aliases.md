```
git config --global alias.review '!f() {\
  git fetch origin pull/$1/head:$2;\
}; f'
```

git fetch origin pull/9/head:karlen
git review 9 karlen