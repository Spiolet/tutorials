# CSES Sum of two values tutorial
Problem link https://cses.fi/problemset/task/1640/

# Problem description
This problem wants us to solve the 2 distinct numbers in an array with x as their sum.

# Problem
```
You are given an array of n integers, and your task is to find two values (at distinct positions) whose sum is x.
Input
The first input line has two integers n and x: the array size and the target sum.
The second line has n integers a_1,a_2,\dots,a_n: the array values.
Output
Print two integers: the positions of the values. If there are several solutions, you may print any of them. If there are no solutions, print IMPOSSIBLE.
Constraints

Example
Input:
4 8
2 7 5 1

Output:
2 4
```
# Solution 1, nested for loops
## Logic
Here, we have 2 solutions, one using nested loops, and the other using a while loop.


## Code
```py
n,x=[int(a) for a in input().split(' ')]
a=[int(b) for b in input().split(' ')]
for i in range(0, n-1):
    for j in range(i+1, n):
        if a[i]+a[j]==x:
            print(i+1, j+1)
            exit()
print('IMPOSSIBLE')
```
## Important parts and explenation
```py
if a[i]+a[j]==x:
    print(i+1, j+1)
    exit()
```
The inner layer of nested loops, the if statement.

Here, the if statement states that if a's ith value plus a's jth value is equal to the value of the variable x, then it will print the one more than the index of the two values each, because the index starts counting at 0, so then when we add 1, then it will be easier for the human to recognise.

Time complexity O(n^2)

## Solution 2 brute force, but with while loop
## Logic
With a while loop, we have 2 variables p, and q, edging in from the 2 ends
```py
n,x=[int(a) for a in input().split(' ')]
a=[int(b) for b in input().split(' ')]
b=[]
for i in range(n):
    b.append((a[i], i+1))
b=sorted(b)

p=0
q=n-1
while p<q:
    if b[q][0]+b[p][0]==x:
        print(b[p][1], b[q][1])
        exit()
    elif b[q][0]+b[p][0]>x:
        q-=1
    else:
        p+=1
print('IMPOSSIBLE')
```
## Explenation

when the 2 variable both get to the middle, and there is no solution, it prints IMPOSSIBLE, but if there is a solution, it prints out the solution.

### Important parts
```py
while p<q:
    if b[q][0]+b[p][0]==x:
        print(b[p][1], b[q][1])
        exit()
    elif b[q][0]+b[p][0]>x:
        q-=1
    else:
        p+=1
print('IMPOSSIBLE')
```
Basically the whole while loop, when the solution is printed, the code will end, but if there is no solution, it will not run the strand that has the exit in it, however, the loop will end, and the code will print IMPOSSIBLE

## Conclusion
This problem is solved by brute force, because the parts need to have a loop.

By: Spencer Wu https://cses.fi/user/212907