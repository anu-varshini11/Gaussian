# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Reduce matrix to upper triangular form using row operations.
2. Solve for unknowns by back-substituting values from the bottom.
3. Validate the solution by substituting into original equations.
4. Output the solution vector obtained from back substitution.

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: M B ANU VARSHINI
RegisterNumber: 23008712 
'''
import numpy as np
n=int(input())
arr=np.zeros((n,n+1))
res=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        arr[i][j]=int(input())
for i in range(n):
    for j in range(i+1,n):
        ratio=arr[j][i]/arr[i][i]
        for k in range(n+1):
            arr[j][k]=arr[j][k]-ratio*arr[i][k]
res[n-1]=arr[n-1][n]/arr[n-1][n-1]
for i in range(n-1,-1,-1):
    res[i]=arr[i][n]
    for j in range(i+1,n):
        res[i]=res[i]-arr[i][j]*res[j]
    res[i]=res[i]/arr[i][i]
for i in range(n):
    print("X%d = %0.2f" %(i,res[i]),end=" ")
```

## Output:
![guass](https://github.com/anu-varshini11/Gaussian/assets/138969827/a48fc5f4-1789-4dd2-b854-a7f1e3471078)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

