# Workshop on the 5th of November 2025

> to be continued.

## How to work with the repository

You need to be logged in to GitHub and have a GitHub account for all these options:
[Create a GitHub account](https://github.com/join)

> ToDo: Make brief video for preperations and as reference

### On the GitHub website

- Create a fork of the repository and work there

### In VSCode in the browser without a workspace

You need to be logged in to GitHub and have a GitHub account.

- [github.dev/enryH/recipe-book](https://github.dev/enryH/recipe-book)

### In GitHub Workspace

- Open in GitHub Codespace if you want to build and preview the website without 
  creating a commit:

  [![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/codespaces/new?hide_repo_select=true&ref=main&repo=1053356553&skip_quickstart=true)

### On local comoputer

Install both an editor, e.g. [VSCode](https://code.visualstudio.com/download) (recommended), 
and the command line program [git](https://git-scm.com/install/)

## Exercises

Choose your favrioute.

### Add your recipe and request a review [basic]

> This I have to test with someone 

- create a fork or request access as collaborator of the the recipe-repo
- add and commit your recipe. The next two steps can be done either as first or 
  second, why?
  - create a branch with your new recipe, e.g. `add-aioli-pasta`
  - create a commit with your new recipe draft
- open a Pull (Merge) Request on GitHub to `origin/main`
- ask someone (by inviting them) to review your PR and get an approval
  - I set-up the repo to require at least one approval before a merge is possible 
    (best-practice)

### Create a merge conflict [medium]

Work simulatenously on the same files, writing new content to the same sections in text.

- `pasta/boscaiola.md` is incomplete. Complete it on your own branch.
  - the first to commit to main, will have no problems as the update passes
  - everyone after has to resolve merge conflicts as the changes are not easy to resolve
    automatically (draw out the graph to see why)


How to merge:
  - Open a GitHub PR, follow the instructions there 
    (see [Web-Editor](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-on-github))
  - too large differences have to resolved locally, e.g. using the 
    [VSCode Merge Editor](https://code.visualstudio.com/docs/sourcecontrol/overview). See 
    [this tutorial](https://www.youtube.com/watch?v=HosPml1qkrg).

How and when to integrate changes from the main branch?
- setting in Repo to suggest to 'Update branch' (you need to own the repo)
- merge in changes locally using `git merge`
- leave it to git and create a 'merge commit' which has two parents

### Rewrite history [advanced]

### Add and remove large files [advanced]

GitHub set a limit of 100MB per file. It's a *best pratice* to only commit code and 
documenation, and if needed small example datasets. Adding larger files than 100MB is 
possible locally, but then the commit cannot be syncronized with the remote, hosted
repository.

- use a large file (e.g. these ones: )
- commit them in a data folder
- add a few more commits (loading the files or what else)
- `rebase` to remove the files again, see 
  [this tutorial](https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase).
  Options:
  - edit the commit where you added the large files and remove them
  - commit a new delete commit and squash it into the one where you added the files

> Please not that files synchronized once to GitHub stay there 'forever'. If you update
> your history (your commits) they are lost by being not referenced anywhere, but anyone
> who knows the commit-id and has access can in princple find them again
