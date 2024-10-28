# Git Tutorial using

> VS Code on Binder  
> VS Code on Binder, because sometimes you need a real editor.  

[![PyPI](https://img.shields.io/pypi/v/jupyter-vscode-proxy)](https://pypi.org/project/jupyter-vscode-proxy/)
[![Install with conda](https://img.shields.io/conda/vn/conda-forge/jupyter-vscode-proxy.svg)](https://github.com/conda-forge/jupyter-vscode-proxy-feedstock)

Start:
 - lab: [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/biosustain/git-tutorial/master?urlpath=lab)
 - vscode: [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/biosustain/git-tutorial/master?urlpath=vscode?folder=/home/jovyan/examples)


## Explore

You will need to setup your git email and user-name
(replace with yours in case you want to commit something, otherwise use copy-paste)

```bash
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
``` 
> could be added to local config using `git config user...`

### Steps

- create a folder with an empty repository (default `examples`
  directly openend in VSCode on binder)
- open instruction: `code-server ../README.md` (local computer: `code ../README.md`)
- `git init` in console to initialize repo (or via command palette "Git: Initialize Repository")
- setup user.name and user.email (see above)
- create files, stage them and see what files are created in `.git/objects`
- commit files and check `.git/objects`
- create branches and checkout `.git/refs` (`git/branches` is a legacy folder,see [here](https://stackoverflow.com/a/10398507/9684872))
- look at `git/HEAD` (maybe `git/ORIG_HEAD` if it exists)

> try to create your own fork, and try to lauch it on [mybinder](https://mybinder.org/)

You can find a recording of the tutorial on YouTube which was done for the Data Club seminar
between DTU biosustain and DTU bioengineering (see sections in description of Video).

[![YouTube Preview](https://img.youtube.com/vi/5iB7qc5zRjQ/maxresdefault.jpg
)](https://www.youtube.com/watch?v=5iB7qc5zRjQ)

> The Live Demo is not pulling the merge commit after merging the branch on GitHub.
> Maybe this could be a possible small follow-up where the repository could be cloned 
> from GitHub: [github.com/biosustain/git_training_henry_recording](https://github.com/biosustain/git_training_henry_recording)

## Links

- [git-moji](https://gitmoji.dev/)
- [curious git](https://matthew-brett.github.io/curious-git/) - detailed intro to the inner workings
- [git parable](http://practical-neuroimaging.github.io/git_parable.html) - why git came to exist
- Videos: 
    - [Python-Git-Client](https://www.youtube.com/watch?v=xvzo_nV9PjU)
    - [Git-Interals](https://www.youtube.com/watch?v=MYP56QJpDr4) - shows how git works
    - [Git PyData Global 2021 talk](https://www.youtube.com/watch?v=rBYC3dEOOyI)
    - Scoot Chacon’s [“So you thin you know git” talk](https://www.youtube.com/watch?v=aolI_Rz0ZqY) (FOSDEM 2024), 
    notes on [blog](https://blog.gitbutler.com/git-tips-1-theres-a-git-config-for-that/) 

## Inspect git objects

```bash
git log --format=raw
git cat-file -p <hash> # pretty print
git cat-file -t <hash> # type

# the binary object can also be inspected using different tools,
# which might make it easier to navigate to certain blobs:
cat .git/objects/<2c>/<38c> | zlib-flate -uncompress
```

You can find the latest objects and compare it to the log

```bash
find .git/objects  -type f -exec ls -lt {} + | head -n 10
git log --format=raw -n 3
```

If you wonder what the codes in a tree mean, check this stackexchange
[answer](https://unix.stackexchange.com/a/450488/349761)


## What's happening?

- You commited ten commits and dit not yet push. Git complains about too much data.
  You realize that you commited your source data. You delete it and commit again, but the problem still persists.
- You commit something and push. You realize your last commit was wrong. You undo it and commit again. Git complains that 
  you cannot push.
