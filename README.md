Download Link: https://assignmentchef.com/product/solved-csci-3104-problem-set-4
<br>
<ol>

 <li>(10 pts) Suppose that we modify the Partition algorithm in QuickSort in such a way that on on every third level of the recursion tree it chooses the worst possible pivot, and on all other levels of the recursion tree Partition chooses the best possible pivot. Write down a recurrence relation for this version of QuickSort and give its asymptotic solution. Then, give a verbal explanation of how this Partition algorithm changes the running time of QuickSort.</li>

 <li>(10 pts) Mr. Ollivander, of Ollivanders wand shop, has hired you as his assistant, to find the most powerful wand in the store. You are given a magical scale which “weighs” wands by how powerful they are (the scale dips lower for the wand which is more powerful). You are given <em>n </em>wands <em>W</em><sub>1</sub><em>,…,W<sub>n</sub></em>, each having distinct levels of power (no two are exactly equal).

  <ul>

   <li>Consider the following algorithm to find the most powerful wand:

    <ol>

     <li>Divide the <em>n </em>wands into pairs of wands.</li>

     <li>Compare each wand with its pair, and retain the more powerful of the two.</li>

    </ol></li>

  </ul></li>

</ol>

<ul>

 <li>Repeat this process until just one wand remains.</li>

</ul>

Illustrate the comparisons that the algorithm will do for the following <em>n </em>= 8 input:

<ul>

 <li>Show that for <em>n </em>wands, the algorithm (2a) uses at most <em>n </em></li>

 <li>Describe an algorithm that uses the results of (2a) to find the <em>second </em>most powerful wand, using at most log<sub>2 </sub><em>n </em>additional comparisons. There is no need for pseudocode; just write out the steps of the algorithm like we have written in (2a). Hint: if you follow sports, especially wrestling, read about the <em>repechage</em>.</li>

 <li>Show the additional comparisons that your algorithm in (2c) will perform for theinput given in (2a).</li>

</ul>

<ol start="3">

 <li>(20 pts) For obtuse historical reasons, Prof. Dumbledore asks his students to line up in ascending order by height in a very tight room with little extra space. Similar to Alex the African Grey parrot (look it up!), the students, being bored, decided to play a little trick on Prof. Dumbledore. They lined up in order by height—<em>almost</em>. They made sure that each person was no more than <em>k </em>positions away from where they were supposed to be (in ascending order), but this allowed them to significantly mess up the precise ordering. Here is an example of an array with this property when <em>k </em>= 2:</li>

</ol>

1

<em>A</em>[0]          <em>A</em>[1]          <em>A</em>[2]          <em>A</em>[3]          <em>A</em>[4]          <em>A</em>[5]

Original Array:             1                     4 i 2                     3                   15b<u><sub>&lt; </sub></u>5

O

Sorted Array:               1               2               3

) 4                                            5 <u><sup>|</sup></u>” 15

<ul>

 <li>Write down pseudocode for an algorithm that would sort such an array in place—so it fits in the tight room—in time <em>O</em>(<em>nk </em>log<em>k</em>). Your algorithm can use a function sort(<em>A,`,r</em>) that sorts the subarray <em>A</em>[<em>`</em>]<em>,…,A</em>[<em>r</em>] in place in <em>O</em>((<em>r</em>−<em>`</em>)log(<em>r</em>−<em>`</em>)) steps (assuming <em>r &gt; `</em>).</li>

 <li>Suppose you are given to an auxiliary room which can fit <em>k </em>+ 1 students. Modify your previous algorithm to sort the given array in time <em>O</em>(<em>nk</em>).</li>

 <li>With the same extra room as in the previous part, modify heap sort using a binarymin heap of size <em>k </em>+ 1 to sort the given array in time <em>O</em>(<em>n</em>log<em>k</em>).</li>

 <li>(5 pts extra credit) Include the correct story about Alex, with proper citation. Ifyou wish, you may copy this story verbatim, but must indicate clearly that you have done so and, of course, still cite your source.</li>

</ul>

<ol start="4">

 <li>(20 pts) Consider the following strategy for choosing a pivot element for the Partition subroutine of QuickSort, applied to an array <em>A</em>.

  <ul>

   <li>Let <em>n </em>be the number of elements of the array <em>A</em>.</li>

   <li>If <em>n </em>≤ 24, perform an Insertion Sort of <em>A </em>and return.</li>

   <li>Otherwise:

    <ul>

     <li>Choose 2b<em>n</em><sup>(1<em>/</em>3)</sup>c elements at random from <em>n</em>; let <em>S </em>be the new list with the chosen elements.</li>

     <li>Sort the list <em>S </em>using Insertion Sort and use the median <em>m </em>of <em>S </em>as a pivot element.</li>

     <li>Partition using <em>m </em>as a pivot.</li>

     <li>Carry out QuickSort recursively on the two parts.</li>

    </ul></li>

   <li>How much time does it take to sort <em>S </em>and find its median? Give a Θ bound.</li>

   <li>If the element <em>m </em>obtained as the median of <em>S </em>is used as the pivot, what can we say about the sizes of the two partitions of the array <em>A</em>?</li>

  </ul></li>

</ol>

2

<ul>

 <li>Write a recurrence relation for the worst case running time of QuickSort with thispivoting strategy.</li>

</ul>

<ol start="5">

 <li>(20 pts extra credit) Recall that the <em>Insertion Sort </em>algorithm (Chapter 2.1 of CLRS) is an in-place sorting algorithm that takes Θ(<em>n</em><sup>2</sup>) time and Θ(<em>n</em>) space. In this problem, you will learn how to <em>instrument </em>your code and how to perform a numerical experiment that verifies the asymptotic analysis of Insertion Sort’s running time. There are two functions and one experiment to do this.

  <ul>

   <li>InsertionSort(A,n) takes as input an unordered array <em>A</em>, of length <em>n</em>, and returns both an in-place sorted version of <em>A </em>and a count <em>t </em>of the number of atomic operations performed by InsertionSort.</li>

  </ul></li>

</ol>

Recall: atomic operations include mathematical operations like −, +, ∗, and <em>/</em>, assignment operations like ← and =, comparison operations like <em>&lt;</em>, <em>&gt;</em>, and ==, and RAM indexing or referencing operations like [].

<ul>

 <li>randomArray(n) takes as input an integer <em>n </em>and returns an array <em>A </em>such that for each 0 ≤ <em>i &lt; n</em>, <em>A</em>[<em>i</em>] is a uniformly random integer between 1 and <em>n</em>. (It is okay if <em>A </em>is a random permutation of the first <em>n </em>positive integers; see the end of Chapter 5.3.)</li>

 <li>From scratch, implement the functions InsertionSort and randomArray. You may not use any library functions that make their implementation trivial. You may use a library function that implements a pseudorandom number generator in order to implement randomArray.</li>

</ul>

Submit a paragraph that explains how you instrumented InsertionSort, i.e., explain which operations you counted and why these are the correct ones to count.

Hint: your instrument code should only count the operations of the InsertionSort algorithm and not the operations of the instrument code you added to it.

<ul>

 <li>For each of , run InsertionSort(randomArray(n),n) fives times and record the tuple (<em>n,</em>h<em>t</em>i), where h<em>t</em>i is the average number of operations your function counted over the five repetitions. Use whatever software you like to make a line plot of these 12 data points; overlay on your data a function of the form <em>T</em>(<em>n</em>) = <em>An</em><sup>2</sup>, where you choose the constant <em>A </em>so that the function is close to your data.</li>

</ul>

Hint: To increase the aesthetics, use a log-log plot.

3