
# PA5 | EXPERIMENT 5 | Punongbayan
---
#### Submitted by Punongbayan, AJ Andriz J | 2ECE-A | 10.27.2026
---
### **Objectives**
---
At the end of this laboratory activity, the student should be able to:

1. create real and complex matrices in MATLAB;
2. distinguish transpose from complex-conjugate transpose operations;
3. express a simultaneous linear system in matrix form; and
4. solve and check a linear system using the inverse method and Cramer’s Rule.

The students are also expected to write a MATLAB script containing clearly labeled sections for both problems. Display the requested
matrices and numerical checks. Use MATLAB matrix operations and built-in functions; do not type
a computed answer directly into the output.

---
### **Programming Problems**
---
#### **A. TRANSPOSE OPERATIONS **

Define the real matrix **R** and complex matrix **Z**

For each matrix, compute and display `transpose(A)`, `A'`, and `A.'`. Below the output, answer the three analytical questions regarding transpose operations in MATLAB comments.

**CODE**
```
% Matrix R 
R = [ 5 -2  0  7;
    1  3 -4  2;
    6  0  8 -1];

R

% Matrix R transpose forms
Transpose_R = transpose(R)

R_Apostrophe = R'

R_Dot_Apostrophe = R.'

% Matrix Z 
Z = [ 2+3i  -1+4i   5-2i; -3+1i   6      2+5i];
Z

% Matrix Z transpose forms
Transpose_Z = transpose(Z)

Z_Apostrophe = Z'

Z_Dot_Apostrophe = Z.'
```

```
% Answer the following in MATLAB comments below your output:
% a. Which operations give identical results for the real matrix R?
% -- All three operations result to identical results for the real matrix R, since all elements 
%    are purely real.
%
% b. Which two operations give identical results for the complex matrix Z?
% -- transpose(Z) and Z.
%
% c. What additional operation is performed by the apostrophe operator (')
%    when the matrix contains complex entries?
% -- The single apostrophe operator (') computes the complex-conjugate
%    transpose. 
```
---
#### **B. TWO METHODS FOR A LINEAR SYSTEM 📐**

Solve the simultaneous system of linear equations
Construct coefficient matrix **A** and right-hand-side vector **b**. 
Solve the system using: 
- Matrix Inverse Method `(x_inv = A^-1 b)`
- Cramer's Rule using column substitution and determinants `(x_cramer)`
- Perform numerical checks by displaying `det(A)`, `norm(x_inv - x_cramer)`, and `norm(A x_inv - b)`.

**CODE**
```
% Coefficient matrix A  
A = [ 2 -1  3  2;
      1  4 -2  1;
      3  2  1 -1;
    -2  3  4  2];
A

% Right-hand-side vector b.
b = [16; -7; 6; 7];
b

% Determinant A
detA = det(A)

% Inverse Method
x_inv = inv(A) * b;
x_inv

% Cramer's Rule
A1 = A; A1(:, 1) = b;
A2 = A; A2(:, 2) = b;
A3 = A; A3(:, 3) = b;
A4 = A; A4(:, 4) = b;

A1
detA1 = det(A1)

A2
detA2 = det(A2)

A3
detA3 = det(A3)

A4
detA4 = det(A4)

x_cramer = [det(A1); 
            det(A2); 
            det(A3); 
            det(A4)] / det(A);
x_cramer

% Numerical precision
normdiff = norm(x_inv-x_cramer)
normprod = norm(A * x_inv - b)
```


### **END OF NOTEBOOK**
