Download Link: https://assignmentchef.com/product/solved-comp352-assignment4-cvr
<br>
Assume a hash table utilizes an array of 13 elements and that collisions are handled by separate chaining. Considering the hash function is defined as: <em>h(k)=k mod 13</em>.

<ol start="48">

 <li>Draw the contents of the table after inserting elements with the following keys: 32, 147, 265, 195, 207, 180, 21, 16, 189, 202, 91, 94, 162, 75, 37, 77, 81, 48.</li>

 <li>What is the maximum number of collisions caused by the above insertions?</li>

</ol>

<h1>Question 2</h1>

To reduce the maximum number of collisions in the hash table described in Question 1 above, someone proposed the use of a larger array of 15 elements (that is roughly 15% bigger) and of course modifying the hash function to:  <em>h(k)=k mod 15</em>. The idea is to reduce the <em>load factor</em> and hence the number of collisions.

Does this proposal hold any validity to it? If yes, indicate why such modifications would actually reduce the number of collisions. If no, indicate clearly the reasons you believe/think that such proposal is senseless.

<h1>Question 3</h1>

Assume an <em>open addressing</em> hash table implementation, where the size of the array is <em>N</em> = 19, and that <em>double hashing</em> is performed for collision handling. The second hash function is defined as:  <em>                                                      d(k) = q – k mod q, </em>

where <em>k</em> is the key being inserted in the table and the prime number <em>q</em> is = 7. Use simple modular operation (<em>k mod N</em>) for the first hash function.

<ol>

 <li>Show the content of the table after performing the following operations, in order: <strong>put(25), put(12), put(42), put(31), put(35), put(39), remove(31), put(48), remove(25), </strong><strong>put(18), put(29), put(29), put(35).</strong></li>

 <li>What is the size of the longest cluster caused by the above insertions? iii) What is the number of occurred collisions as a result of the above operations? iv)            What is the current value of the table’s <em>load factor</em>?</li>

</ol>

<strong> </strong>

<strong><u>Question 4</u></strong> Given the following tree, which is assumed to be an AVL tree:

<ol>

 <li>i) Are there any errors with the tree as shown? If so, indicate what the error(s) are, correct these error(s) [you should attempt applying the smallest possible number of changes to correct the tree], show the corrected AVL tree, then proceed to the following questions (Questions ii to iv) and <u>start with the tree</u> <u>that you have just corrected</u>. If no errors are there in the above tree, indicate why the tree is correctly an AVL tree, then proceed to the following questions (Questions ii to iv) and <u>continue working on the</u> <u>tree as shown above</u>. ii) Show the AVL tree after <strong><em>put(74)</em></strong> operation is performed. Give the complexity of this operation in terms of Big-O notation.</li>

</ol>

<ul>

 <li>Show the AVL tree after <strong><em>remove(62)</em></strong> is performed. Give the complexity of this operation in terms of Big-O notation.</li>

</ul>

<ol>

 <li>Show the AVL tree after <strong><em>remove(93)</em></strong> is performed. <u>Show the progress of your work step-by-step</u>. Give the complexity of this operation in terms of Big-O notation.</li>

</ol>

<h1>Question 5</h1>

Show the steps that a radix sort takes when sorting the following array of integer keys:

832   91   411   172   243   573   326   292   682   489   96

<strong><u>Part 2: Programming Question </u></strong>

CARFAX, is a commercial service that supplies vehicle history reports to individuals and businesses on used cars and light trucks for the American and Canadian consumers. It keeps records of all Vehicle Identification Number (VIN). Where each VIN is unique and consists of alphanumeric characters (e.g. 4DUSR6IQ8LN209176). The composition of Vehicle Identification Number is unique for each vehicle with maximum length is restricted to 17 alphanumeric characters.  CARFAX has some lists that are local for cities and areas, where <em>n </em>counts a few hundred properties. Others are at the provincial/ state level, that is <em>n </em>counts tens of thousands or more, or even at country levels, that is <em>n </em>counts millions or more. Furthermore, it is important to have access to the vehicle history. Such a historical record for a Vehicle Identification Number should be kept in reverse chronological order (i.e.  from most recent)

CARFAX, needs your help to design a Customized “Vehicle history Report listing” data structure called CVR. Keys of CVR entries are vehicle identification numbers, that are strings composed of 10-17 alphanumeric characters, and one can retrieve the key of a CVR or access a single element by its key. Furthermore, similar to sequences, given a vehicle identification number in a CVR one can access its predecessor or successor (if it exists).

CVR adapts to its usage and keeps the balance between memory and runtime requirements. For instance, if a CVR contains only a small number of entries (e.g., few hundreds), it might use less memory overhead but slower (sorting) algorithms. On the other hand, if the number of contained entries is large (greater than 1000 or even in the range of tens of thousands of elements or more), it might have a higher memory requirement but faster (sorting) algorithms. CVR might be almost constant in size or might grow and/or shrink dynamically. Ideally, operations applicable to a single CVR entry should be between O (1) and O (log n) but never worse than O(n). Operations applicable to a complete CVR should not exceed O(n<sup>2</sup>).

You are asked to <strong>design </strong>and <strong>implement </strong>CVR, a customized data structure which automatically adapts to the dynamic content that it operates on. In other words, it accepts the size (total number of Vehicle Identification Number) as a parameter and uses an appropriate (set of) data structure(s) from the one(s) studied in class in order to perform the operations below efficiently<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a>.

The CVR must implement the following methods:

<ul>

 <li><strong>setThreshold(Threshold)</strong>: where 100 ≤ Threshold ≤ ~900,000 is an integer number that defines when a listing should be implemented with a data structure such as a Tree,</li>

</ul>

Hash Table, AVL tree, binary tree, if its size is greater than or equal to value of Threshold. Otherwise it is implemented as a Sequence.

<ul>

 <li><strong>setKeyLength(Length)</strong>: where 10 ≤ Length ≤ 17 is an integer number that defines the fixed string length of keys.</li>

 <li><strong>generate(n)</strong>: randomly generates a sequence containing n new non-existing keys of alphanumeric characters.</li>

 <li><strong>allKeys()</strong>: return all keys as a <strong>sorted sequence (lexicographic order) </strong></li>

 <li><strong>add(key,value<sup>2</sup>)</strong>: add an entry for the given key and value</li>

 <li><strong>remove(key)</strong>: remove the entry for the given key</li>

 <li><strong>getValues(key)</strong>: return the values of the given key <strong>nextKey(key)</strong>: return the key for the successor of key.</li>

 <li><strong>prevKey(key)</strong>: return the key for the predecessor of key</li>

 <li><strong>prevAccids(key)</strong>: returns a sequence (sorted in reverse chronological order) of accidents(previously) registered with the given key (dates).</li>

</ul>

<ol>

 <li>Write the pseudo code for each of the methods above.</li>

 <li>Write the Java code that implements the methods above.</li>

 <li>Discuss how both the time and space complexity change for each of the methods above if the underlying structure of your CVR is an array or a linked list?</li>

</ol>

You have to submit the following deliverables:

<ol>

 <li>A detailed report about your design decisions and specification of your CVR ADT including a rationale and comments about assumptions and semantics.</li>

 <li>Well-formatted and documented Java source code and the corresponding class files with the implemented algorithms.</li>

 <li>Demonstrate the functionality of your CVR by documenting at least 10 different but representative data sets. These examples should demonstrate all cases of your CVR ADT functionality (e.<strong>, all operations of your ADT for different sizes).</strong></li>

</ol>

<ul>

 <li>Create <strong>one </strong>zip file, containing the necessary files (.java, .doc, .html, etc.). Please name your file following this convention: If the work is done by 1 student: Your file should be called <em>a#_studentID</em>, where # is the number of the assignment <em>studentID </em>is your student ID number.</li>

</ul>

If the work is done by 2 students: The zip file should be called <em>a#_studentID1_studentID2</em>, where <em># </em>is the number of the assignment, and <em>studentID1 </em>and <em>studentID2 </em>are the ID numbers of each student.

<ul>

 <li>If working in a group, only one of the team members can submit the programming part. Do not upload 2 copies.</li>

</ul>

<strong><u>Very Important:</u></strong> Again, the assignment must be submitted in the right folder of the assignments. Depending on your section, you will either upload to EAS or to Moodle (your instructor will indicate which one to use). <strong>Assignments uploaded to an incorrect folder will not be marked and result in a zero mark. No resubmissions will be allowed. </strong>

ð Additionally, for the programming part of the assignment, an<strong> online demo</strong> <strong>maybe</strong> required (please refer to the courser outline for full details). In such case, the markers will inform you about the demo times and how it will take place online. <strong>If an online demo is required, please notice that failing to demo your assignment will result in zero mark regardless of your submission.</strong> If working in a team, both members of the team must be present during the online demo time. More details on these online demos will be provided to you around the due date of the assignment. <strong> </strong>

<a href="#_ftnref1" name="_ftn1">[1]</a> The lower the memory and runtime requirements of the ADT and its operations, the better will be your grades. <sup>2</sup> Value here could be any feature of the vehicle’s report.