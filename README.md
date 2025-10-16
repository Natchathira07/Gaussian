# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.First,we want to import numpy,then import sys,assume a variable
2.For gaussian method,we want to make 2nd and 3rd column zero
3.For that we want to make a range according to your output
4.Then print the program with the correct form then the output will display 

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: VD Natchathira
RegisterNumber: 212224230178
*/
import numpy as np
import sys

# Reading number of unknowns
n = int(input())

# Making numpy array of n x n+1 size and initializing 
# to zero for storing augmented matrix
a = np.zeros((n,n+1))

# Making numpy array of n size and initializing 
# to zero for storing solution vector
x = np.zeros(n)

# Reading augmented matrix coefficients
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())

# Applying Gauss Elimination
for i in range(n):
    if a[i][i] == 0.0:
        sys.exit('Divide by zero detected!')
        
    for j in range(i+1, n):
        ratio = a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]

# Back Substitution
x[n-1] = a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    
    for j in range(i+1,n):
        x[i] = x[i] - a[i][j]*x[j]
    
    x[i] = x[i]/a[i][i]

# Displaying solution
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]), end = ' ')
```

## Output:
<img width="1100" height="569" alt="Screenshot 2025-10-16 101942" src="https://github.com/user-attachments/assets/56a81b74-83f9-4ab1-80fa-222b70256d58" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

