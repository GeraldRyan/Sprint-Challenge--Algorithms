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


This is basically a binary search problem- divide and conquer strategy. We want to determine the thresshold floor where eggs break but sacrifice as few eggs to find that out. So start on floor n/2. if breaks, then we know we have to drop from a lower floor. Don't dry one floor down. Changes are that will break too and won't tell us much. Don't start on first floor. Divide and conquer. Start on the floor that is midway between the floor you dropped on the last iteration (n/2/2), so if 10 floors, you dropped from 5th floor and broke, then you drop from the 2.5 floor, the mezzanine, ok round down, or up. Rinse and repeat until it doesn't break. If the if didn't break on floor five (amazing eggs), then try total floors (n=10) minus floor last tried divided by 2 rounded down (n/2/2 = 2.5 or 2) = 8. This is basically binary search. The length of the array gets reduced down through each search and when it is 1 single element, you know that is a hit (if the item exists in the (sorted) array- and if it doesn't exist you still hae your answer, so by reducing the subarray searched to 1, that is the maximum number of iterations a search can take and that array search length is the function n/2^k) where k is the number of iterations. In our example, k1 is n/2, k2 is n/2/2 or n/2^2 and a third would be n/2/2/2 or n/2^3. Symbolic representation is cool. 

so length of array = n/2^k (Max complexity) and so
1 = n/2^k and so 
2^k = n and so 
log(2^k) = log(n) and so
k log(2) = log(n) and so 
log(2) is a constant we can throw out and so 
k is number of operations or the definition of runtime complexity, and so
k = log(n)

log(n) is the runtime complexity. The more floors, the greater the runtime complexity but only in terms of log() where n = number of floors. Graphically this is pretty flat, not very steep, so runtime complexity doesn't increase that much. 

This is logical because if you double your sample or floor building size, you only at most increase the runtime by one operation, because the first run reduces the array by half. If you multiply it by 8, you only add three operations. By 16 only by four operations. 32x by 5. It scales well. 

Array_of_floors = [0, 1, 2,...n]
<!-- Breaking Floor = None -->
test mid floor 
if breaks(Array_of_floors//2):
<!-- does break on lower floors -->
  test if it breaks on half the floors down, slice the array up in half with recursive or iterative
   if no, return array of floors
else if does not break:
   Try half the floors up to the top from current floor. Use iterative or recursive

you need two floors to get right answer confirmed. This is not exactly like a binary search where you can find the number on a given try before k. In this case you have to find the floor it breaks on and the floor lower that it doesn't break on so you have to go to the bitter end of testing but the principles are same

