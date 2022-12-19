# git push --delete

[git push -d](https://git-scm.com/docs/git-push#Documentation/git-push.txt--d)

> All listed refs are deleted from the remote repository.

```bash
git push -d origin mybranch
git push --delete origin mybranch
```

[git push -d](https://git-scm.com/docs/git-push#Documentation/git-push.txt--d)

> This is the same as prefixing all refs with a colon.

```bash
git push origin :mybranch
```

[SO question #7303687](https://stackoverflow.com/q/7303687):

> Why does Git use a colon (`:<branch>`) to delete remote branches?
>
> is there a deeper meaning behind the colon symbol that I didn't know?

[SO answer #7303710](https://stackoverflow.com/a/7303710):

> It is not the meaning of the `:` per se, but what is present, or rather absent before it.
>
> The refspec format is
>
> `<+><source>:<destination>`
>
> (optional + for non-fast forward)
>
> So when you do something like `git push origin :featureA`, you are specifying an empty source ref and basically making the destination "empty" or deleting it.
>
> PS: Note that the refspec of `:` or nothing doesn't mean push nothing to nothing however. It makes git to push "matching" branches: for every branch that exists on the local side, the remote side is updated if a branch of the same name already exists on the remote side.

[SO answer #7303708](https://stackoverflow.com/a/7303708):

> The colon isn't a "delete flag". Note that git push and git pull both accept zero or more refspecs as their final argument(s). Now [read about refspecs](http://git-scm.com/book/en/Git-Internals-The-Refspec). A colon separates source from destination in a refspec. The command `git push origin :foo` has an empty source and essentially says "push nothing to branch foo of origin", or, in other words, "make branch foo on origin not exist".
