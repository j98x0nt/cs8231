java c
CIT 5930 Module07 HW: LC-4 Assembly Programming
Due Date: Friday 10/18 @11:59pm via codio submission only
Which Lectures Should I Watch to Complete this Assignment?: Module07
Video lectures can be found on canvas under “Class Recordings ”
PDF files of the module lectures can be found on canvas under “Files->Module_Slides”
What textbook sections should I read to complete this assignment?
READING: Chapters 6-7 of the book will be helpful, but realize they refer to the LC3 and we are using the LC4; if you are new to programming you will still find these chapters helpful.
PennSim and the CODIO platform:
For this HW assignment, we will use a tool called PennSim, it is a simulator that behaves as an LC4 Assembler, a loader, and even a simulator.  It was demonstrated during lecture.  PennSim is written in Java, and while it could ideally run on any platform, we will instead use a platform. called: Codio.  Codio is a web-based Linux-based computer that you can use through your browser to write and run programs in LC4 Assembly, C, and many other languages.  We will use it for this HW to run PennSim, but in future HWs we will use it to run various C-compilers.
Because codio is a web-based computer (also called a Virtual Machine – VM), you can access it from anywhere.  It also gives each student a standard environment to work in.  If you have a Mac or PC, it won’t matter, everyone will be working on the same type of computer.  Another wonderful feature of this tool is that a TA (or I) can login to your web-based codio computer from anywhere, in order to help you debug problems if they should arise.  The last very helpful feature is that this tool allows you to more easily submit coding HWs (instead of using gradescope or canvas).  But I ask you for your patience, this is the first semester we are trying this tool and so I’m sure there will be glitches along the way.
Setting up Codio for this HW:
1)   Navigate to:https://codio.com/p/signup?courseToken=lady-diploma
a.   Signup for codio using your upenn.edu email account
b.   Once you sign up for codio, you can use the same login for all future HWs
2)   Once codio is open, open the assignment by doing the following:
a.   From the “Course” Dropdown box in the middle of the screen, select:
CIT 5930 – F24 – ONCAMPUS
b.   From the “Module” Dropdown box in the middle of the screen, select:
Assembly-Assignments
c.   A list of assignments should appear, select:
MOD_07_HW_Assembly
d.   This logs you into your instance of the codio virtual machine
e.   It is a Linux based virtual computer that uses “Ubuntu” flavored Linux
3)   When Codio opens, a file called: “README.md” will be open, you may close it
Starting PennSim in Codio
1)   Opening up the codio X-server:
a.   Along the top menu, click on the globe icon next to “PennSim Window”
b.   If things work, you’ll get a blank black window, this window is called an “Xserver”
i.   It can display any “graphical” output of your codio virtual machine
c.    If you see an error # 502.  Contact the professor right away  Don’t attempt to solve this on your own.
2)   Opening up the codio Terminal Window:
a.   On the left hand side of the screen, you will see what’s called the “ File Tree”
i.   This is a listing of all the files on your virtual codio computer
b.   Click on the small arrow/line icon; I’ve circled it on the image below: 
c.   This will bring up a Linux Terminal Window, where you can manually type in commands to your computer.
d.   Type in (DO NOT COPY  PASTE THIS – type it in manually) the following command to start the LC4 Simulator (PennSim):
java -jar PennSim.jar 
(DO NOT COPY  PASTE THIS – type it in manually)
i.   this command uses Java to start our PennSim program
e.   In the “Xserver” window, PennSim (the java app) will open up: i.   click on the “Preview http … .” tab to see PennSim: 
Running Multiply.ASM in PennSim
1)   From the “ File Tree” click on the file: multiply.asm
a.   Examine the contents of the file, notice it is the multiply algorithm from lecture 2)   From the File Tree, click on the file: multiply_script.txt
a.   This file shows all of the commands that must be entered into PennSim to
assemble and load the file, examine it line by line
3)   Return back to the “PennSim” window you opened in the last section
a.   In PennSim’s “Controls” section, type in:
script. multiply_script.txt
Then press enter:
4)   Press the “Step” button to run the program line by line.  Carefully examine the register file, the program counter, and the state of the machine as you run it line by line!
Learn to use PennSim:
1)   PennSim has a lot of features, we’ve made a video of how to use it and posted it on canvas under: Files->Resources->Tutorials-> PennSimTutorial in 5minutes.wmv
a. Watch this video before continuing on with the HW
b.   Experiment with multiply.asm since its loaded into your PennSim
2)   There is a proper manual for PennSim; it is handy to review.  It is also on canvas under: Files->Resources->Tutorials-> PennSimStartGuide.zip
Assigned Problems (to be done individually, NOT group work):
--Make certain you’ve setup codio and learned PennSim before attempting these problems!
1)   WHILE LOOPS IN ASSEMBLY
The pseudo-code below describes the mathematical operation known as a factorial.  When   the algorithm below is completed, the variable B will contain A!  For the given positive value of A, the factorial is defined as 5 x 4 x 3 x 2 x 1 = 120.
Here is the pseudo-code for the factorial algorithm:
A = 5 ;  // example to do 5!
B = A ;  // B=A! when while loop completes
while (A > 1) {
A = A - 1 ;
B = B * A ;
}
Implement the given algorithm using LC4-Assembly.  Use R0 to hold variable A, and R1 to hold variable B.  In your codio “File Tree” you’ll see a file I created for you:factorial.asm.  Open the factorial.asm file on codio and implement the factorial algorithm above within it.  Test it using the other file I’ve provided for you:
factorial_script.txt.  You may hard code A to have the value 5, but when we grade your assignment, we will try out different #s to ensure your algorithm is working.  So be certain to run your program in PennSim and make certain it is working for different values of A.
In your program and in your script. file be certain to set a breakpoint labeled “END.”  (see multiply.asm for an example of this).  This will ensure you program ends, instead of requiring an infinite loop to stop execution.  Be certain to comment your code (but not over comment), to help us understand the flow of your program as we grade.
POINTS WILL BE DEDUCTED IF YOUR CODE IS NOT COMMENTED!For this problem you will edit and change the 2 files: factorial.asm and factorial_script.asm
2)   SUBROUTINES IN ASSEMBLY
For this problem, you’ll convert your factorial program from problem #1 into a subroutine and call it using JSR.
File setup: After you’ve completed problem #1, copy the file: factorial.asm file in the codio “ File Tree” by right-clicking on the file, clicking “copy” and then right clicking once again in the file tree and pressing “paste.”  Give it the name: factorial_sub.asm.
Next, copy and paste the file: factorial_script.txt.  Give it the name: factorial_sub_script.txt.   Next, you’ll need to open the new file:
factorial_sub_script.txt – to ensure it assembles and loads “factorial_sub.asm” instead of “factorial.asm”
What to do for this problem:
Add the label: SUB_FACTORIAL to the top of your factorial program.  Remove any “CONST”   instructions you may have that would set the variable A (register R0).  We want “A” to be an argument to your subroutine.  Replace the END label with a RET statement, as we wish B to  be the return value for your function.
Above your subroutine code, implement the following code to call your subroutine:
MAIN
A = 6 ;
B = sub_factorial (A) ;
// your sub_factorial subroutine goes here
END
After you return from the subroutine, make certain to “jump” over your subroutine to a new END label, so that your subroutine isn’t executed twice!  Make certain to set END as a breakpoint in your script. file.
Next, add an “If/else” statement to the start of your subroutine to ensure A is a positive # and is <= the largest number your assembly can work with. If A is < 0 or > the largest number your algorithm can work with, set B = -1 and return from the subroutine without attempting to find the factorial.
POINTS WILL BE DEDUCTED IF YOUR CODE IS NOT COMMENTED!
POINTS WILL ALSO BE DEDUCTED IF YOU DON’T CALL THE SUBROUTINE USING AJSR and RETURN FROM IT USING AN RET!
3)   WORKING WITH DATA MEMORY IN ASSEMBLYFor this problem, you will have to review the example of working with data memory in  lecture, as well as the “sum_numbers.asm” example in the PennSimStartGuide Manual discussed at the start of this assignment.
File setup: After you’ve completed problem #2, copy the file: factorial_sub.asm and paste it with the new name: dmem_fact.asm.  Then copy:
factorial_sub_script.txt and paste it with the new name:
dmem_fact_script.txt.  Next, update dmem_fact_script.txt to ensure assembles and loads “dmem_fact_script” instead of “factorial_sub.asm”
What to do for this problem:
Recall the “ .FILL” directives mentioned in lecture and also in the sum_numbers.asm
example from the PennSimStartGuide.  Use the .FILL directive to populate 5 rows of data
memory starting address x4020 with the numbers: 6, 5, 8, 10, -5.  Write a short assembly
program that will load each of the 5 rows of data memory that you’ve populated and call
the subroutine you’ve created in problem #2 on each of those rows.  After the factorial
subroutine is run on each row, you should then store the #’s factorial back to data memory overwriting the original #.  As an example of how the first row of data memory should look after your program completes, address x4020, should have the number #720.
POINTS WILL BE DEDUCTED IF YOUR CODE IS NOT COMMENTED!
e.c. (5 points): In addition to the program above, create a new program in dmem_fact_ec.asm, that allows your subroutine: SUB_FACTORIAL, to take in as its only argument a data memory address (instead of a value).  The new SUB_FACTORIAL should then  load the value from data memory, specified by the argument, find its factorial, and store the result back in data memory (instead of returning a value).  Update your code from problem #3 to call this subroutine properly.
Directions on how to submit your work:
You must submit two things for this HW:
1)   An anti-plagiarism form. in gradescope
2)   Your codio work
• Submitting in gradescope:
o Download the file: CIT593_HW-Plagiarism_Signature.pdf from canvas
o This must be done for each electronic assignment in our course
o Print it out and sign the form.
o Scan in the printed out form. (using your favorite app or scanner) and upload it to gradescope
o Your codio submission will not be graded unless you have submitted this form. on gradescope•   Submitting in Codio:
o To manually submit your work, from the codio menu, choose: “EDUCATION”
From the education menu, choose: “ Mark As Completed”, type yes and press OK
On our end of codio, we will see your project as “completed.”  Then we can     open it and grade your HW.  You can still see your files, but you won’t be able to modify them any further after you mark your HW as completed.
Note the late policies that are outlined in the syllabus.•    Important Note on Plagiarism:
o We will scan your HW files for plagiarism using an automatic plagiarism detection tool.
o If you are unaware of the plagiarism policy, make certain to check the syllabus



         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
