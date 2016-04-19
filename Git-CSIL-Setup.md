There are four "one time setup" items that we recommend that you do under your CSIL account to make it easier to work with git/github. 
These are:

1. Creating a ~/github directory
1. Setting up the git default name and email for your ACMS account
1. Creating an ssh public/private key pair
1. Uploading your ssh public key to github.com


# 1.  Creating a ~/github directory

You can "clone a github repo" in any directory (folder) in your CSIL account.  But you may find it helpful and less 
confusing to create a `~/github` directory, and always clone your github repos in that directory.  
This helps you remember which directories are github repos, and which ones are not.

(Recall that `~` signifies your "home directory" on a Linux file system).

To create a `~/github` directory, simply type this at the shell prompt:

 mkdir -p ~/github

(The `-p` is optional.  It will ensure that you do not get an error message if the directory already exists.  
The `-p` can also be used with the mkdir command if you are creating an entire 
directory path all at once.  We aren't doing that here, but it is handy to 
just get in the habit of always using `-p` with `mkdir`.)

# 2. Setting up the git default name and email for your CSIL account

In a terminal window, while logged into your CSIL account, type in these two commands at the Unix shell prompt, 
substituting your name and email in place of Phill's:

```
git config --global user.name "Phill Conrad"
git config --global user.email "pconrad@cs.ucsb.edu"
```

# 3. Creating an ssh public/private key pair

In this step, we will set up a public/private key pair on your CSIL account. 

The idea of a public/private key pair is that you give away your public key, and you keep your private key a secret. 
This allows anyone with your public key to know that you are you without you having to type in a password 
(as long as your private key stays secret).

To generate a public/private key pair: Open a terminal session, and type the `ssh-keygen` command.

You will be asked a series of questions. For each question, just press the enter/return key (to accept the default option.)

That will look like this:
```
bash-4.3 $ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/cs/student/jgaucho/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /cs/student/jgaucho/.ssh/id_rsa.
Your public key has been saved in /cs/student/jgaucho/.ssh/id_rsa.pub.
The key fingerprint is:
de:8f:c0:d8:69:bc:82:e9:06:e9:30:25:42:16:bc:1c spis15t7@ieng6-240
The key's randomart image is:
+--[ RSA 2048]----+
|...              |
| E               |
|+ o              |
|oo.              |
|.o .    S        |
|o o    * o       |
| + . o. O .      |
|  . + .. o o     |
|   o.  .. . .    |
+-----------------+
bash-4.3 $
```


The effect of that is to create two files in a hidden directory of your account called `.ssh` 

If you type `cd` to go to your home directory, and `ls` at your terminal prompt, you will not see this directory. Example:

But if you use `ls -a` you WILL see the `.ssh` directory along with many other hidden directories.

Next, type the command `cd ~/.ssh` at the Terminal prompt.   Then use `ls` to list your files.

You should see two files `id_rsa` and `id_rsa.pub` as follows. (If you see other files, don't worry)

```
bash-4.3 $ cd ~/.ssh
bash-4.3 $ ls
id_rsa  id_rsa.pub
bash-4.3 $  
```

You want to now look at the contents of `id_rsa.pub`.  This file is your public key. 
That is the one you are going to share with `github.com`. (The contents of `id_rsa` are your private key, which you do NOT share. )

To see the contents of `id_rsa.pub`, we use the cat command:

```
bash-4.3 $ cat id_rsa.pub
ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEA1yTFW/PkiZCebbR9EqkduGCApKwW7uy7CZ1ThomgG+xZs
VgWWIMirzkNJbahxwwEVIH0Hj+irID3ICkH8o60T3QiMk1v5VJSVFaKdqtiZXFQapYR2Rwln1wf2XXBCT/cdVW
if9usiS5vLqtno74/dpKCEiELjGSHdpFTyFoF3ZHR6plFYA2/iX4XWDrDJwG/Qwf+SBd0uzIy7CpFrQK+9kMWDr
K2jUGhd0goYPQu2LCgHxnu8R041M5ooSUE79seE+64gVcjoSfPJwdKhZdwy2zjYvKKz0CM4w3ysPbOpr1FkT
6MnlhN3dyJBFA+BjmtXGVDNl7a5yjtY9QzORILfQ== jgaucho@csil.cs.ucsb.edu
bash-4.3 $ 
```


Your public key will look different, but similar. You are now going to to do a "copy/paste" of that key into a page of github.com. 
Our next step is to navigate to the correct page of github.com to enter that key.


# 4. Uploading your ssh public key to github.com

To upload your ssh public key to github.com, start by opening a web browser to github.com.  If you are not yet logged in, login to your github.com account.   
Go to the github.com settings menu.  It's on a pull down menu at the upper right hand corner of the page.

Once you are at the settings menu, choose  the SSH keys option. It's in the middle on the left.  


Selecting User Settings in github.com	Choosing SSH Keys from User Settings
github.com settings menu	Choose the ssh keys menu option Then, click "Add SSH key" as shown here:

Click Add SSH key


Next, copy your SSH public key as shown here, so that we can paste it into the github.com web browser window. Be careful to get the whole key, but nothing more than the key. Don't include the shell prompts or the cat command.

Copy your ssh public key

paste in your ssh public key

Github may ask for your password as shown here:
asks for password

Then you should get a message that your key was added:
github confirms that key was added
Congratulations! You've now added the public key associated with your SPIS ACMS account to github.com.

In the future, if you have a different ACMS account, you'll need to do this step again.

Optional: You may also want to repeat this step for the public key associated with your own personal laptop or desktop computer.
You'll have to generate a separate public/private ssh key pair for each computer that you use with github.com
On Mac and Linux, the ssh-keygen command should work.
The ssh-keygen command is also available in the "git shell" that comes with the Windows version of git.
