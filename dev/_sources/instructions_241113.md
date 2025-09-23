# Workshop on the 13th of November 2024

.. at DTU biosustain and DTU bioengineering.

## Plan

- Introduction to git ([slides](https://docs.google.com/presentation/d/1RsKMiKquE4wqncrAv9LEtjivGE_dGiHoJ8nKCxgVKeY/edit?usp=sharing)),
  see recording [here](https://youtu.be/cAU3BCUkHxM)
- Hands-on, focusing this time on
    - working on a shared repository (per group, i.e. e.g. per table)
    - creating and merging branches
    - viewing and annotating collaborative work
    - showing features of GitHub

If time allows - and maybe due to common errors - we will also cover:
- merge conflicts
- out-of-sync issues

The workshop will require you to have a GitHub account. Please open it here: [github.com/join](https://github.com/join) 

### 1. step - create a shared repository

> ONLY one person per group has to do this.

Per group (e.g. table) create one repository on GitHub on one of the group members account
or under the DTU biosustain organization.
 - Use as template this repository from  
   [github.com/enryH/notes_template](https://github.com/enryH/notes_template). 
   Follow the instructions described 
   [here](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template#creating-a-repository-from-a-template) or 
   [the demo-recording](https://youtu.be/XolIezJtSPI?t=98) to use it.

### 2. step - create a clone of the shared repository

Now you have a common repository you can share with each others. You can either 
[work in a codespace](https://docs.github.com/en/codespaces/developing-in-a-codespace/creating-a-codespace-for-a-repository#creating-a-codespace-for-a-repository)
(opening the repository in a virtual machine in the browser) or clone the repository
to your local machine.

- we won't cover the website aspect of the template here, but I created a video on how 
  to use the template for a website [here](https://www.youtube.com/watch?v=XolIezJtSPI) 
  (which is also linked in the [repository's README](https://github.com/enryH/notes_template)).

### 3. step - each create a branch

Each of you create a branch, e.g. give it your name. Add a brief description of what you 
are passionate about in a file called `aboutme.md` in a folder with your name.

In order to commit this to the GitHub repository you have to do one of the two options:

- [add all collaborators](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-access-to-your-personal-repositories/inviting-collaborators-to-a-personal-repository#inviting-a-collaborator-to-a-personal-repository)
  of your group to the repository (write access)
- create a fork on your GitHub account (you will be asked in VSCode if you want to do this)

You can also mix both approaches in your group to find out about the differences.

> You can see how to commit changed files [here](https://www.youtube.com/watch?v=XolIezJtSPI&t=938s)
> (in one part of the notes template hands on recording)

### 4. step - merge the branches to the main branch

On GitHub open a pull request to merge your branch to the main branch. We will explore 
together some features of the pull request website.

> Hint: Use the extension
> [Git Graph](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph)
> to visualize your branches and the history of your repository.

### 5. step - view and annotate the collaborative work

Switch back to the `main` branch and get all the latest changes from your coworkers (pull). 
Now, each create (again) a new branch (pick a unique new name) and create a the file name `biosustain.md`. 
In this file write a about what you think biosustain is about.

### 6. step - merge the branches to the main branch

The first pull request will work fine. Everyone else has to deal with merge conflicts, as 
the same named file will be overwritten - and there is no clear way to say which version 
is the correct one or how to combine you changes.

- Hint: In your CodeSpace make sure to checkout the latest changes from the main branch 
  before creating a new branch (pull on main).

### 7. step - merge conflicts

> Advanced!

We will explore how to resolve merge conflicts in VSCode's UI. This is advanced and 
you don't have to do this for now.

## Follow up recording

[![Live Demo of Hands On part](https://img.youtube.com/vi/mX3Il5xvKAs/maxresdefault.jpg
)](https://www.youtube.com/watch?v=mX3Il5xvKAs)

