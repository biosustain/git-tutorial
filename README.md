# Git Tutorial using

> VS Code on Binder  
> VS Code on Binder, because sometimes you need a real editor.  

[![PyPI](https://img.shields.io/pypi/v/jupyter-vscode-proxy)](https://pypi.org/project/jupyter-vscode-proxy/)
[![Install with conda](https://anaconda.org/conda-forge/jupyter-vscode-proxy/badges/installer/conda.svg)](https://github.com/conda-forge/jupyter-vscode-proxy-feedstock)

Start:
 - lab: [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/RasmussenLab/git-tutorial/master?urlpath=lab)
 - vscode: [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/RasmussenLab/git-tutorial/master?urlpath=vscode)


## Explore

You will need to setup your git email and user-name
(replace with yours in case you want to commit something, otherwise use copy-paste)

```bash
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
``` 
> could be added to local config

- create a folder with an empty repository
- setup user.name and user.email
- create branches
- etc

> try to add notes to your own fork

## Links

- [git-moji](https://gitmoji.dev/)
- Videos: [Python-Git-Client](https://www.youtube.com/watch?v=xvzo_nV9PjU), [Git-Interals](https://www.youtube.com/watch?v=MYP56QJpDr4)

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
 - VSCode [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/RasmussenLab/git-tutorial/master?urlpath=vscode/?folder=/home/jovyan/PythonTsunami)
 - JupyterLab [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/RasmussenLab/git-tutorial/master?urlpath=lab/tree/PythonTsunami)
 - Jupyter Notebook [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/RasmussenLab/git-tutorial/master?urlpath=tree/PythonTsunami)
