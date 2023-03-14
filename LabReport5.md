# Lab Report 5
---


This Report focuses on 4 options or alternate ways to use the command grep

* -c, --count
* -i, --ignore-case
* -n, --line-number
* -C number


---

## -c or --count
This command counts how many lines in each file contains the pattern. This is useful to figure out which files contain the specficed pattern the most/least or to find out how many times it is used within a single file. 
I found this using ChatGPT and [linuxcommand](https://linuxcommand.org/lc3_man_pages/grep1.html)

for example within the Abernathy directory within written_2
You can run the following which also uses -R to search recursivly through all ther files within the working directory.
```
grep -Rc "Bond"
```
The output of that command is:
```
./ch2.txt:1
./ch3.txt:0
./ch1.txt:6
./ch7.txt:0
./ch6.txt:0
./ch8.txt:0
./ch9.txt:0
./ch15.txt:0
./ch14.txt:0
```

Another example would be running the following within non-fiction/OUP/Berk
```
grep -c "child" ch1.txt
```
The output is:
```
127
```


---

## -i, --ignore-case
This searched for the specfied pattern while ignoring the case of the letters within the pattern. This can be very useful to still find files that contain the pattern if the word(s) may or may not be capitalized.
I found this using ChatGPT and [linuxcommand](https://linuxcommand.org/lc3_man_pages/grep1.html)

An example of this is looking for Talia in the ch1.txt file in non-fiction/OP/Berk.
Using -i in tandum with -c,
```
grep -ic "talia" non-fiction/OP/Berk/ch1.txt
```
The outpuut is 
```
2
```
If you were to run just 
```
grep -c "talia" non-fiction/OP/Berk/ch1.txt
```
the output would be 
```
0
```

Another example is using -i along with -R and -c to look recursivly within the directory and list how many instances of the pattern are found in each file. 
```
grep -Ric "Shark" non-fiction/OUP/Berk
```
The output is the follwiing which finds an instance of shark in CH4 despite "shark" having a lowercase S in the file.
```
non-fiction/OUP/Berk/ch2.txt:0
non-fiction/OUP/Berk/ch1.txt:0
non-fiction/OUP/Berk/CH4.txt:1
non-fiction/OUP/Berk/ch7.txt:0
```


---

## -n, --line-number
This option displays the line number where the pattern is found within the specified file at the begining of the output. This is useful to know exactly where within the file the patttern is occuring so it can more easily be found when looking at the file seperatly or to go to the line number to look at the surrounding information. 
I found this using ChatGPT and [linuxcommand](https://linuxcommand.org/lc3_man_pages/grep1.html)

Here is an example of it being used:
```
grep -n "shark" non-fiction/OUP/Berk/CH4.txt
```
The output for the above command is the following, indicating that "shark" is found on line 231 in the file
```
231:•Inﬂuencing another’s social behavior. Joint make-believe can be an effective strategy for attaining a social goal. When 2-year-old Molly stood at the top of a slide and asked for help, her mother tried to get her to slide down on her own. Molly refused and stepped into pretend: “A shark . . . There’s a shark in the sand!” Molly’s mother immediately helped her down.64**
```

Here is an example when it is used in combination with -R which searched recursivily. -R causes the path to the file where it is found to be displayed at the start of the output.
```
grep -Rin "Shark" non-fiction/OUP/Berk
```
In the output, the line number from the -n option is displayed after the path to teh file, but befoe any of the text from the line that contains "shark"

```
non-fiction/OUP/Berk/CH4.txt:231:•Inﬂuencing another’s social behavior. Joint make-believe can be an effective strategy for attaining a social goal. When 2-year-old Molly stood at the top of a slide and asked for help, her mother tried to get her to slide down on her own. Molly refused and stepped into pretend: “A shark . . . There’s a shark in the sand!” Molly’s mother immediately helped her down.64
```

---

## -C number
This displays a certain number of lines of context before and after the found pattern. This is useful to only read through the sentances around the found word instead of getting the entire file returned. 
I found this using ChatGPT and [linuxcommand](https://linuxcommand.org/lc3_man_pages/grep1.html)

```
grep -C 1 "Talia" non-fiction/OUP/Berk/ch1.txt
```
The output is 
```
•Angela, mother of a 4-year-old and 6-year-old: My husband and I have demanding careers and need to bring work home in the evenings. I’ve read that it’s the quality of time we spend with our children that’s important, not the quantity. We try hard to give Victor and Jeannine our undivided attention, but they’re often whiny, demanding, and quarrelsome. Many times we end up sending them to their rooms or letting them watch TV, just to get some peace after a long day. What’s the best way to create quality parent–child time?
•Talia, mother of a 7-year-old: My son Anselmo, a ﬁrst grader, constantly asks us to help him with his homework. His father ﬁrmly insists that he do it by himself. Anselmo tries, but he gets so frustrated and upset that I move in and help, even in the face of opposition from his dad. By that time, Anselmo is on such a short string that I do most of the assignment for him. Should we be helping Anselmo with his homework and, if so, how?
•Noah and Suzanne, parents of a 2-year-old: When our parents were raising us, they seemed conﬁdent of their power and inﬂuence. Recently we read that how children turn out is mostly written in their genes; there’s little we as parents can do about it. Does parenting really matter?
--
The core lesson to be learned from our discussion so far is that development is a matter of children’s genetic/biological potential undergoing a cultural metamorphosis, a process that cannot take place without parents and teachers as thoughtful and committed participants in children’s lives. From the sociocultural perspective, parents and teachers are leaders in awakening children’s minds and fostering their development; children are apprenticed to these experts.
Hence, to Talia’s concern, posed at the start of our discussion: Should she and her husband, Jim, respond to 7-year-old Anselmo’s pleas for help with his homework? Given what we currently know about how children develop, the answer is a resounding yes. Rather than promoting dependency (as Talia and her husband fear), assisting Anselmo is the surest route to competent functioning, provided parental interaction builds on Anselmo’s current capacities and remains sensitive to his unique characteristics. Now let’s turn to just how parents and teachers can advance children’s knowledge and skills.
```
It prints out context for both instances of "Talia" in the file.

It can also be used with -R to search recrusibly in all files within the specfiied directory.
```
grep -RC 1 "shark" non-fiction/OUP/Berk
```
The output includes context for the instance of "shark" and includes which file it is found within.
```
non-fiction/OUP/Berk/CH4.txt-•Expressing and regulating emotion. Traci’s exploration, with her mother’s help, of what it might be like to have a mother who got sick and died exempliﬁes how parents and children use make-believe to express and manage intense feelings. In pretend scenarios, Traci acted out feeling ill, feeling better, sadness, happiness, worry, love, and caring.
non-fiction/OUP/Berk/CH4.txt:•Inﬂuencing another’s social behavior. Joint make-believe can be an effective strategy for attaining a social goal. When 2-year-old Molly stood at the top of a slide and asked for help, her mother tried to get her to slide down on her own. Molly refused and stepped into pretend: “A shark . . . There’s a shark in the sand!” Molly’s mother immediately helped her down.64
non-fiction/OUP/Berk/CH4.txt-•Having fun. As illustrations of adult–child make-believe throughout this chapter affirm, most of the time parents and children engage in imaginative play just for fun. In fact, some theorists have argued that the earliest expressions of humor emerge out of fantasy play.65 Consistent with this claim, participating in adult–child make-believe seems to precede children’s ﬁrst verbal jokes. One toddler named Ari, having become an avid make-believer, soon showed a corresponding rise in joking. At 20 months, he touched a picture of a sheep in a book his mother was reading to him, exclaimed “Neigh!” and laughed hysterically. At 21 months, while watching his mother wash dishes, he remarked, “Nutmeg [the family cat] drinks water with spoon” and then interpreted, “Funny thing! Ari tell Mommy joke.”66 As Ari’s humor makes plain, pretending is not just a pleasurable activity in itself but brings pleasure to life in general.
```
