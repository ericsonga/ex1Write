..  Copyright (C)  Mark Guzdial, Barbara Ericson, Briana Morrison
    Permission is granted to copy, distribute and/or modify this document
    under the terms of the GNU Free Documentation License, Version 1.3 or
    any later version published by the Free Software Foundation; with
    Invariant Sections being Forward, Prefaces, and Contributor List,
    no Front-Cover Texts, and no Back-Cover Texts.  A copy of the license
    is included in the section entitled "GNU Free Documentation License".

.. setup for automatic question numbering.

.. 	qnum::
	:start: 1
	:prefix: 2-1-

Algorithms for Working with List Items - Fix Code
======================================================

Example: Count Target Values
------------------------------

One of the common things to do with a list is to count the number of times a target value appears in a list.  To do this initialize a count to zero and then loop through all the values in the list.  If the current value is equal to the target value increment the count.  Return the count.  

The code below also contains tests to make sure that the code works as intended.  For example ``countTargetValues(5, [1, 2, 3])`` should return 0 since there are no 5's in the list and ``countTargetValues(5, [5, 4, 5])`` should return 2 since there are two 5's in that list.

Click the "Run" button to run the tests that check that this code is working correctly.  All tests should print "Pass".

.. activecode:: Count_Targets

   # define the function
   def countTargetValues(target, numList):
   
       # initialize the count
       count = 0
  
       # loop through all the indices
       for index in range(len(numList)):
       
           # get the current value
           current = numList[index]
       
           # if the curent value is equal to the given target value
           if (current == target):
           
               # increment the count
               count = count + 1
               
       # return the count
       return count
       
   from unittest.gui import TestCaseGui

   class myTests(TestCaseGui):

       def testTarget(self):
           self.assertEqual(countTargetValues(5, [1, 2, 3]), 0)
           self.assertEqual(countTargetValues(5, [3, 2, 5]), 1)
           self.assertEqual(countTargetValues(5, [5, 4, 5]), 2)
           self.assertEqual(countTargetValues(5, [5, 5, 5]), 3)
           
   myTests().main()
   
Practice: Count Target Values in Range
----------------------------------------

You can also count the number of target items in a list between a first and last index, including the values at the first and last indices.  To do this initialize a count to zero and then loop through all the values in the list from the start index to the end index. If the current value is equal to the target value increment the count. Return the count.
   
.. note ::
   
    Remember that the ``range(first, last)`` function actually returns the values from first to last - 1.  So ``range(1,3)`` returns ``[1,2]``. 

The following code should count and return the number of values in a list that are equal to the passed target value and are between the given start and end indices (including the values at the start and end indicies), but it has errors. 

The code below contains tests which will check if your code is correct.  For example ``countTargetInRange(3, 0, 1, [3, 3, 2, 6])`` should return 2 since there are 2 values that are equal to 3 from index 0 to 1.  The call ``countTargetInRange(3, 0, 3, [2, -3, 0, 1])`` should return 0 since there are no values that are equal to 3 in that list from index 0 to 3.

Fix the errors so that all the tests all print "Pass" when you click the "Run" button.  The error messages and test results are displayed below the code. 

.. activecode:: Count_Target_In_Range

   def countTargetInRange(target, start, end, numList)
   
       count = 1
  
   for index in range(start, end+1):
   
           current = numList[index]
       
           if current == target:
           
               count = Count + 1
               
       return coun
       
   from unittest.gui import TestCaseGui
       
   class myTests(TestCaseGui):

       def testTarget(self):
           self.assertEqual(countTargetInRange(3, 0, 1, [3, 3, 2, 6]), 2)
           self.assertEqual(countTargetInRange(3, 0, 3, [2, -3, 0, 1]), 0)
           self.assertEqual(countTargetInRange(3, 1, 2, [1, 2, 3]), 1)
           self.assertEqual(countTargetInRange(3, 0, 1, [1, 2, 3]), 0)
           self.assertEqual(countTargetInRange(3, 0, 2, [5, 4, 5]), 0)
           
   myTests().main()
  
   
Example: Find the Maximum Value
--------------------------------
    
Another common thing to do is find the maximum value in a list.  To do this create a variable to keep track of the maximum value found so far and set it to the first item in the list to start.  Then loop through all the values in the list and each time test if the current value is greater than the saved maximum value.  If it is, then set the maximum value to the current value.  Return the maximum value.

The code below also contains tests to make sure that the code works as intended. For example ``getMaximum([9, 3, 8])`` should return 9 and ``getMaximum([-2, -1, -3]), -1)`` should return -1.

Click the "Run" button to run the tests that check that this code is working correctly.  All tests should print "Pass".

.. activecode:: Get_Max

   # define the function
   def getMaximum(numList):

       # set the maximum to the first item
       maximum = numList[0]

       # loop through all the values 
       for current in numList:

           # if num is greater than the maximum so far
           if current > maximum:

               # set the maximum to the current value
               maximum = current

       # return the maximum value 
       return maximum
       
   from unittest.gui import TestCaseGui
       
   class myTests(TestCaseGui):

       def testTarget(self):
           self.assertEqual(getMaximum([9, 3, 8]), 9)
           self.assertEqual(getMaximum([-2, -1, -3]), -1)
           self.assertEqual(getMaximum([2, 3, 5, 15]), 15)
           self.assertEqual(getMaximum([32, 64, 28]), 64)
           self.assertEqual(getMaximum([3]), 3)
           
   myTests().main()
   
Practice: Find the Minimum Value
---------------------------------
   
The following code should find and return the minimum value in a list, but it contains errors.  To find the minimum value, create a variable to keep track of the minimum value found so far and set it to the first item in the list to start.  Then loop through all the values in the list and each time test if the current value is less than the saved minimum value.  If it is, then set the minimum value to the current value.  Return the minimum value.

The code below contains tests which will check if your code is correct. For example ``getMinimum([9, 3, 8])`` should return 3 and ``getMinimum([-2, -1, -3])`` should return -3.

Fix the errors so that all the tests all print "Pass" when you click the "Run" button.  The error messages and test results are displayed below the code. 
   
.. activecode:: Get_Min

   def getMinimum(numList:

       minimum = numList[0]

       for current in numlist:

           if current > minimum

               min = current

       return minimum
       
   from unittest.gui import TestCaseGui
       
   class myTests(TestCaseGui):

       def testTarget(self):
           self.assertEqual(getMinimum([9, 3, 8]), 3)
           self.assertEqual(getMinimum([-2, -1, -3]), -3)
           self.assertEqual(getMinimum([2, 3, 5, 15]), 2)
           self.assertEqual(getMinimum([32, 64, 28]), 28)
           self.assertEqual(getMinimum([3]), 3)
           
   myTests().main()
       
   
Example: Find the Average of a List of Values
----------------------------------------------
      
Another common thing to do to a list of values is to find the average of them.  To calculate an average first create a variable to hold the sum and set it to zero.  Then loop through all the values in the list and add each one to the sum.  Remember that you can't divide by 0, so if the list is empty return 0 and otherwise return the sum divided by the number of items in the sum (which is the number of items in the list).

The code below also contains tests to make sure that the code works as intended. For example ``getAverage([50,60,70])`` should return 60 and ``getAverage([])`` should return 0.

Click the "Run" button to run the tests that check that this code is working correctly.  All tests should print "Pass".

.. activecode:: Get_Average

   def getAverage(numList):
   
       # initialize the sum
       sum = 0  
      
       # loop through the values
       for num in numList:  
      
           # add the value to the sum
           sum = sum + num 
    
       # prevent a divide by zero if this is called with an empty list
       if len(numList) == 0:
      	   return 0 
       else:
           return sum / len(numList)
      
   from unittest.gui import TestCaseGui

   class myTests(TestCaseGui):

       def testOne(self):
           self.assertEqual(getAverage([50,60,70]),60)
           self.assertEqual(getAverage([]),0)
           self.assertEqual(getAverage([75,60,80,95]),77.5)
           self.assertEqual(getAverage([10,20,30,40,90]),38)
           self.assertEqual(getAverage([4]),4)

   myTests().main()
   
Practice: Find the Average of Every Other Value in a List
-----------------------------------------------------------

The following code should find the average of every other value in a list starting with the value at index 0, but it contains errors.  To find the average of every other value in a list first initialize a sum and count to zero. Next loop through every other index starting at index zero, add the value at each index to the sum, and increment the count.  If the count is zero then return zero and otherwise return the sum divided by the count.

The code below contains code for testing the ``getAverageEveryOther`` function.  For example ``getAverageEveryOther([10,30,90])`` should return 50 since 10 plus 90 is 100 and 100 divided by 2 is 50, and ``getAverageEveryOther([])`` should return 0 since the count would be zero.

Click the "Run" button to run the tests that check that this code is working correctly.  All tests should print "Pass".

.. activecode:: Get_Average_Every_Other

   def getAverageEveryOther(numList):
       sum = 0
       count = 0
       for index in range(0,numList,2):
           value = numList[index]
           sum = value
           count = count + 1
       if count == 0:
           return 0
       else 
       sum / count
           
   from unittest.gui import TestCaseGui

   class myTests(TestCaseGui):

       def testOne(self):
           self.assertEqual(getAverageEveryOther([10,30,90]),50)
           self.assertEqual(getAverageEveryOther([]),0)
           self.assertEqual(getAverageEveryOther([30]),30)
           self.assertEqual(getAverageEveryOther([10,20]),10)
           self.assertEqual(getAverageEveryOther([4, 8, 4, 3]),4)

   myTests().main()
           
   
Practice: Find the Average of a List of Values Without the Minimum Value
-------------------------------------------------------------------------
   
The following code should find the average of a list of values, except it should not include any of the minimum value in the list in the calculation of the average. It should first find the minimum value in the list.  Then it should initialize a sum and count to zero.  Then it should loop through the values in the list and if the current value is equal to the minimum value it should add it to the sum and increment the count.   If the count is zero then it should return zero, otherwise it should return the sum divided by the count. 

The code below contains tests which will check if your code is correct. For example, ``getAverageExceptMinimum([90, 3, 10, 3])`` should return 50 since 90 plus 10 is 100 (ignoring both 3's) and the average is 100 divided by 2 which is 50.  And ``getAverageExceptMinimum([2])`` should return 0 since removing the minimum value means the number of values in the sum is 0 so the average should be 0.  

Fix the errors so that all the tests all print "Pass" when you click the "Run" button.  The error messages and test results are displayed below the code. 
   
.. activecode:: Get_Average_Without_Minimum

   def getAverageExceptMinimum(numList):
   
       min = numList[0
       
       for num in numList:
       
           if num < min:
               num = min
               
       sum = 0  
       count = 1
      
       for num in numList:  
      
           if num != min:
           
               sum = sum + num 
               count = count + 1
    
               if sum == 0:
      	   return 0 
       else:
           return sum / count
      
   from unittest.gui import TestCaseGui

   class myTests(TestCaseGui):

       def testOne(self):
           self.assertEqual(getAverageExceptSmallest([90,3,10,3]),50)
           self.assertEqual(getAverageExceptSmallest([2]),0)
           self.assertEqual(getAverageExceptSmallest([75,60,80,95,20]),77.5)
           self.assertEqual(getAverageExceptSmallest([20,95,20]),95)
           self.assertEqual(getAverageExceptSmallest([2, 5]),5)
           
   myTests().main()
   

   
