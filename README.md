# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: Sai Praveen C
RegisterNumber: 212225230239
'''
import numpy as np
def qr_Decomposition(A):
    A=np.array(A,dtype=float)
    m,n=A.shape
    
    Q=np.zeros((m,n))
    R=np.zeros((n,n))
    
    for j in range(n):
        v=A[:,j]
        for i in range(j):
            R[i,j]=np.dot(Q[:,i],A[:,j])
            v=v-R[i,j]*Q[:,i]
            
        R[j,j]=np.linalg.norm(v)
        Q[:,j]=v/R[j,j]
        
    return Q,R
    
    
A=np.array(eval(input()))
Q,R=qr_Decomposition(A)

print("The Q Matrix is \n",Q)
print("The R Matrix is \n",R)
```

## Output
```
<img width="1907" height="866" alt="Ex 8(a) Maths for AI" src="https://github.com/user-attachments/assets/774f5e2a-ccb7-4063-aa9a-5a9b08455e2d" />
<img width="1917" height="922" alt="Ex 8(b) Maths for AI" src="https://github.com/user-attachments/assets/a79c77f2-998d-4ce9-97cf-1e3dcf026ea9" />

```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
