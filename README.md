Download Link: https://assignmentchef.com/product/solved-cs-4303-introduction-to-functional-programming-lisp
<br>



This document provides instructions about using Lisp and examples of the design of Lisp functions. For more information about Lisp programming, look at the links in Lisp_sources.html.

<em>TASK 1: Using the LISP interpreter</em>

Install Allegro-Lisp software (https://franz.com/downloads/clp/survey) on your computer. You may explore the features of the software by trying to run simple lisp functions.

Some of the primitive functions allowed in Lisp are listed below. It would be a very good practice if you try these primitive functions on the system.  You may look at the other primitive functions supported by Lisp by looking at any book on common lisp.

EXAMPLE:

<strong>                        LC-USER 1&gt;<em>(</em></strong><em>car ‘(a b c))</em><strong>     &lt;</strong>in<strong>&gt;</strong>

<strong>                        <em>A         </em>                                                &lt;</strong>out<strong>&gt;</strong>

<strong>                        LC-USER 2&gt;<em>(</em></strong><em>eq</em> <em>‘x ‘y)</em><strong>            &lt;</strong>in<strong>&gt;</strong>

<strong>                        <em>NIL     </em>                                                &lt;</strong>out<strong>&gt;</strong>

<strong>                        LC-USER 3&gt;<em>(</em></strong><em>setq</em> <em>x ‘(a b c))</em><strong>             &lt;</strong>in<strong>&gt;</strong>

<strong>                        <em>(A B C)</em></strong>

To learn more about LISP programming, click on the following link:

http://cms.dt.uh.edu/Faculty/LinH/courses/CS4303/LISP/Lisp_sources.html

<em>TASK 2: More practice:</em>

In each of the following questions predict the results first and then use the Lisp interpreter to check your answers:

1. Write down the results of typing the following expressions in Lisp. (one line at a time).

(list ‘big ‘cat ‘sat)

(cons ‘the (list ‘big ‘cat ‘sat))

(list ‘all (list ‘good ‘people) ‘should (list ‘go ‘ahead))

(cdr (car (cdr ‘(a (b c) d))))

(cdadr ‘(a (b c) d))

2. What will be the value of the last expression in each case?




a.         (setq a ‘(u v w))

(set (car (cdr a)) ‘b)

(cons v a)

b.         (setq A ‘A)

(setq B ‘A)

(list A B ‘B)

3. What will be the result of each of the following sets of s-expressions typed in Lisp environment?

a.         (defun double (x) (* 2 x))

(double 2.3)

b.         (defun times-square (x y) (* x y y))

(times-square 4 3)

c.         (defun TIMES-CUBE (X Y) (* X Y Y Y))

(defun CUBE-TIMES (X Y) (TIMES-CUBE Y X))

(CUBE-TIMES 3 2)

Using an editor you may type the above functions in separate files with “lsp” or “.lisp” extension (you may use the editor which comes with Allegro Lisp – under <em>file</em> menu choose <em>new</em> option; write the code; save the program under the name <em>double.lsp</em>).  And then load the program into the Allegro Lisp environment for execution (under <em>file</em> menu choose <em>load</em> option; write the name of the program <em>double.lsp</em> ). After loading the program you may execute any functions within that file using the listener window;

CL-USER 1&gt; <em>(double 5)</em>         ;running the function <em>double</em>

<em>10</em>

4. Evaluate each of the following s-expressions:

a.         (atom ‘3)

b.         (floatp ‘(A B))

c.         (listp ‘(A B))

d.         (not (null ‘nil))

e.         (not (atom ‘(A B)))

f.          (eq ‘a ‘a)

g.         (eq ‘(A B) (list ‘A ‘B))

h.         (eq 3 3.0)

i.          (equal 3 3.0)

j.          (eq 2.3 (+ 1.1 1.2))

k.         (and (atom ‘3) (listp ‘(A B)))

5. Write two different s-expressions to access symbol C for each of the following lists.

a.         (A B C D E)

b.         ((A B C) (D E F))

c.         ((A B) (C D) (E F))

d.         (A (B C D) E F)

6. Write a function DOT-PRODUCT that takes two lists, each list has three numbers (elements), and produces the dot product of the vectors that they represent. For example,

-&gt; (DOT-PRODUCT ‘(1.2 2.0 -0.2) ‘(0.0 2.3 5.0))

-&gt; 3.6

The answer for this question can be found in file <em>DOT-PRODUCT.LSP</em> in the same directory. The key for designing a lisp function is using recursion.

7. Write a function COUNT-NUMBER that counts the number of numbers that occur in a list. It should work like this:

-&gt; (COUNT-NUMBER ‘(A 2.3 B 5 4.53 C F))

-&gt; 3

<strong>Hint</strong>: To determine whether s-expression is a number or not, use <em>numberp</em> function. The following examples show how <em>numberp</em> works:

-&gt; (numberp 5)

-&gt; T

-&gt; (numberp 5.5)

-&gt; T

-&gt; (numberp T)

-&gt; nil

-&gt; (numberp ‘(A B))

-&gt; nil

8. Write a function NEW-LIST that takes a number as its argument and constructs a list of that length containing all Ts. For example,

-&gt; (new-lit 5)

-&gt; (T T T T T)

9. The Lisp function LENGTH counts the number of elements in the top level of a list. Write a function ALL-LENGTH of one argument that counts the number of atoms that occur in a list at all levels.  Thus, the following lists will have the following ALL-LENGTHs.

(A B C)                                   =&gt; 3

((A (B C) D (E F))      =&gt; 6

(NIL NIL (NIL NIL) NIL )    =&gt; 5

Turn in your responses to these questions 6-9 in one single Lisp program file (.lsp or .lisp file)