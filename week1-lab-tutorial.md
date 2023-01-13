Remote Access Server Tutorial 
=============================
In this tutorial, we are going to use a terminal (VSCode) to connect to a remote computer via the Internet.  

Step 1. Install `VSCode`, if it is not already on the computer you are using.  
[Install VSCode (make sure you have the right version for Windows/Mac/etc](https://code.visualstudio.com/)

**For new VSCode users**

> After installing, the screen you will see is going to be blank with a few example commands like *Ctrl/Command + `*


Here is what the VSCode startup screen might look like if you already have VSCode installed before this tutorial. 
![Image](https://github.com/symsoph/cse15l-lab-reports/blob/main/after%20install%20vscode.png)

Step 2. Now we need to install `git`. Follow the links provided below.

[Install `git` for Windows](https://github.com/git-guides/install-git#install-git-on-windows)
[Install `git` for Mac](https://github.com/git-guides/install-git#install-git-on-mac)

Done? Great! Follow [this post](https://stackoverflow.com/a/50527994) for what to do next.  

With the `Git Bash` terminal in VSCode, type `ssh` and copy your course-specified account address and add @ieng6.ucsd.edu.
Your command in the terminal may look like this: '$ ssh cs15lwi23zz@ieng6.ucsd.edu'. \Now press `enter`.

Surprise✨This message might have showed up because you have not logged into this server before, but do not fret!

```
# $ ssh cs15lwi23zz@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
```
Just type `yes`, press `Enter`, and paste your account password.  
![login in success](https://user-images.githubusercontent.com/120623425/212242385-fcbb5a6d-c2f4-4eaf-badd-d71536346feb.png)

Success! Now your computer (the client) is connected to the server. 

