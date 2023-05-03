Download Link: https://assignmentchef.com/product/solved-cs-201-data-structures-library-phase-1
<br>



For phase 1 of the CS201 programming project, we will start with a circular dynamic array class and extend it to implement some of the algorithms discussed in class.

Your dynamic array class should be called CDA for circular dynamic array. The CDA class should manage the storage of an array that can grow and shrink.  The class should be implemented using C++ templates.  As items are added and removed from both the front and the end of the array, the items will always be referenced using indices 0…size-1.  Your CDA class should include a flag indicating whether the array is in sorted in increasing order, or it is unordered.

<table width="619">

 <tbody>

  <tr>

   <td colspan="2" width="619">The only include files that should be necessary for the CDA class would be related to generating random</td>

  </tr>

  <tr>

   <td width="134">values for Quickselect.</td>

   <td width="485"> </td>

  </tr>

 </tbody>

</table>

The public methods of your class should include the following (elmtype indicates the type from the template):

<table width="623">

 <tbody>

  <tr>

   <td colspan="3" width="182">Function</td>

   <td colspan="7" width="345">Description</td>

   <td width="96">Runtime</td>

  </tr>

  <tr>

   <td colspan="3" width="182">CDA();</td>

   <td colspan="7" width="345">Default Constructor. The array should be of capacity 1, size 0 and ordered is false.</td>

   <td width="96">O(1)</td>

  </tr>

  <tr>

   <td colspan="3" width="182">CDA(int s);</td>

   <td colspan="7" width="345">For this constructor the array should be of <strong>capacity</strong> and <strong>size</strong> s with ordered = false.</td>

   <td width="96">O(1)</td>

  </tr>

  <tr>

   <td colspan="3" width="182">~CDA();</td>

   <td colspan="7" width="345">Destructor for the class.</td>

   <td width="96">O(1)</td>

  </tr>

  <tr>

   <td colspan="3" rowspan="2" width="182">elmtype&amp; operator[](int i);</td>

   <td colspan="7" width="345">Traditional [] operator. Should print a message if i is out of bounds and return a reference to value of type elmtype stored in the class for this purpose<span style="text-decoration: line-through">.  If the</span> <span style="text-decoration: line-through">ordered flag is true, verify that any change in the array</span> <span style="text-decoration: line-through">leaves it still ordered.  If necessary set the ordered flag</span></td>

   <td rowspan="2" width="96">O(1)</td>

  </tr>

  <tr>

   <td colspan="2" width="58"><span style="text-decoration: line-through">to false. </span></td>

   <td colspan="2" width="111">Removed this test.</td>

   <td colspan="3" width="176"> </td>

  </tr>

  <tr>

   <td colspan="3" width="182">void AddEnd(elmtype v);</td>

   <td colspan="7" width="345">increases the size of the array by 1 and stores v at the end of the array. Should double the capacity when the new element doesn’t fit.  If ordered is true, check to be sure that the array is still in order.</td>

   <td width="96">O(1) amortized</td>

  </tr>

  <tr>

   <td colspan="3" width="182">void AddFront(elmtype v);</td>

   <td colspan="7" width="345">increases the size of the array by 1 and stores v at the beginning of the array. Should double the capacity when the new element doesn’t fit. The new element should be the item returned at index 0.  If ordered is true, check to be sure that the array is still in order.</td>

   <td width="96">O(1) amortized</td>

  </tr>

  <tr>

   <td colspan="3" width="182">void DelEnd();</td>

   <td colspan="7" width="345">reduces the size of the array by 1 at the end. Should shrink the capacity when only 25% of the array is in use after the delete. The capacity should never go below 1.</td>

   <td width="96">O(1) amortized</td>

  </tr>

  <tr>

   <td colspan="3" width="182">void DelFront();</td>

   <td colspan="7" width="345">reduces the size of the array by 1 at the beginning of the array. Should shrink the capacity when only 25% of the array is in use after the delete. The capacity should never go below 1.</td>

   <td width="96">O(1) amortized</td>

  </tr>

  <tr>

   <td colspan="3" width="182">int Length();</td>

   <td colspan="7" width="345">returns the size of the array.</td>

   <td width="96">O(1)</td>

  </tr>

  <tr>

   <td colspan="3" width="182">int Capacity();</td>

   <td colspan="7" width="345">returns the capacity of the array.</td>

   <td width="96">O(1)</td>

  </tr>

  <tr>

   <td rowspan="2" width="7"> </td>

   <td width="26">void</td>

   <td rowspan="2" width="149"> Clear();</td>

   <td colspan="6" rowspan="2" width="333">Frees any space currently used and starts over with an array of capacity 1 and size 0.</td>

   <td rowspan="2" width="12"> </td>

   <td rowspan="2" width="96">O(1)</td>

  </tr>

  <tr>

   <td width="26"> </td>

  </tr>

  <tr>

   <td colspan="3" width="182">bool Ordered();</td>

   <td colspan="6" width="333">Returns the status of the ordered flag.</td>

   <td width="12"> </td>

   <td width="96">O(1)</td>

  </tr>

  <tr>

   <td colspan="3" width="182">int SetOrdered();</td>

   <td colspan="6" width="333">Check to see if the array is in order.  Set the order flag appropriately.  Return 1 if the array was ordered and otherwise.</td>

   <td width="12">1</td>

   <td width="96">O(size)</td>

  </tr>

  <tr>

   <td colspan="3" width="182">Elmtype Select(int k);</td>

   <td colspan="6" width="333">returns the k<sup>th</sup> smallest element in the array.  If ordered is true then return the item at index k-1.  Otherwise use the quickselect algorithm. Quickselect should choose a random partition element.</td>

   <td width="12"> </td>

   <td width="96">O(1) or O(size) expected</td>

  </tr>

  <tr>

   <td colspan="3" width="182">Void InsertionSort()</td>

   <td colspan="6" width="333">Performs insertion sort on the array.  Sets ordered to true.</td>

   <td width="12"> </td>

   <td width="96">O(size*size) worst case</td>

  </tr>

  <tr>

   <td colspan="3" width="182">void QuickSort();</td>

   <td colspan="6" width="333">Sorts the values in the array using the quick sort algorithm.  This should pick the partition value using the median of three technique.  Set ordered to true. Should also make use of insertion sort to improve performance.</td>

   <td width="12"> </td>

   <td width="96">O(size * size) worst caseO(size lg size) expected</td>

  </tr>

  <tr>

   <td colspan="3" rowspan="3" width="182">void CountingSort(int m);</td>

   <td colspan="6" width="333">Sorts the values in the array using counting sort, wher the values in the array are in the range 0…m.  Set</td>

   <td rowspan="3" width="12">e </td>

   <td rowspan="3" width="96">O(size * m)</td>

  </tr>

  <tr>

   <td colspan="3" width="110">ordered to true.</td>

   <td colspan="3" width="224"> You may assume that all values in the</td>

  </tr>

  <tr>

   <td width="7"> </td>

   <td colspan="4" width="217">array are integers in the range 0…m.</td>

   <td width="109"> </td>

  </tr>

  <tr>

   <td colspan="3" width="182">int Search(elmtype e)</td>

   <td colspan="6" width="333">If ordered is true, perform a binary search of the array looking for the item e.  Otherwise perform linear search.  Returns the index of the item if found or -1 otherwise.</td>

   <td width="12"> </td>

   <td width="96">O(lg size) orO(size) </td>

  </tr>

  <tr>

   <td width="7"></td>

   <td width="26"></td>

   <td width="149"></td>

   <td width="7"></td>

   <td width="51"></td>

   <td width="51"></td>

   <td width="60"></td>

   <td width="55"></td>

   <td width="109"></td>

   <td width="12"></td>

   <td width="96"></td>

  </tr>

 </tbody>

</table>




Your class should include proper memory management, including a destructor, a copy constructor, and a copy assignment operator.

<table width="609">

 <tbody>

  <tr>

   <td colspan="3" width="609">For submission, all the class code should be in a file named CDA.cpp.  Create a makefile for the project</td>

  </tr>

  <tr>

   <td colspan="3" width="609">that compiles the file phase1main.cpp and creates an executable named phase1.  A sample makefile is</td>

  </tr>

  <tr>

   <td colspan="2" width="559">available on Blackboard.  Place both CDA.cpp and makefile into a zip file and upload the file to</td>

   <td rowspan="2" width="50"> </td>

  </tr>

  <tr>

   <td width="70">Blackboard.</td>

   <td width="489"> </td>

  </tr>

  <tr>

   <td width="70"></td>

   <td width="489"></td>

   <td width="50"></td>

  </tr>

 </tbody>

</table>

<table width="567">

 <tbody>

  <tr>

   <td colspan="2" width="567">No late submissions will be accepted.  There will be an opportunity to resubmit by February 18.</td>

  </tr>

  <tr>

   <td width="258">Resubmissions will have a 20 point penalty.</td>

   <td width="309"> </td>

  </tr>

 </tbody>

</table>

☐ Create your CDA class

☐ Modify the makefile to work for your code (changing compiler flags is all that is necessary)

☐   Test your CDA class with the sample main provided on the cs-intro server

☐   Make sure your executable is named phase1

☐   Develop additional test cases with different types, and larger arrays

☐   Create the zip file with CDA.cpp and makefile

☐   Upload your zip file to Blackboard


