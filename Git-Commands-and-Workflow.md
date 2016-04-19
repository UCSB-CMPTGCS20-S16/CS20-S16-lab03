
# The basic workflow

The normal workflow when using git is as follows.  

The following instructions assumes you've already completed the steps describe on the "One time set up for CSIL" page (whether on your CSIL account, or on your own computer.)

# One time setup per project:

Short version: 

```
cd ~/github
git clone ssh-clone-url-of-your-repo
cd repo-name
```

Longer version:
* Find the repository web page on github.com
* Find the SSH clone URL on the right hand side, about half way down.
* If the link says HTTPS clone URL instead of SSH clone URL, click the blue SSH link.
* Copy the link.
* cd into your ~/github directory on your ACMS account (or wherever you want the repo to be stored).
* Do the command `git clone paste-your-ssh-clone-url-here`
* Do an `ls` command, and you should now have a directory with the same name as your repositority.  
* `cd` into that directory to do your work.

# Each time you make a change

It is recommended, but not required, to do a `git status` first, and after each command below:

```
git status
```

Then:

```
git add  names-of-files-you-changed
git commit -m "AB/CD describe your changes"
```

(When pairing, AB is the initials of the driver, CD are the initials of the navigator)

```
git push origin master
```

Troubleshooting:

* If push is rejected because the remote has work you do not have locally, do a `git pull origin master` first.
* If you are thrown into vim, use escape `:wq` then press Enter/Return  to save the automatic commit message.)

