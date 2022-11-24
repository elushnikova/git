# git merge --allow-unrelated-histories

> If you want to merge project-a into project-b
>
> ```bash
> cd path/to/project-b
> git remote add project-a /path/to/project-a
> git fetch project-a --tags
> git merge --allow-unrelated-histories project-a/master # or whichever branch you want to merge
> git remote remove project-a
> ```

Source: [StackOverflow answer #10548919](https://stackoverflow.com/a/10548919).

I merged unrelated gist histories for this repository, and Git history timeline looks like this:

![Unrelated git histories timeline](screenshots/merge-unrelated.png)
