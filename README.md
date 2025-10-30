# Git Tutorial

Sign-Up to the workshop here (being logged in with your DTU Microsoft account): [Sign-Up Form](https://forms.office.com/e/62H1nV61R0)

## Announcement

This workshop will give you the opportunity to practice git as a version control system
and Github as a website to host your repositories. Using git you can track changes in
folders. It allows you track your progress and to spot random typos when working on
many projects and tasks in parallel. In the workshop you will get the time to practice
the fundamental concepts and actions directly in your browser - either using VSCode in
GitHub Codespaces or in using the GitHub web interface. If you want, you can also try
everything on your local computer.

I will give a brief introduction to git. Then you will specific workflows by
collaboratively work on extending a [recipe book](https://enryh.github.io/recipe-book/)
(please bring a recipe you like).
You will learn how to work on
[branches](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches),
review [Pull Requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)
and merge them into the main branch. If you have specific requests, feel free to reach out to me.

If you have specific requests, feel free to reach out to [me](mailto:heweb@dtu.dk) and/or write it down in the sign-up form.

What you'll learn:

- Basic tasks and actions to perform with git (in VSCode or in the browser)
- How to branch and tag
- Follow trunk-based development
- See how to merge and comment a Pull Request based on a branch
- Solve merge conflicts
- Familiarize yourself with VSCode’s and GitHub’s interface and user experience
- Get to know new recipes

Minimal prerequisite: A [GitHub account](https://github.com/signup).
If you want to follow along locally, please install
[GitHub Desktop](https://desktop.github.com/download/) and
[VSCode](https://code.visualstudio.com/) on your machine.

### Brief timeline of the workshop:

| Time          | Activity                                   |
| ------------- | ------------------------------------------ |
| 10:00 - 10:15 | Coffee and snacks 🥐                       |
| 10:15 - 10:45 | Introduction and example workflow          |
| 10:45 - 12:00 | Working collaboratively on the recipe book |
| 12:00 - 12:30 | lunch break (not included)                 |
| 12:30 - 13:30 | Your question and advanced content         |

## Slides

<iframe 
src="https://docs.google.com/presentation/d/1RsKMiKquE4wqncrAv9LEtjivGE_dGiHoJ8nKCxgVKeY/embed?slide=id.p#slide=id.p" 
frameborder="0"
width="100%" height="480" 
allowfullscreen="true"
 mozallowfullscreen="true" 
webkitallowfullscreen="true">
</iframe>

## Local Setup

See [local_setup](local_setup.md) for instructions to setup git on your local computer.

## Links to learn more

- [git-intro by coderefinery](https://coderefinery.github.io/git-intro/#)
- [git-moji](https://gitmoji.dev/)
- [Git Internals - Plumbing and Porcelain](https://git-scm.com/book/en/v2/Git-Internals-Plumbing-and-Porcelain)
- [Glossary of terms (technical for git)](https://www.git-scm.com/docs/gitglossary)
- [GitHub Glossary terms](https://docs.github.com/en/get-started/learning-about-github/github-glossary)

## Git under the hood (Extended version)

> Extended content for those interested in how git works under the hood

You can find a recording of the
[talk](https://www.youtube.com/watch?v=cAU3BCUkHxM)
([slides](https://docs.google.com/presentation/d/1RsKMiKquE4wqncrAv9LEtjivGE_dGiHoJ8nKCxgVKeY/edit?usp=sharing))
and [hands-on tutorial](https://www.youtube.com/watch?v=5iB7qc5zRjQ)
on YouTube which was done for the Data Club seminar
between DTU biosustain and DTU bioengineering (see sections in description of Video).

Talk:
[![Recording of talk](https://img.youtube.com/vi/cAU3BCUkHxM/maxresdefault.jpg)](https://www.youtube.com/watch?v=cAU3BCUkHxM)

Live Demo:
[![Live Demo of Hands On part](https://img.youtube.com/vi/5iB7qc5zRjQ/maxresdefault.jpg)](https://www.youtube.com/watch?v=5iB7qc5zRjQ)

The above Live Demo is not pulling the merge commit after merging the branch on GitHub:
[github.com/biosustain/git_training_henry_recording](https://github.com/biosustain/git_training_henry_recording)

I show the merge commit in the video below, cloining the recording repository in a newly
create VSCode sandbox environment above:

[![Live Demo Hand on Addon](https://img.youtube.com/vi/gcfzruIJ-rw/sddefault.jpg)](https://www.youtube.com/watch?v=gcfzruIJ-rw)

### Instructions

- create a folder with an empty repository (default `examples`
  directly openend in VSCode on binder)
- open instruction: `code-server ../README.md` (local computer: `code ../README.md`)
- `git init` in console to initialize repo (or via command palette "Git: Initialize Repository")
- setup user.name and user.email (see above)
- create files, stage them and see what files are created in `.git/objects`
- commit files and check `.git/objects`
- create branches and checkout `.git/refs` (`git/branches` is a legacy folder,see
  [here](https://stackoverflow.com/a/10398507/9684872))
- look at `git/HEAD` (maybe `git/ORIG_HEAD` if it exists)

> try to create your own fork, and try to lauch it on [mybinder](https://mybinder.org/)

### Inspect git objects

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

### What's happening?

Can you explain what happens in the following scenarios?

- You committed ten commits and did not yet push. Git complains about too much data.
  You realize that you committed your source data. You delete it and commit again,
  but the problem still persists.
- You commit something and push. You realize your last commit was wrong. You undo it
  and commit again. Git complains that you cannot push.

### Git internals resources

- [curious git](https://matthew-brett.github.io/curious-git/) - detailed intro to the
  inner workings
- [git parable](http://practical-neuroimaging.github.io/git_parable.html) - why git came to exist
- Videos:
  - [Python-Git-Client](https://www.youtube.com/watch?v=xvzo_nV9PjU)
  - [Git-Interals](https://www.youtube.com/watch?v=MYP56QJpDr4) - shows how git works
  - [Git PyData Global 2021 talk](https://www.youtube.com/watch?v=rBYC3dEOOyI)
  - Scoot Chacon’s [“So you thin you know git” talk](https://www.youtube.com/watch?v=aolI_Rz0ZqY) (FOSDEM 2024),
    notes on [blog](https://blog.gitbutler.com/git-tips-1-theres-a-git-config-for-that/)
