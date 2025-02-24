Download link :https://programming.engineering/product/eecs205002-linear-algebra-assignment-1-mmm-how-fast-it-can-be/


# EECS205002-Linear-Algebra-Assignment-1-Mmm-How-Fast-It-Can-Be-
EECS205002 Linear Algebra Assignment 1: Mmm, How Fast It Can Be?
Matrix matrix multiplication (Mmm) is one of the fundamental operations in numerical algorithms. Let A, B, and C be three n n matrices, whose elements are denoted as ai;j, bi;j and ci;j respectively for 1 i; j n. Based on the de nition of matrix multiplication C = AB,

n

ci;j =

kX

ai;kbk;j;

(1)

=1

we have the basic matrix multiplication algorithm, as shown below.

Algorithm 1 Matrix-Matrix Multiplication

for i = 1 to n do

for j = 1 to n do

C[i][j] = 0

for j = 1 to n do

C[i][j] = C[i][j] + A[i][k]B[k][j]

end for

end for

end for

This is a three loop algorithm. You can calculate the number of additions is n3 and the number of multiplication is also n3.

Now we consider another type of algorithms, called block matrix multiplica-tion. It is based on the property of block matrices. Let

2A2;1

A2;2

A2;M

3

2B2;1

B2;2

B2;N 3

6

A1;1

A1;2

A1;M

7

6

B1;1

B1;2

B1;N

7

A =

A

...

A

...

...

A

...

; B =

...

...

...

B

...

6

7

6B

B

7

4

N;1

N;2

N;M

5

4

M;1

M;2

M;N

5

6

7

6

7

and

3

C1;1

C1;2

C1;N

C =

6C2…;1

C2...;2

...

C2…;N 7

:

6

C

C

C

7

4

N;1

N;2

N;N

5

6

7


where n = Np = Mq for some integer p and q. And each AI;J is a p q matrix; each BI;J is a q p matrix; and each CI;J is a p p matrix. It can be shown that

M

X

CI;J = AI;KBK;J:

(2)

K=1

Assignments

(20%) Prove the correctness of (2). You can reference textbook Sec 1.6.

(20%) Show the numbers of additions and multiplications of (1) and (2) are the same.

(20%) Implement the block version of matrix multiplication in C.

(20%) Let n = 1024. Try di erent combinations of p and q, and measure their running times.

(20%) Google what is cache memory in computer architecture, and look up the cache size of your computer. Explain the reason of the performance di erences for various p and q.

Submission

Write a report in PDF le that includes the answers of question (1), (2),

(4), and (5). Represent the answer of (4) in a table.

Time(seconds) p = 4 p = 8 p = 16 p = 256

q = 4

q = 8

q = 16

...

q = 256

The code of (3) should be implemented in the le implement.c. It should follow the interface de ned in in matmul.h, and can be compiled together with matmul.c. If the code cannot be correctly compiled or run by TA, you got 0 for (3) and (4).

Zip them and submit.
