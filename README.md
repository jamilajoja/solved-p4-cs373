Download Link: https://assignmentchef.com/product/solved-p4-cs373
<br>



Construct a PDA that accepts { x#y | x, y in {0, 1}* such that x ≠ y and x<sub>i</sub> = y<sub>i</sub> for some i, 1 ≤ i ≤ min(|x|, |y|) }.

For your PDA to work correctly it will need to be non-deterministic. You can assume that you will always be given a valid string – that is, the input will always contain one # and x and y will be strings over {0, 1}. My PDA has 31 states and and is broken into two major sections, one for |x| = |y| and one for |x| ≠ |y|.

For the case where we assume that |x| = |y|, you need to find a symbol that matches at the same index of x and y (x<sub>i</sub> = y<sub>i</sub> for some i) and a symbol that does not match at the same index of x and y (x<sub>j</sub> ≠ y<sub>j</sub> for some j). One way that this can be accomplished is by finding an index i such that x<sub>i</sub> = y<sub>i</sub> and x<sub>i+1</sub> ≠ y<sub>i+1</sub> or x<sub>i+1</sub> = y<sub>i+1</sub> and x<sub>i</sub> ≠ y<sub>i</sub>. As in programming assignment 3, you can store the index in the stack and the values of x<sub>i</sub> and x<sub>i+1</sub> in the state.

For the case where we assume that |x| ≠ |y|, you need to find an index i where x<sub>i</sub> = y<sub>i</sub>. Since the lengths are different, we get that x ≠ y without finding an index j in which x<sub>j</sub> ≠ y<sub>j</sub>. For this case, you can simple check that x<sub>1</sub> = y<sub>1</sub> and verify that |x| ≠ |y|. If x<sub>1</sub> ≠ y<sub>1</sub>, then the other portion of the code (where we assume that |x| = |y|) will accept the string.

Your PDA will need to be able to handle input strings of length up to about 80 symbols using at most 1GB of memory. My PDA can handle all the test strings with the default 64MB of memory that is allocated to the heap.

You should be able to use the concepts learned for programming assignment 3 to assist you in constructing this PDA.

If you are having memory issues, try starting JFLAP from the command line allocating more memory. As an example, from the directory that JFLAP is in, enter “java -Xmx500m -classpath JFLAP.jar JFLAP”. The -Xmx500m tells java to allocate 500MB of memory to the heap. By default, java only allocates 64MB to the heap.




For this programming assignment, and the remainder of them for the semester, you need to follow my submission directions – filename (lower case last name followed by “_p4.jff” or “_p4.jflap”) and e-mail subject (“CS 373 program 4”). As with programming assignment 3, you can use JFLAP version 8 if you want to.