# CSES Sum of two values tutorial
Here, we have 2 solutions, one using nested loops, and the other using a while loop.
'''py
n,x=[int(a) for a in input().split(' ')]
a=[int(b) for b in input().split(' ')]
for i in range(0, n-1):
    for j in range(i+1, n):
        if a[i]+a[j]==x:
            print(i+1, j+1)
            exit()
print('IMPOSSIBLE')
'''