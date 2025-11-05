# Workshop on the 5th of November 2025

## How to work with the repository

You need to be logged in to GitHub and have a GitHub account for all these options:
[Create a GitHub account](https://github.com/join)


These information might be helpful:

 - basic Markdown syntax: [Mastering Markdown](https://guides.github.com/features/mastering-markdown/)

We will by default be using VS Code in the Browser with a GitHub Codespace connected.
Please have a look at the (video) tutorials before the course:
- VSCode in the Browser: [vscode-web](https://code.visualstudio.com/docs/setup/vscode-web)
            ( we will connect a remote machine using a codespace)
- Codespaces: [codespaces/quickstart](https://docs.github.com/en/codespaces/quickstart)

### On the GitHub website

- [Create a fork](https://github.com/biosustain/recipe-book/fork) 
  of the repository and work there

### In VSCode in the browser without a workspace

You need to be logged in to GitHub and have a GitHub account.

- [github.com/biosustain/recipe-book (Website)](https://github.com/biosustain/recipe-book)
- [github.dev/biosustain/recipe-book (Editor)](https://github.dev/biosustain/recipe-book)

### In GitHub Workspace

- Open in GitHub Codespace if you want to build and preview the website without
  creating a commit:

  [![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/codespaces/new?hide_repo_select=true&amp%3Bref=main&amp%3Brepo=1053356553&amp%3Bskip_quickstart=true&skip_quickstart=true&machine=basicLinux32gb&repo=1053356553&ref=main&devcontainer_path=.devcontainer%2Fdevcontainer.json&geo=EuropeWest)

> If you start from the `biosustain/recipe-book` repository you can create a codespace,
> and it will automatically create a fork for you if you don't have write access.

### On local computer

Install both an editor, e.g. [VSCode](https://code.visualstudio.com/download) (recommended),
and the command line program [git](https://git-scm.com/install/)

## Exercises

Choose your favourite. We will focus on the basic one, but you can try the others
as well or instead. Find exercise groups seeing the marks on the tables.

### Add your recipe and request a review [basic]

- [create a fork](https://github.com/biosustain/recipe-book/fork)
  (or request access as collaborator of the the recipe-repo)
- create a new branch from `main`, e.g. `add-aioli-pasta`
- create a commit with your new recipe draft
- open a Pull (Merge) Request on GitHub to `origin/main`
- ask someone (by inviting them) to review your PR and get an approval
  - I set-up the repo to require at least one approval before a merge is possible
    (best-practice)
- merge the PR into `main` (you can do it yourself after getting the approval)
  - check out your options (merge, squash, rebase) and choose one
- syncronize your branch with `main` with `origin/main` (before adding a new recipe)

<details>
<summary>See full pass through exercise</summary>

[![GitHub Codespaces & VS Code in the Browser - Video Tutorial](https://img.youtube.com/vi/b3uTxjO7tAc/maxresdefault.jpg)](https://www.youtube.com/watch?v=b3uTxjO7tAc)

<iframe width="560" height="315" src="https://www.youtube.com/embed/b3uTxjO7tAc?si=oRVMYlZtwpZ0iOhx" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

Watch this video for a walkthrough of using GitHub Codespaces and VS Code in the browser.

Additional steps:
- check out to `main` branch
- sync `fork/main` with `origin/main` on your fork (on GitHub website of your fork)
- delete your codespaces afterwards to not use up all your credits: 
  [Deleting a codespace](https://docs.github.com/en/codespaces/developing-in-a-codespace/deleting-a-codespace#deleting-a-codespace)
</details>

### Create a merge conflict [medium]

Work simulatenously on the same files, writing new content to the same sections in text.

- `pasta/boscaiola.md` is incomplete. Complete it on your own branch.
  - the first to commit to main, will have no problems as the update passes
  - everyone after has to resolve merge conflicts as the changes are not easy to resolve
    automatically (draw out the graph to see why)

How to merge:

- Open a GitHub PR, follow the instructions there
  (see [Web-Editor](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-on-github))
- too large differences have to be resolved locally, e.g. using the
  [VSCode Merge Editor](https://code.visualstudio.com/docs/sourcecontrol/overview). See
  [this tutorial](https://www.youtube.com/watch?v=HosPml1qkrg).

How and when to integrate changes from the main branch?

- setting in repository on GitHub to suggest to 'Update branch' (you need to own the repo)
- merge in changes locally using `git merge`
- leave it to git and create a 'merge commit' which has two parents

### Rewrite history [advanced]

> You can do this on your own repository or the recipe-book repo on a branch.

- add a few more commits (loading the files or what else)
- `rebase interactive` to remove the files again, see
  [this tutorial](https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase).
  Please make sure you understand one of it's main comments:
  > "It's very important to understand that even though the branch looks the same,
  >  it's composed of entirely new commits."
- edit, squash, delete or reorder commits

Try an interactive rebase to rewrite history. To edit the last 4 commits, use:

```bash
git rebase -i HEAD~4
```
or with respect to the `main` branch:
```bash
git rebase -i main
```

All the instructions will be visable to you in your default editor. Try to follow them
using the help of the linked tutorial.

<details>
<summary>What is an interactive rebase?</summary>

An Interactive rebase is a Git command that allows you to edit, reorder, squash,
or delete commits in your branch's history. This is useful for cleaning up your commit
history before merging changes, combining related commits, or removing mistakes.

Common actions during interactive rebase:
- `pick`: Use the commit as is.
- `reword`: Edit the commit message.
- `edit`: Pause to amend the commit.
- `squash`: Combine this commit with the previous one.
- `drop`: Remove the commit.

It will look something similar to this (taken from the tutorial linked above):

```bash
pick 2231360 some old commit
pick ee2adc2 Adds new feature


# Rebase 2cf755d..ee2adc2 onto 2cf755d (9 commands)
#
# Commands:
# p, pick = use commit
# r, reword = use commit, but edit the commit message
# e, edit = use commit, but stop for amending
# s, squash = use commit, but meld into previous commit
# f, fixup = like "squash", but discard this commit's log message
# x, exec = run command (the rest of the line) using shell
# d, drop = remove commit
```

workflow:
1. Run `git rebase -i HEAD~4` to open the last 4 commits in your editor.
2. Change the action keywords as needed.
3. Save and close the editor to apply changes.
4. Resolve any conflicts if prompted.

> Interactive rebase rewrites commit history. Only use it on branches that haven't 
  been shared with others, or coordinate closely with collaborators to avoid confusion.

</details>

### Add and remove large files [advanced]

GitHub set a limit of 100MB per file. It's a _best pratice_ to only commit code and
documenation, and if needed small example datasets. Adding larger files than 100MB is
possible locally, but then the commit cannot be syncronized with the remote, hosted
repository.

- use a large file generating some random large files (e.g. this
  [one](https://drive.google.com/drive/folders/1xvYoWVzzgU1mGCG07tvv6V03mR7meC1Q?usp=sharing
  I created running the Python code below):

  ```python
  import numpy as np
  alphabet = np.array(['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm',
       'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z'],
      dtype='<U1')
  mb = 1024*1024
  n = 105*mb  # number of random characters to get >100MB so GitHub rejects it
  np.random.choice(np.fromstring(alphabet, dtype='<U1'), n)
  ```

- commit them in a data folder
- add a few more commits (loading the files or what else)
- try to push the changes to GitHub, it will fail
  <details>
  <summary>See error you will encounter uploading large files</summary>

  I added two commits, where the older one (the first one) contains a large file:

  ```
  heweb@nnfcb-l1106 recipe-book % git push
  Enumerating objects: 9, done.
  Counting objects: 100% (9/9), done.
  Delta compression using up to 11 threads
  Compressing objects: 100% (7/7), done.
  Writing objects: 100% (7/7), 66.75 MiB | 31.34 MiB/s, done.
  Total 7 (delta 2), reused 0 (delta 0), pack-reused 0
  remote: Resolving deltas: 100% (2/2), completed with 1 local object.
  remote: error: Trace: cb745b39bf3e1c2e15b6a344ef0eb8c2610555ec1fb16bb2773facc475e525be
  remote: error: See https://gh.io/lfs for more information.
  remote: error: File large_text_file.txt is 105.00 MB; this exceeds GitHub's file size limit of 100.00 MB
  remote: error: GH001: Large files detected. You may want to try Git Large File Storage - https://git-lfs.github.com.
  To https://github.com/biosustain/recipe-book.git
  ! [remote rejected] test-lfs -> test-lfs (pre-receive hook declined)
  error: failed to push some refs to 'https://github.com/biosustain/recipe-book.git'
  ```

  As of now git has a built-in support for hinting you at which files are to large to be
  uploaded to GitHub.
  </details>

- `rebase` to remove the files again, see
  [this tutorial](https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase).
  Options:
  - edit the commit where you added the large files and remove them
  - commit a new delete commit and squash it into the one where you added the files

> Please not that files synchronized once to GitHub stay there 'forever'. If you update
> your history (your commits) they are lost by being not referenced anywhere, but anyone
> who knows the commit-id and has access can in princple find them again

#### How does it happen in practice?

- data is commited, but not every commit is synced to the remote
- long notebooks with outputs are commited, making it very large text files (espe
  with interactive plots)

> so check for large individual files if you cannot push your changes
