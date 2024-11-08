# Workshop on the 13th of November 2024

.. at DTU biosustain and DTU bioengineering.

## Plan

- Introduction to git (slides), see recording here
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
   [here](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template#creating-a-repository-from-a-template) to use it.

### 2. step - create a clone of the shared repository

Now you have a common repository you can share with each others. You can either 
[work in a codespace](https://docs.github.com/en/codespaces/developing-in-a-codespace/creating-a-codespace-for-a-repository#creating-a-codespace-for-a-repository)
(opening the repository in a virtual machine in the browser) or clone the repository
to your local machine.

- we won't cover the website aspect of the template here, but I created a video on how 
  to use the template for a website here (which is also linked in the repository's README).

### 3. step - each create a branch

Each of you create a branch, e.g. give it your name. Add a brief description of what you 
are passionate about in a file called `aboutme.md` in a folder with your name.

### 4. step - merge the branches to the main branch

On GitHub open a pull request to merge your branch to the main branch. We will explore 
together some features of the pull request website.

> Hint: Use the extension
> [Git Graph](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph)
> to visualize your branches and the history of your repository.

### 5. step - view and annotate the collaborative work

Switch back to the `main` branch and get all the latest changes from your coworkers. No each
create a new branch (pick a unique new name) and create a the file name `biosustain.md`. 
In this file write a about what you think biosustain is about.

### 6. step - merge the branches to the main branch

The first pull request will work fine. Everyone else has to deal with merge conflicts, as 
the same named file will be overwritten - and there is no clear way to say which version 
is the correct one or how to combine you changes.

### 7. step - merge conflicts

> Advanced!

We will explore how to resolve merge conflicts in VSCode's UI. This is advanced and 
you don't have to do this for now.