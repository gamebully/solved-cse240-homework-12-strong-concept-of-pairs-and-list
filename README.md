Download Link: https://assignmentchef.com/product/solved-cse240-homework-12-strong-concept-of-pairs-and-list
<br>
Introduction

The aim of this assignment is to make sure that you understand and are familiar with the concepts covered in the lectures.  By the end of the assignment, you should have ● strong concept of functional paradigm.

<ul>

 <li>strong concept of pairs and list.</li>

 <li>understood the use of let-form and unnamed procedure.</li>

 <li>applied recursion to solve complex problems.</li>

</ul>




<strong>Reading</strong>: chapter 4 and course notes (slides).

You are expected to do the majority of the assignment outside the class meetings.   Should you need assistance, or have questions about the assignment, please contact the instructor or the TA during their office hours.

<strong>Preparation</strong>: Complete the <strong>multiple choice questions</strong> in the textbook exercise section. The answer keys can be found in the course Web site. These exercises can help you prepare for your weekly quiz and the exam. You are encourage to read the other exercise questions and make sure you understand these questions in the textbook exercise section, which can help you better understand what materials are expected to understand after the lectures and homework on each chapter.

You are expected to do the majority of the assignment outside the class meetings.   Should you need assistance, or have questions about the assignment, please contact the instructor or the TA during their office hours.

You are encouraged to ask and answer questions on the course discussion board.  (However, <strong>do not share your answers</strong> in the course discussion board.)

Practice Exercises (no submission required)

<ul>

 <li>What is the major difference between a while-loop and a recursive procedure? What is tailrecursion?</li>

 <li>What are the major steps of developing a recursive procedure?</li>

 <li>Given the following Scheme program:</li>

 <li>Given the following program:</li>

</ul>




<em>(define mymax1 (lambda (lst) </em>

<em>                (if (= (length lst) 1) </em>

<em>                    (car lst) </em>

<em>                    (let ((m (mymax1 (cdr lst)))) </em>

<em>                      (if (&gt; (car lst) m)                           (car lst)                           m))) </em>

<em>)) </em>

<ul>

 <li>Add a procedure to handle the case of empty list, that is, if the given list is empty, the program should return “error: list empty”.</li>

 <li>Describe the four design steps used to solve the recursive problem and give the solution obtained in each step.</li>

 <li>Compare and contrast the algorithm (approach) used in this program and the divide-andconquer algorithm.</li>

 <li>Use C to re implement the program.</li>

</ul>

<ul>

 <li>Follow the four design steps to solve each of the following recursive problems, using Scheme and using C, respectively.

  <ul>

   <li>Count the number of the elements in a list</li>

   <li>Sum a list</li>

   <li>Reverse a list</li>

  </ul></li>

 <li>For each recursive procedure you write, describe the four design steps that you use to solve the recursive problem and give the solution obtained in each step.</li>

 <li>Fibonacci Numbers are defined by</li>

</ul>




Follow the four design steps to write a recursive procedure to implement the function

<ul>

 <li>Define the size-n problem</li>

 <li>Define the stopping conditions and the return values.</li>

 <li>Define the size-m problems</li>

 <li>Construct the size-n solution from the hypothetic size-m solutions.</li>

 <li>Give the complete procedure that computes Fibonacci Numbers for any given integer n &gt;= 0.</li>

</ul>




<h1>Programming Exercise</h1>

Logic gates and adder are basic components of building a processor. All high-level language programs will be translated into instructions that can be executed on these basic components. The correctness and performance of these components are extremely important.

A computer system consists of hardware and software. Before we implement a hardware component, the design is normally simulated by a program first, so that we can verify its correctness and evaluate its performance. In this project, you will write Scheme programs to simulate an n-bit Adder.

If you did not take CSE/EEE120, or CSE/EEE230 and are not familiar with logic gates, you can ignore the physical meaning of the components. Simply consider each component as a pure math/logic function that does something, and you are asked to combine a more complex function using a few simpler functions in a specific way.

<ul>

 <li>Write three Scheme procedures to simulate these three gates: AND, OR, and NOT, shown in the diagram in Figure 1. Test your procedures using all possible input combinations. Hint: Lecture slides showed the implementation of a not-gate in Scheme. (3 points)</li>

</ul>




Figure 1. Logic gates AND, OR, and NOT

The test cases and expected outputs are given in the code template file hw12.rkt. Do not remove or edit these lines.

<ul>

 <li>Write a Scheme procedure to simulate the XOR gate, shown in the diagram in Figure 2.</li>

</ul>

You must use AND, OR, and NOT gates that you defined in question 1 to implement XOR. In infix notation, c = ((NOT a) AND b) OR (a AND (Not b)))             (2 points)




Figure 2. Logic gate XOR, where c = ((NOT a) AND b) OR (a AND (Not b)))

<ul>

 <li>Define Scheme procedures to simulate the logic design given in the diagram in Figure 3. The procedures must follow the design in Figure and call the gate procedures that you defined in the previous questions and must return a <strong>pair</strong> with two elements <sub>‘(c . s)</sub>, where <sub>s</sub> is the binary sum of <sub>a, b, and x</sub>, while <sub>c</sub> is the carry-out. You will implement the procedure in three steps using three procedures, as listed below.

  <ul>

   <li>Write a procedure (halfAdder x a b) to generate (return) the sum bit s. The upper half of</li>

  </ul></li>

</ul>

Fig. 3                                                                                                                           (5 points)

<ul>

 <li>Write a procedure (carry-out x a b) to generate (return) the carryOut bit c. The lower half of</li>

</ul>

Fig. 3                                                                                                                           (5 points)

<ul>

 <li>Write a procedure (fullAdder x a b) to generate the pair output (c . s), where s is the output of the halfAdder procedure and c is the output of the carry-out procedure. The fullAdder is also called a one-bit adder. (5 points)</li>

</ul>




Figure 3. The logic design of a one-bit full adder

Verify your procedure by exhaustive testing: Use all valid inputs to test the procedure. There are eight valid inputs:

(fullAdder 0 0 0)

(fullAdder 0 0 1)

(fullAdder 0 1 0)

(fullAdder 0 1 1)

(fullAdder 1 0 0)

(fullAdder 1 0 1)

(fullAdder 1 1 0)

(fullAdder 1 1 1)

The test cases and expected outputs are given in the code template file hw12.rkt. Do not remove or edit these lines.

<ul>

 <li>The diagram in Figure 4 shows the design of an n-bit adder using n one-bit full adders, where n = 32 in the diagram. The carryOut of bit-i is the carryIn of bit i+1, where the carryIn of bit 0 is 0. The procedure should have three parameters: A, B, and n, where A and B are two lists representing two binary inputs numbers, and n is the length of A and B: <em>(nbit-adder A B n)</em>. Two solutions are acceptable: (1) Follow the design in Figure 4, or (2) follow the binary addition algorithm given in the lecture slides. In both case, you must call at least one of the procedures that you defined in Question 3. You may define one or more helper procedures.</li>

</ul>




<img decoding="async" data-recalc-dims="1" data-src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2020/05/280.png?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

 <noscript>

  <img decoding="async" src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2020/05/280.png?w=980&amp;ssl=1" data-recalc-dims="1">

 </noscript>




Figure 4. The design of a 32-bit adder

<ul>

 <li>Define a procedure (tail lst), which returns the last element of lst.      (4 points)</li>

 <li>Define a procedure (rmtail lst), which returns the list without the last element of lst. For example, (rmtail (1 3 5 6 8)) should return (1 3 5 6). (4 points)</li>

 <li>Follow the fantastic-four abstract approach to design your recursive solution to implement the diagram in Figure 4. You must also explain: (4 points)

  <ul>

   <li>What is the size-n problem of your procedure?</li>

   <li>What are the stopping condition and its return value?</li>

   <li>What is the size-(n-1) problem?</li>

   <li>What are the steps to construct the size-n problem solution from the size-(n-1) solution.       Write the answers as comments in the program.</li>

  </ul></li>

 <li>Following the fantastic-four steps that you have designed in the previous question, implement the n-bit adder, and design a test plan to test the program. (18 points)</li>

</ul>

Note: your (n-bit-adder A B n) should call a recursive procedure, e.g., (recursiveAdd A B c), where c is a carry. You can follow the lecture slides to write these two procedures. However, you cannot use (quotient t 2) and (remainder t 2). Instead, you must call your (fulladder (tail A) (tail B) c). You can use (car (fulladder (tail A) (tail B) c)) and (cdr (fulladder (tail A) (tail B) c)) to obtain the sum and carry, respectively.

Test your program using the given test cases and make sure they generate the output matching with the expected output.

In the output, the left-most element is the carry-out of the n-bit adder. If the carry-out is 1, it represents an overflow in the adder. The remaining elements of the list are the sum