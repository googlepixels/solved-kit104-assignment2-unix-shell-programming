Download Link: https://assignmentchef.com/product/solved-kit104-assignment2-unix-shell-programming
<br>



<strong> </strong>There are three (3) shell programming tasks in this assignment. This is an individual assignment. You are required to make a directory named kit104a2 under your home directory (on alacritas), and use kit104a2 as your working directory for this assignment.

Assignment submissions will be marked by the KIT104 tutors on alacritas. If you write and test your scripts elsewhere it’s your responsibility to ensure that your scripts run correctly on the School UNIX system (alacritas).

<h1>Task A</h1>

Write a shell script (to run on the Bourne shell) to copy all the files from the directories named dir1 and dir2 into a new directory named dir3.

(1). In the beginning of your script you need to check that the directories dir1 and dir2 exist under the current directory (if not, your script displays an error message and then exits).

(2). All the three directory names are supplied as arguments, and the new directory dir3 must not currently exist (ie, the creation of dir3 is part of the script).

(3). The script first copies all the files from dir1 into dir3.

(4). The script then copies every file from dir2 to dir3 subject to these conditions: if the file from dir2 is not already present in dir3, or if the dir2 file is newer than the same dir3 file it will overwrite its namesake in dir3.

(5). Remove all the temporary files (if any) at the end of your script.

(6). Your script must generate an output similar to the sample output shown in the top box of page 2.

Hint: You should note that the cp command without any option does not preserve certain attributes (such as ownership and timestamps).

Your script for this task must be named <strong>cp2.sh</strong>. Make sure that your script is user-friendly and follows common sense. The following is a sample output of the script. The $ is the shell prompt.

<table width="569">

 <tbody>

  <tr>

   <td width="569"><strong>$ ./cp2.sh  dir1  dir2  dir3 </strong>These files from dir1 copied into dir3:a.c  b.c  file1.c These new file(s) from dir2 copied into dir3: file2.cThese file(s) from dir2 copied into dir3 and overwrite(s) their namesakes in dir3: a.c</td>

  </tr>

 </tbody>

</table>




The following sample outputs verify the above result:

<table width="569">

 <tbody>

  <tr>

   <td width="569"><strong>$ ls </strong>cp2.sh dir1  dir2  dir3 <strong>$ ls -l dir1 </strong>total 12-rw-r–r– 1 sxu staff  9 Aug  2 12:52 a.c-rw-r–r– 1 sxu staff  9 Aug  2 12:52 b.c-rw-r–r– 1 sxu staff  9 Aug  2 12:52 file1.c <strong>$ ls -l dir2 </strong>total 12-rw-r–r– 1 sxu staff  9 Aug  2 12:53 a.c-rw-r–r– 1 sxu staff  9 Aug  2 12:51 b.c-rw-r–r– 1 sxu staff  9 Aug  2 12:53 file2.c <strong>$ ls -l dir3 </strong>total 16-rw-r–r– 1 sxu staff  9 Aug  2 12:53 a.c-rw-r–r– 1 sxu staff  9 Aug  2 12:52 b.c-rw-r–r– 1 sxu staff  9 Aug  2 12:52 file1.c-rw-r–r– 1 sxu staff  9 Aug  2 12:53 file2.c</td>

  </tr>

 </tbody>

</table>







(Continued next page)<strong>                                                  </strong>

<h1>Task B</h1>

Write a shell script (to run on the Bourne shell) that runs an infinite loop to monitor which users on a <em>denial list</em> have logged into the UNIX system more than once.




(1). The denial list must be stored in a text file named user.deny which lists which users are not allowed multiple logins, specified by one username per line.




(2). In the beginning of the script you need to check that the user.deny file exists under the current directory, and if not, your script displays a message to say so and then exits.




(3). Every 3 seconds, the script must display a warning message to report users on the denial list who have logged in multiple times. Display the user’s full name instead of his/her username in the warning message.




(4). It’s unnecessary for your script to handle the situation where a user logs in and then logs off immediately (i.e. within a 3 second interval).




Your script for this task must be named <strong>mlog.sh</strong>. The following is a sample output of the script (It is OK if the script leaves behind temporary files when it is finally interrupted). The $ is the shell prompt.




<table width="569">

 <tbody>

  <tr>

   <td width="569"><strong>$ ./mlog.sh </strong> No user on the user.deny list has multiple logins No user on the user.deny list has multiple logins The user John Smith (on the denial list) has logged in more than once!The user Adam Jones (on the denial list) has logged in more than once! No user on the user.deny list has multiple logins No user on the user.deny list has multiple logins The user David Monks (on the denial list) has logged in more than once!The user Nick Andrews (on the denial list) has logged in more than once!… … … … … … … … … … … … … … … …</td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<strong> </strong>

<h1>Task C</h1>

Dominion Consulting in Sydney needs a shell script (to run on the Bourne shell) to maintain its employee records file, which contains the following information about each employee: telephone number (8 digits, first digit nonzero), family name (alphabetic characters), first name (alphabetic characters), department number (2 digits), and job title (alphabetic characters). This script should let users <strong>add</strong>, <strong>delete</strong>, <strong>search</strong> for, and <strong>display</strong> specific employee information.




(1). Create a text file named records containing the following records with fields delimited by colons:




95671660:Jones:Sarah:45:sales manager

93272658:Smith:John:43:technical manager

98781987:Williams:Nick:35:computer officer

99893878:Brown:Sarah:12:electrician

95673456:Couch:David:26:chef

95437869:Anderson:Sarah:19:CEO




(2). In the beginning of your script you need to check to see whether the required text file (records) actually exists under the current directory (if not, your script displays a message and then exits).




(3). Your script (must be named <strong>menu.sh</strong>) will present a menu of operations that a user may choose from. Among other tasks, these operations automate the following four activities:




<ol>

 <li>Displaying all current employee records on the screen.</li>

 <li>Searching for and displaying specific employee record(s) (search all fields, ignoring case)</li>

 <li>Adding new records to the records</li>

 <li>Deleting records from the records</li>

</ol>




(4). Your script must produce the following menu:




Dominion Consulting Employees Info Main Menu

============================================

<ul>

 <li>– Print All Current Records</li>

 <li>– Search for Specific Record(s)</li>

 <li>– Add New Records</li>

 <li>– Delete Records Q – Quit</li>

</ul>




(5). After a user makes a selection and that the selected operation has been completed, the menu must be displayed again so that the user can make another selection.




(6). You must validate the employee details when adding a new record.




(7). A valid family name, first name and job title must be alphabetic characters and/or spaces. The first digit of a valid phone number (of eight digits) must not be zero. Each telephone number must be unique. A valid department number must only contain 2 digits.




Here is a sample output of your script. The $ is the shell prompt. The items in italics are not part of the sample output. They are hints indicating how your script should behave.




<strong>$ ./menu.sh </strong>




Dominion Consulting Employees Info Main Menu

============================================

<ul>

 <li>– Print All Current Records</li>

 <li>– Search for Specific Record(s)</li>

 <li>– Add New Records</li>

 <li>– Delete Records</li>

</ul>

Q – Quit




Your Selection: 1(<em>user input</em>)

95671660:Jones:Sarah:45:sales manager

93272658:Smith:John:43:technical manager

98781987:Williams:Nick:35:computer officer

99893878:Brown:Sarah:12:electrician

95673456:Couch:David:26:chef

95437869:Anderson:Sarah:19:CEO




Press Enter to continue… (<em>user presses Enter here</em>)




Dominion Consulting Employees Info Main Menu

============================================

<ul>

 <li>– Print All Current Records</li>

 <li>– Search for Specific Record(s)</li>

 <li>– Add New Records</li>

 <li>– Delete Records</li>

</ul>

Q – Quit




Your Selection: 5(<em>user input</em>)

Invalid selection




Press Enter to continue… (<em>user presses Enter here</em>)




Dominion Consulting Employees Info Main Menu

============================================

<ul>

 <li>– Print All Current Records</li>

 <li>– Search for Specific Record(s)</li>

 <li>– Add New Records</li>

 <li>– Delete Records</li>

</ul>




<table width="561">

 <tbody>

  <tr>

   <td width="561">Q – Quit Your Selection: 2(<em>user input</em>)Enter keyword: Sarah (<em>user input</em>)95671660:Jones:Sarah:45:sales manager99893878:Brown:Sarah:12:electrician95437869:Anderson:Sarah:19:CEO Press Enter to continue… (<em>user presses Enter here</em>)Dominion Consulting Employees Info Main Menu============================================1  – Print All Current Records2  – Search for Specific Record(s)3  – Add New Records4  – Delete RecordsQ – Quit Your Selection: 2 (<em>user input</em>)Enter keyword: Monks (<em>user input</em>)Monks not found Press Enter to continue… (<em>user presses Enter here</em>)Dominion Consulting Employees Info Main Menu============================================1  – Print All Current Records2  – Search for Specific Record(s)3  – Add New Records4  – Delete RecordsQ – Quit Your Selection: 2(<em>user input</em>)Enter keyword: (<em>user simply presses Enter without typing in anything</em>)Keyword not entered Press Enter to continue… (<em>user presses Enter here</em>)Dominion Consulting Employees Info Main Menu============================================1  – Print All Current Records2  – Search for Specific Record(s)3  – Add New Records4  – Delete RecordsQ – Quit Your Selection: 3(<em>user input</em>)Add New Employee RecordPhone Number (xxxxxxxx): (<em>user simply presses Enter without typing in anything</em>)Phone number not enteredPhone Number (xxxxxxxx): 00123456 (<em>user input</em>)Invalid phone numberPhone Number (xxxxxxxx): 95437869 (<em>user input</em>)Phone number existsPhone Number (xxxxxxxx): 99887766 (<em>user input</em>)Family Name: abc123 (<em>user input</em>)Family name can contain only alphabetic characters and spaces</td>

  </tr>

  <tr>

   <td width="561">Family Name: Warren (<em>user input</em>)Given Name: Tony5 (<em>user input</em>)Given name can contain only alphabetic characters and spaces Given Name: Tony (<em>user input</em>) Department Number: 123 (<em>user input</em>)A valid department number contains 2 digitsDepartment Number: 23 (<em>user input</em>)Job Title: accountant1 (<em>user input</em>)Job title can contain only alphabetic characters and spaces Job Title: accountant (<em>user input</em>) Adding new employee record to the records file …New record saved (<em>display this only after saving record is successful</em>) Add another? (y)es or (n)o: n (<em>user input</em>) (<em>Note: if the user answer is y here then the above procedure is repeated</em>) Dominion Consulting Employees Info Main Menu============================================1  – Print All Current Records2  – Search for Specific Record(s)3  – Add New Records4  – Delete RecordsQ – Quit Your Selection: 4(<em>user input</em>)Delete Employee Record Enter a phone number: 05671660 (<em>user input</em>)Invalid phone numberEnter a phone number: 99999999 (<em>user input</em>)Phone number not foundEnter a phone number: 95671660 (<em>user input</em>)95671660:Jones:Sarah:45:sales manager Confirm deletion: (y)es or (n)o: y (<em>user input</em>)Record deleted. (<em>This message is displayed only after this record has been successfully deleted from the </em><em>records</em><em> file</em>)(<em>If the user answer is n then the main menu is displayed again.  Then if the user enters Q or q then the script is terminated.</em>) </td>

  </tr>

 </tbody>

</table>







(Continued next page)

<strong>             </strong>

<h1>For All Your Scripts</h1>

You must  x Include your <strong>full</strong> <strong>name</strong>, student <strong>ID</strong>, and a <strong>brief introduction</strong> of what the script does in all your shell scripts, as a comment in the beginning of each script.

x Make your scripts run on the Bourne shell, regardless of which shell the user of your scripts is currently on.

x Add in-line comments to help other people understand your scripts.

x Use “
” where appropriate to make the output of your scripts more readable.

x Note that your script structure and layout are also important as they will be marked as part of the assessment process.