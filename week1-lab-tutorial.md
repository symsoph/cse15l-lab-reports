Remote Access Server Tutorial 
=============================
In this tutorial, we are going to use a terminal (VSCode) to connect to a remote computer via the Internet.  

## Step 1. 
[Install](https://code.visualstudio.com/) `VSCode`, if it is not already on the computer you are using. Make sure you have the right version for Windows/Mac/etc.

**For new VSCode users**

> After installing, the screen you will see is going to be blank with a few example commands like *Ctrl/Command + `*

Not new? Here is what the VSCode startup screen might look like if you already have VSCode installed before this tutorial. 
![after install vscode](https://user-images.githubusercontent.com/120623425/212242718-5a5d146b-f744-4a64-9189-af575040fe81.png)




## Step 2.
Now we need to install `git`. Follow the links provided below.

> Install `git` for [Windows](https://github.com/git-guides/install-git#install-git-on-windows)
>
> Install `git` for [Mac](https://github.com/git-guides/install-git#install-git-on-mac)

Done? Great! Follow [this post](https://stackoverflow.com/a/50527994) for what to do next.  

## Step 3. 
With the `Git Bash` terminal in VSCode, type `ssh` and copy your course-specified account address and add @ieng6.ucsd.edu.

Your command should look similar to this: `$ ssh cs15lwi23zz@ieng6.ucsd.edu`. **On your end notice**: in place of `zz` the last letters are different.  

> *DO NOT copy and paste the above command.*

Now press `enter`. 

Surprise✨This message might have showed up because you have not logged into this server before, but do not fret!

```
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
```
Just type `yes`, press `Enter`, and paste your account password.  
![login in success](https://user-images.githubusercontent.com/120623425/212242385-fcbb5a6d-c2f4-4eaf-badd-d71536346feb.png)

Success! Now your computer (the client) is connected to the server. 

## Step 4. 
Run some commands

- `cd`
- `cd ~`
- `ls`
- `ls -lat`
- `ls -a`
- `pwd`

Example of outputs.![running commands](https://user-images.githubusercontent.com/120623425/212244719-59d8f50c-a7a7-47c9-b8cf-8cbc5cc9e962.png)

To log out of the remote server use: `Crtl/Command + D` **or** type `exit`.

