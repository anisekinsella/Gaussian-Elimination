# Gaussian-Elimination

## AIM 
To write a program to find the solution of a matrix using Gaussian Elimination.

## EQUIPMENTS REQUIRED 
 1. Hardware – PCs
 2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## ALGORITHM
1. Start the program.
2. Read the number of unknowns n and form the augmented matrix [A|B].
3. Perform forward elimination: For each pivot row, make elements below the pivot equal to zero using row operations.
4. Perform back substitution: Solve for variables starting from the last row up to the first row. Display the values of unknowns. Stop the program.

## PROGRAM 
~
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: ANISE KINSELLA A
RegisterNumber: 212225040021
'''
import os
os.environ['OPENBLAS_NUM_THREADS']='1'
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i] == 0.0:
        sys.exit("Divide by Zero detected!")

   for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]
x[n-1] = a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    for j in range(i+1,n):
        x[i] = x[i]-a[i][j]*x[j]
    x[i] = x[i]/a[i][i]
for i in range(n):
    print("X%d = %0.2f " %(i,x[i]) ,end= "")
~

## OUTPUT 
<img width="1292" height="667" alt="image" src="https://github.com/user-attachments/assets/af3109a7-7607-499d-ba84-1940fa9375cf" />


## RESULT 
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.
