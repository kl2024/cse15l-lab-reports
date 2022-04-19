# [Lab Report 1](https://kl2024.github.io/cse15l-lab-reports/lab-report-1-week-2.html)
---
**Instructions: 
You will write a tutorial for incoming 15L students (and your future self!) about how to log into a course-specific account on `ieng6`. Your post should include the steps you took, along with screenshots of what each step looked like. You’re free to use the screenshots you took for lab 1, or new ones. Complete any steps you didn’t complete in your group on your own.**

## Step 1: Installing VScode
Download VScode by going to the [Visual Studio Code website](https://code.visualstudio.com/) and following the instructions either for OS (for Macs) or Windows(for PCs) to download and install it on your computer.

Once you have installed VScode, you should be able to click and open a new VScode window that looks like this:

![Image](https://user-images.githubusercontent.com/103288212/162543554-4f7cb23d-15a8-428d-95dd-bf9abcea94dd.png)

## Step 2: Remotely Connecting

Install the [OpenSSH program](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse), which can connect your computer to other computers that have this kind of account.

You can look up your course-specific account through [this link](https://sdacs.ucsd.edu/~icc/index.php).

After finding your course-specific account, open a terminal in VSCode and type in this command with your own account information:

`$ ssh cs15lsp22zz@ieng6.ucsd.edu`

Once you type in this command, you should get an output that looks like this: 

![Image](https://user-images.githubusercontent.com/103288212/163937584-1d2f404f-ba46-4a65-b056-f9e27e042f52.png)


## Step 3: Trying Some Commands

After ssh-ing, you should be able to run the commands `cd`, `ls`, `pwd`, `mkdir`, and `cp` a few times in different ways, both on your computer, and on the remote computer. Try it out! You should get a result that looks somewhat like this:

![Image](https://user-images.githubusercontent.com/103288212/163479599-52d91012-21e0-4ba7-b341-430be412375f.png)

To log out of the remote server in your terminal, you can use:
- Ctrl-D
- Run the command `exit`

## Step 4: Moving Files with `scp`

To copy a file (or many files!) from your computer to a remote computer, you will use the command called `scp`. Once you've created a java file on your *own* computer (the client), run this command (using your own file and username):

`scp filename.java cs15lsp22zz@ieng6.ucsd.edu:~/`

You should get a result that looks like this:

![Image](https://user-images.githubusercontent.com/103288212/163479785-7475aa60-9d02-4783-88a1-dc312ea53db7.png)


## Step 5: Setting an SSH Key

To prevent having to enter your password every time you pass the command `scp`, we can use `ssh` keys. Here’s what you should run on your computer terminal to set this up:

`$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/<user-name>/.ssh/id_rsa): /Users/<user-name>/.ssh/id_rsa
Enter passphrase (empty for no passphrase): `

**Note: Make sure that you do not add a passphrase for this step.**

`Enter same passphrase again: `
`Your identification has been saved in /Users/<user-name>/.ssh/id_rsa.`
`Your public key has been saved in /Users/<user-name>/.ssh/id_rsa.pub.`
`The key fingerprint is:`
`SHA256:jZaZH6fI8E2I1D35hnvGeBePQ4ELOf2Ge+G0XknoXp0 <user-name>@<system>.local`
`The key's randomart image is:`
`+---[RSA 3072]----+`
`|                 |`
`|       . . + .   |`
`|      . . B o .  |`
`|     . . B * +.. |`
`|      o S = *.B. |`
`|       = = O.*.*+|`
`|        + * *.BE+|`
`|           +.+.o |`
`|             ..  |`
`+----[SHA256]-----+`

![Image](https://user-images.githubusercontent.com/103288212/163480035-2a36be7c-0df1-405a-8bd7-cbc60046e792.png)

Now we need to copy the public (not the private) key to the `.ssh` directory of your server account.

`$ ssh cs15lsp22zz@ieng6.ucsd.edu`
`<Enter Password>`
`# now on server`
`$ mkdir .ssh`
`$ <logout>`
`# back on client`
`$ scp /Users/<user-name>/.ssh/id_rsa.pub cs15lsp22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys`
`# You use your username and the path you saw in the command above`

Congratulations! You should now be able to `ssh` or `scp` from this client to the server without entering your password.

## Step 6: Optimizing Remote Running

Guess what? You can make an even more pleasant process for making a local edit, copying it to a remote server, and then running it by reducing the process to one command. You can write a command in quotes at the end of an `ssh` command to directly run it on the remote server, then exit. Using semicolons can also run multiple commands on the same line in most terminals.

Try running:

`scp filename.java cs15lsp22xxx@ieng6.ucsd.edu:~/; ssh cs15lsp22xxx@ieng6.ucsd.edu; "javac filename.java"; "java filename"`

![Image](https://user-images.githubusercontent.com/103288212/163940919-eeb24391-6a5e-4217-ad63-e3662c464091.png)

