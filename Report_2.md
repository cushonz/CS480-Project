﻿Report 2 - Design


By
Wayne Miles, Darrel Wheeler, Zach Cushon,and Manni Singh


NOTE: Many changes have been made since this report was written, the structure of the mentioned classes is different and can be found in the code demo folder, while the organization has changed the general approach to assignment is similar.

In order to properly assign TA’s to classes this program will need the following information:
* TA availability
   * Two dimensional array, [days][hours]
* TA Qualifications
   * This will be a subset of CSV data corresponding to the header of the csv
* Current TA Assignments
   * It is necessary to be able to check if the TA position is available or not in order to quickly identify non-matches and begin processing the next potential TA.


An object oriented approach  will be taken, with objects representing both TA applicants and class sections. The program will take a collection of class objects and a collection of TA objects as file inputs. 
“TA” Object Outline


        The Class TA has the following attributes:
* Name
* Student ID
* Availability
   * A table of integers
* Senior
   * This will denote the class standing of the TA in question
* Qualified
   * This will denote the classes that the TA has passed with a sufficient score
        “Section” Object Outline 
        The class Section has the following attributes:
* Course
   * This is the number following “CS” throughout the major, this will be used to check the qualified table against. This should be populated by an int array
* Professor
* Start Time
   * This is the time the class starts, checking TA availability against this number will denote if the student is free for the duration of the class.
* Black List 
   * A list of students that the professor will provide of potentially problematic TAs
   * These TAs will be automatically disqualified from positions they are black listed on
   * This is an optional argument
* Request
   * A list of students that the professor would like to have as their TAs
   * If two TAs of 1 kind are assigned to the position, the TA in the first position will be assigned the position and the second will be denied.
   * This is also an optional argument.


The program then performs the following checks(in order) :
1. Has the TA who is trying to be assigned to this class passed this course? 
   a. if True, next check
2. Is the TA available during course hours?
3. Check if the desired position is available
   a. This is determined first by checking the "492?" field
      1. If the flag is true, the program will attempt to assign the student to the 492 position
      2. If the flag is true, the program will attempt to assign the student to the 392 position
        
After repeating this process for all the students/classes, the TA positions will have been assigned.  Additionally we would like to sort the list of students in the initial list by graduation date with ties being broken by student ID number. The student with the lower ID number will take precidence since they have been at CWU longer.


We aim to set this project apart from the rest and create something that will generate a better experience for both students and professors of the computer science department at CWU.

