#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

a)
<!-- ```python
 a = 0
    while (a < n * n * n):
      a = a + n * n
``` -->

The end condition of n increases cubically while a increases squared. I think that n squared factors out and is left with an O(n) complexity.

if n = 2 then while (a < 8):
  a = 0 + 4
  a = 4 + 4
  Two steps and n = 2

if n = 3 then while a < 27:
   a = 0 + 9
   a = 9 + 9 = 18
   a = 18 + 9 + 27
   n steps = 3

if n = 4 then while a < 64
   a = 0 + 16
   a = 16 + 16
  a = 32 + 16
  a = 48 + 16
  n = four steps. 

  Hot dog it's O(n) final answer



b)  
<!-- sum = 0
    for i in range(n):
      j = 1
      while j < n:
        j *= 2
        sum += 1 -->


line 36, for i in range(n) is an O(n) operation but on top of that, for each of these operations we have another n set of operations- like a 2x2 matrix (the matrix is real Neo). Now if they multipled j by n on line 39 then it would 'factor out' but they don't and we can't assume they would. 





c) 
<!-- ```
 def bunnyEars(bunnies):
      if bunnies == 0:
        return 0

      return 2 + bunnyEars(bunnies-1)
``` -->

This is written in recursive. The bunnies arg is an int. Think of it like n. The base case is where bunnies is 0 and the recursion call steps down by one each time. I just realized if it called bunnyEars(bunnies+1) on line 54 then it would never hit base case and would time out or be infinite until electricity was cut.

So the greater the n the more operations, so I want to say O(n). Yes, O(n). stepping down to zero, so n times this is run. 

case in point, bunnies = 3
return 2 + bunnyEars(2) =
return 2 + 2 + bunnyEars(1) = 
return 2 + 2 + 2 + 0
3 lines of code



## Exercise II


<!-- Suppose that you have an n-story building and plenty of eggs. Suppose also that an egg gets broken if it is thrown off floor f or higher, and doesn't get broken if dropped off a floor less than floor f. Devise a strategy to determine the value of f such that the number of dropped + broken eggs is minimized.

Write out your proposed algorithm in plain English or pseudocode AND give the runtime complexity of your solution. -->


