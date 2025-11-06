# Setup git locally

## Download git

Download and install git from [git-scm.com](https://git-scm.com/install) 
for your operating system.

## Configure git

You will need to setup your git email and user-name
(replace with yours in case you want to commit something, otherwise use copy-paste)
to identify yourself in the commits:

```bash
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
``` 
> could be added to local config using `git config user...`

Then you need to define how to handle merge conflicts, in case you have committed 
changes locally and there are changes in the remote repository. The easiest way is to
always create a merge commit 
([docs](https://git-scm.com/docs/git-config#Documentation/git-config.txt-pullrebase)):

```bash
git config --global pull.rebase false
# or only for this repository
git config --local pull.rebase false
```

Setting it to true has a the warning: 
> NOTE: (setting it to true) is a possibly dangerous operation; do not use it unless you understand 
> the implications. (see [git-rebase](https://git-scm.com/docs/git-rebase) for details)
