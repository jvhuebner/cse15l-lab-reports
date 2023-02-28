## Lab Report 4

### Step 4
Keys pressed:
`ssh cs15lwi23avk@ieng6.ucsd.edu <enter>`
I typed in the command to log into my ieng6 account. I already set up the SSH key so I did not need to enter a password.


### Step 5
Keys Pressed:

`git clone https://github.com/jvhuebner/lab7 <enter>`
I typed in the command to clone my fork. 

### Step 6

Keys pressed:
`cd l<tab><enter>`
`javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java <enter>`
`java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests <enter>`

I used tab to auto fill for `lab7` to change my working directory. I types in the commands to compile the java files
and then run the Tests.

### Step 7
Keys pressed:
`nano ListExamples.java <enter>`
`option + V <up><up><up><up><up><up><up><left><left><delete> 2 <enter>`
`option o <enter>`
`option X`

I used nano to open and edit the ListExamples.java file. I used `option V` to go all the way to the bottom and then
used arrow keys to get to the desired line to fix the bug. I replaced `index1` with `index2`.
I used option + o and then enter to save my changes and opttion + X to exit the file.
  
  
### Step 8

Keys pressed:
`<up> <up> <enter>`
`<up> <up> <up> <enter>`

The  `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` command was up 2 in the search history 
so I pressed the up arrow twice to acces it.
The `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`command was 
up 3 in the search history so I pressed the up arrow twice to acces it.

### Step 9

Keys pressed:
`git add ListExamples.java`
`git commit -m "Updated"`
`git push git@github.com:jvhuebner/lab7.git`

I used git add to add the fixed ListExamples.java file. I then committed it with the message "updated".
To push the commit I typed in the local SSH on the fork.



