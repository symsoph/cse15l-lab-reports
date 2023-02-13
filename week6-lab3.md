Exploring the `grep` Command
----------------------------

In this lab report, I will listing **4** ways to use `grep` and give examples using the `./written_2/` directory and its files.
Information from [Docs Oracle](https://docs.oracle.com/cd/E19253-01/806-7612/filesearch-96061/index.html) and `grep --help`.


> 📌1. Searching in a File


Format for this grep option: $ grep string <<file>>

**Example 1**

📩Command:
```
$ grep the written_2/non-fiction/OUP/Castro/chA.txt
```
This command is searching for string "the" through the .txt file called chA.  Because I did not include a space afterwards like this "the ", any pattern in the file with "the" will be highlighted.

⬅️Output:
```
El Abuelo (Grandfather)
An old-man figure called el abuelo (the grandfather) played the role of a bogeyman in Hispano folklore. 
In literature it is sometimes spelled aguelo, and some scholars speculate that it may be a borrowed word from the 
language of the Pueblo Indians. In Spanish it means “grandfather,”....
```
The actual output is very long, and pretend grandfather looks like grandfa`the`er.  See the `grep` command printed out all of the chA.txt file and highlighted all instances of "the".

This `grep` option would be useful to quickly skim a specific file for a certain word.

**Example 2:**

📩Command
```
grep Castro written_2/non-fiction/OUP/Castro/chBZ.txt
```
⬅️Output:
```
grep: written_2/non-fiction/OUP/Castro/chBZ.txt: No such file or directory
```
Here `grep` in addition to searching for "Castro", also looks for the file chBZ.txt in the respective directories.  So because chBZ.txt could not be found. We got the above output.

This could be useful for someone to realize that their file name/directory is wrong because `grep` gives the entire path along with "No such file or directory" in its error message.


> 📌2. Filtering with a Pipe

**Example 1**

📩Command
```
grep "the" written_2/non-fiction/OUP/Castro/chA.txt | grep Journal
```
For this command, grep goes from left to right.  The part before the pipe `|` would be the same long result in [Searching in a File Example 1], but then after the pipe `|` grep looks for "Journal" capitalization and all.  

⬅️Output
```
In the late 1960s Chicanos starting calling the southwestern United States, or that portion of Mexico lost to 
the United States during the U.S.-Mexican War of 1846–1848, Aztlán, in reference to the legend of the wandering 
Mexica. The concept of a homeland for Chicanos called Aztlán was presented at the First National Chicano Youth 
Liberation Conference held in Denver, Colorado, in 1969. It was articulated in the manifesto, El Plan Espiritual 
de Aztlán, a document that outlined an ideology meant to unite all Chicanos of the Southwest. The document is 
accredited to Alurista, a poet who was already presenting Aztlán in a Chicano studies class he taught in 1968 at 
San Diego State University. The manifesto stressed the concept of ethnic nationalism and self-determination, and 
of the need for Chicanos to control their own communities, schools, and political structures. The document proclaims,
“We are a Bronze People with a Bronze Culture. Before the world, before all of North America, before all our brothers 
in the bronze continent, we are a nation, we are a union of free pueblos, we are Aztlán. Por La Raza todo, Fuera de 
La Raza nada.” El Plan Espiritual de Aztlán was published in the journal El Grito del Norte, Volume 2, 1969. In 1970, 
a journal was started at the University of California, Los Angeles, titled Aztlán: Chicano Journal of the Social 
Sciences and the Arts, which is still published today.
```
Which leads us to this much shorter output where "Journal" would be highlighted at the bottom, found in the line `titled Aztlán: Chicano Journal of the Social...`

This is useful for adding on other words to search instead of pressing the arrow key to insert another word.


**Example 2**

📩Command
```
grep "El Abuelo" written_2/non-fiction/OUP/Castro/chA.txt | grep "(Grandfather)"   
```
⬅️Output
```
El Abuelo (Grandfather)
```
Here `grep` is looking first for the pattern of strings "El Abuelo" then filters in order to look for "Grandfather". Tip: use `""` when searching to more than one word.

This `grep` option is useful for filtering results so that only necessary information stands out.

> 📌3. Searching for Words Without a Certain File

**Example 1**

📩Command
```
grep "hungry h" written_2/travel_guides/*/*
```
⬅️Output
```
written_2/travel_guides/berlitz1/WhereToHongKong.txt:        “hungry tigers”) and, for hungry humans, a restaurant. Gambling is
```
This `grep` option searches for "hungry h" in multiple files found in the sub-sub directory of `written_2/travel_guides` which are signified by `*`.
This would be useful if one did not know the extra directory or file to search.

**Example 2**

📩Command
```
grep "hungry" written_2/*/*/*/*
```
⬅️Output
```
written_2/non-fiction/OUP/Castro/chB.txt:You keep me away from INSANITY’S hungry jaws;
```
This `grep` option searches the many sub-directories of `written_2/` to find "hungry" and then returns the extra path and line which contains the word.
This is useful if one only knew the desired term to be searched and the main directory to search through, also saving time using `*` instead of using `ls` for every sub-directory you run into.

> 📌4. Using Dashes and Letters

For this last round of examples, I am in the `written_2` directory and am using help from [GNU](https://www.gnu.org/savannah-checkouts/gnu/grep/manual/grep.html)


**Example 1**

📩Command
```
grep -l "Lucayans" */*/*
```
`-l` while using `grep` means to print out only files that match, so files that contained "Lucayans" would be printed only.

⬅️Output
```
grep: non-fiction/OUP/Abernathy: Is a directory
grep: non-fiction/OUP/Berk: Is a directory
grep: non-fiction/OUP/Castro: Is a directory
grep: non-fiction/OUP/Fletcher: Is a directory
grep: non-fiction/OUP/Kauffman: Is a directory
grep: non-fiction/OUP/Rybczynski: Is a directory
travel_guides/berlitz2/Bahamas-History.txt
```
This option is useful, especially if you are only looking for the file that contains "Lucayans" and don't want anything else.


**Example 2**

📩Command
```
grep -H "Lucayans" */*/*
```
`grep -H` prints out the file names that contain the word in addition to the usual output of lines within the file(s) that contain "Lucayans".

⬅️Output
```
grep: non-fiction/OUP/Abernathy: Is a directory
grep: non-fiction/OUP/Berk: Is a directory
grep: non-fiction/OUP/Castro: Is a directory
grep: non-fiction/OUP/Fletcher: Is a directory
grep: non-fiction/OUP/Kauffman: Is a directory
grep: non-fiction/OUP/Rybczynski: Is a directory
travel_guides/berlitz2/Bahamas-History.txt:Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
travel_guides/berlitz2/Bahamas-History.txt:The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
```
In this curious case, "Lucayans" is found twice within the same file, but `grep -H` makes it seem like two matching files were found.  
Such as option would be useful if one needed both the line(s) and the file name that matches the conditions.
