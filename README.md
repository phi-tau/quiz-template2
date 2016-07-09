This Latex problem repository and quiz template that allows teachers to build quizzes from individual question files. It is designed to fit my grading scheme, I'm sure you'll want to edit before it is useful to you.

##Folders
* **img** contains image files
* **questions** contains individual quiz items
 * naming doesn't matter. I do (the section or standard number)-(quiz week).tex, i.e., 10.4-5.tex 
* **quizzess** contians quiz files, which are collections of lins to questions**
 * naming does matter here, so that the for loop in main.tex will select the file
 * Use #-#.tex. I use the first number to be quarter or grading period, and then the second as the week number
  * i.e., for the 3rd week in the second quarter, I'd name it 2-3.tex

##Files
* **main.tex** is where the compilation of questions into quizzes into one large quiz document happens (main.pdf)
 * You can change the class and teacher name here.

##Commands
In questions, you can use
* ```\drawgraph``` to insert a grid for students to answer with a 2-D graph
* ```\blank``` to insert a 100pt blank
* ```\imgA{file}``` to insert a small image (must be in img directory, no file extensions)
* ```\imgB{file}``` to insert a large image (must be in img directory, no file extensions)

Then create the header using ```\quizheader{QUIZ_NAME}{NUMBER_OF_POINTS}```. Edit the quiz header command in main.tex to your liking.

Insert questions using ```\question{QUESTIONFILENAME}{QUESTIONNUMBER}```
* QUESTIONFILENAME doesn't use an extension (must be .tex in the questions folder)
* QUESTIONNUMBER could also be text. I generally number question by their standard number in the course or by section number in the book.


To compile into a pdf, use the command below. It needs to be run twice to generate the table of contents.
```
pdflatex main && pdflatex main
```

On OS X, you can add this to your .zshrc or .bashrc file to do it all at once and open the final product:
```
alias quiztime="pdflatex main && pdflatex main && open main.pdf
```
