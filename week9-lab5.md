🔎Exploring the `find` Command🔍
----------------------------

In this lab report, I will be listing **4** ways to use `find` and give examples using the `./written_2/` directory and its files.
Information for this report from [this guide](https://kb.iu.edu/d/admm#:~:text=Use%20the%20Unix%20find%20command%20to%20search%20for,a%20filename%20or%20matching%20expression%2C%20such%20as%20%22%2A.txt%22.), [GNU](https://www.gnu.org/software/findutils/manual/html_mono/find.html), [plesk](https://www.plesk.com/blog/various/find-files-in-linux-via-command-line/), [Redhat](https://www.redhat.com/sysadmin/linux-find-command) and `find --help`. 


> 📌1. Searching for a File

**Example 1**

📩Command:
```
$ find . -name Bahamas-History.txt
```

⬅️Output:
```
./travel_guides/berlitz2/Bahamas-History.txt
```
For this option `-name`, I needed to know the exact file name because `-name` is case-sensitive. However, since I did not remember which sub-directory the file is in, I use `.` for this and the `.` tells `find` to look through the current directory `written_2/` and sub-directories for the Bahamas-History.txt file.  

**Example 2:**

📩Command
```
find . -iname "*Bahamas*txt"
```
⬅️Output:
```
./travel_guides/berlitz2/Bahamas-History.txt
./travel_guides/berlitz2/Bahamas-Intro.txt
./travel_guides/berlitz2/Bahamas-WhatToDo.txt
./travel_guides/berlitz2/Bahamas-WhereToGo.txt
```
Here `find` looks at a directory called `non-fiction` within the `written_2` (the current working directory) and returns matches of `.txt` files with Bahamas in the name. `-iname` means not case-sensitive so if there was a file with lowercase "Bahamas", it would also be returned.

This could be useful for someone who doesn't exactly know a file name.


> 📌2. Explore directories

**Example 1**

📩Command
```
find non-fiction/
```
⬅️Output:
```
non-fiction/
non-fiction/OUP
non-fiction/OUP/Abernathy
non-fiction/OUP/Abernathy/ch1.txt
non-fiction/OUP/Abernathy/ch14.txt
    ....(more files)....
```
Here `find` looks at a directory called `non-fiction` within the `written_2` (the current working directory) and returns everything in that sub-directory.

This could be useful for someone who wants to view what files and other sub-directories are in a directory.


**Example 2**

📩Command
```
find travel_guides -name "*History*txt"
```
⬅️Output
```
travel_guides/berlitz1/HistoryDublin.txt
travel_guides/berlitz1/HistoryEdinburgh.txt
travel_guides/berlitz1/HistoryEgypt.txt
travel_guides/berlitz1/HistoryFWI.txt
travel_guides/berlitz1/HistoryFrance.txt
travel_guides/berlitz1/HistoryGreek.txt
travel_guides/berlitz1/HistoryHawaii.txt
(etc)
```
Here `find` is looking through the `travel_guides` directory for files that contain the pattern "History" and "txt" in the name. This is useful for someone who wants to specifically look at a directory, trying to look for a file they vaguely know exists. 

> 📌3. What's your type?

**Example 1**

📩Command
```
find -type d
```
⬅️Output
```
.
./non-fiction
./non-fiction/OUP
./non-fiction/OUP/Abernathy
./non-fiction/OUP/Berk
./non-fiction/OUP/Castro
./non-fiction/OUP/Fletcher
./non-fiction/OUP/Kauffman
./non-fiction/OUP/Rybczynski
./travel_guides
./travel_guides/berlitz1
./travel_guides/berlitz2
```
This `find` option returns a list of directories specified by `-type d`. In this case, starting within the `written_2` directory, all sub-directories are returned.

This is useful if someone wants to know what kinds of directories and sub-directories exist, and only directories.

**Example 2**

📩Command
```
find -type f
```
⬅️Output
```
./non-fiction/OUP/Abernathy/ch1.txt
./non-fiction/OUP/Abernathy/ch14.txt
./non-fiction/OUP/Abernathy/ch15.txt
./non-fiction/OUP/Abernathy/ch2.txt
./non-fiction/OUP/Abernathy/ch3.txt
./non-fiction/OUP/Abernathy/ch6.txt
./non-fiction/OUP/Abernathy/ch7.txt
./non-fiction/OUP/Abernathy/ch8.txt
(etc)
```
This `find` option returns all the files in the `written_2` and sub-directories because I gave the option `-type f`. This is useful for when one desires a list of all files and only files.

> 📌4. Stalker much?


**Example 1**

📩Command
```
find . -newermt "Jan 1"
```

⬅️Output
```
.
./non-fiction
./non-fiction/OUP
./non-fiction/OUP/Abernathy
./non-fiction/OUP/Abernathy/ch1.txt
./non-fiction/OUP/Abernathy/ch14.txt
./non-fiction/OUP/Abernathy/ch15.txt
./non-fiction/OUP/Abernathy/ch2.txt
./non-fiction/OUP/Abernathy/ch3.txt
./non-fiction/OUP/Abernathy/ch6.txt
(etc)
```
`-newermt` is a way to list files in the `written_2` directory that were modified after January 1st of the current year (2023).  So if you want to know if files were changed recently without asking the creator directly, this is the way.


**Example 2**

📩Command
```
find ./travel_guides/berlitz2/Bahamas-History.txt -atime +7
```
⬅️Output
```
./travel_guides/berlitz2/Bahamas-History.txt
```
`-atime +7` means that file(s) that were accessed more than 7 days ago would be returned. Since the argument before `-atime` is a path to Bahamas-History.txt, it goes to show that Bahamas-History.txt was definitely accessed more than 7 days ago. 

If you would like to see what you have accessed before, this is a good combination of options to input. 
