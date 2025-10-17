# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. import numpy and sys to create matrix a and array x
2. calculate the solution by transforming a and solving for x
3. using nested loops find the perfect solution
4. print them with print another loop

## Program:
```
Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: MadhanM
RegisterNumber: 25018367
```
```py
import numpy as np
import sys
n = int(input())
a = np.zeros((n, n+1))
x = np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())
for i in range(n):
    if a[i][i] == 0:
        sys.exit('Divide by zero detected')
    for j in range(i+1, n):
        ratio = a[j][i] / a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k]-ratio*a[i][k]
x[n-1] = a[n-1][n] / a[n-1][n-1]
for i in range(n-2, -1, -1):
    x[i] = a[i][n]
    for j in range(i+1, n):
        x[i] = x[i]-a[i][j]*x[j]
    x[i] = x[i] / a[i][i]
y=['X0','X1','X2']
for i in range(n):
    print(f"{y[i]} = {x[i]:.2f}", end=" ")
```

## Output:
<img width="808" height="454" alt="image" src="https://github.com/user-attachments/assets/3c3f4455-8796-4ab4-8298-dc3fe9d0ac16" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.
