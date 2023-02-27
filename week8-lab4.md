Recreating Steps in Competition
--------------

Note: created ssh keys for logging into ieng6 and github from ieng6


1. Log into ieng6
![image](https://user-images.githubusercontent.com/120623425/221470307-03b8918c-3fda-4444-a6bb-1db16a93f0d5.png)

Keys pressed: `<up><up>, <enter>`
I recently used the ssh ieng6 command, so I used the up arrows and `ssh cs15lwi23afq@ieng6.ucsd.edu` was 2 up in search history.

2. Clone your fork of the repository from your Github account.
   ![image](https://user-images.githubusercontent.com/120623425/221470378-64f81ab8-116a-421b-8d3e-f666aa9fc2d8.png)
![image](https://user-images.githubusercontent.com/120623425/221470482-4df5433c-e1dc-4da5-9c01-8baddc51e0b9.png)
  
  Keys pressed: `<Ctrl+R>, <type "ss">, <enter>`
    Then `<^R>, <type "c">, <enter>`
      
I ran this lab before so I knew that I logged into my Github account from my ieng6 account with `ssh -T git@github.com`, but I wasn't sure how far I would need to use the up arrow, so I used `<^R>` to be quicker.
    Then I needed to clone the repository from my Github, so I searched for the command `git clone git@github.com:symsoph/lab7` with `<Ctrl+R>`
    
3. Run the tests, demonstrating that they fail.
 ![image](https://user-images.githubusercontent.com/120623425/221471087-368b5d81-4faa-4a9a-9790-80f5cb7221c4.png)


Keys pressed: `<type "cd la">, <tab>, <enter>` Then `<Ctrl+R>, <type "javac">, <enter>` Next `<Ctrl+R>, <type "java ">, <enter>`
  
You must see a pattern by now with `<Ctrl+R>`.  It is very useful for searching through the terminal history. One different key is <tab> which autocompletes directory names, file names, and commands. 
  
4. Edit the code file to fix the failing test 

  ![image](https://user-images.githubusercontent.com/120623425/221475554-e71ceb9c-8362-42ae-ac94-07cb1c015d1b.png)
  
Keys pressed for editting: `<^R>, <"na">, <enter>` 
  
  Inside nano, keys pressed: `<^W>, <merge>, <enter>, 19 <down>, 7 <left>, <delete>, <"2">, <^O>, <enter>, <^X>`
      
To edit the file quickly, I searched for the command `nano`. Once inside the file, I search for "merge" where the tester found an erorr, go towards the area (just reassigning a variable) using those number of down and left arrows, and edit the file. Then I save my changes with `<Ctrl+O>` and I exit `nano` and the file with `<Ctrl+X>`.  Those nano commands can be found at the bottom of the screen.  

5. Run the tests, demonstrating that they now succeed.
![image](https://user-images.githubusercontent.com/120623425/221472479-3c52c267-a294-445b-97fc-1f67c60aa67d.png)
      
Keys pressed for testing: `<Ctrl+R>, <type "javac">, <enter>` Next `<Ctrl+R>, <type "lib">, <enter>`
      
To test the file to see if it succeeds, I could have used the up arrows since I compiled and ran the tester not too long ago, but instead, I used `<^R>` to search because I forgot. You see that I typed "lib" because <^R> and then `<"java ">` did not give me the right command, it showed me a `.java` file, probably because I messed up and used nano again. Thus, a recent use of a line with `java` was returned by `<^R>`.  As a result, I had to search for the java command to run the tester with a different word.
      
6. Commit and push the resulting change to your Github account (you can pick any commit message!)
![image](https://user-images.githubusercontent.com/120623425/221473955-3ac50c50-69eb-4f98-b44b-06086caccd63.png)

      Keys pressed: `<^R>, <"git add">, enter`
      To commit with a message: `<^R>, <"comm">, enter`
      Push changes: `<^R>, <"pus">, <enter>`
 `<^R>` is my best friend! I used it to search for prior git add, commit, and push commands I used before.
