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

- create a folder with an empty repository (default `examples`)
- `git init` in console to initialize repo
- setup user.name and user.email
- create files, stage them and see what files are created in `.git/objects`
- commit files and check `.git/objects`
- create branches and checkout `.git/refs` and `git/branches` folder
- look at `git/HEAD` (maybe `git/ORIG_HEAD` if it exists)

> try to create your own fork, and try to lauch it on [mybinder](https://mybinder.org/)

## Links

- [git-moji](https://gitmoji.dev/)
- [curious git](https://matthew-brett.github.io/curious-git/) - detailed intro to the inner workings
- [git parable](http://practical-neuroimaging.github.io/git_parable.html) - why git came to exist
- Videos: 
    - [Python-Git-Client](https://www.youtube.com/watch?v=xvzo_nV9PjU)
    - [Git-Interals](https://www.youtube.com/watch?v=MYP56QJpDr4)
    - [Git PyData Global 2021 talk](https://www.youtube.com/watch?v=rBYC3dEOOyI)

## Inspect git objects

```bash
git log --format=raw
git cat-file -p <hash> # pretty print
git cat-file -t <hash> # type

# the binary object can also be inspected using different tools,
# which might make it easier to navigate to certain blobs:
cat .git/objects/<2c>/<38c> | zlib-flate -uncompress
```

## Note

> Should be Run the Python Tsunami notebooks on binder.
?urlpath=vscode/?folder
Go directly to Python Tsunami repository in
 - VSCode [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/biosustain/git-tutorial/master?urlpath=vscode/?folder=/home/jovyan/PythonTsunami)
 - JupyterLab [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/biosustain/git-tutorial/master?urlpath=lab/tree/PythonTsunami)
 - Jupyter Notebook [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/biosustain/git-tutorial/master?urlpath=tree/PythonTsunami)
