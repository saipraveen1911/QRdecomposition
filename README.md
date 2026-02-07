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

<img width="1915" height="858" alt="Ex 8(a) Maths for AI" src="https://github.com/user-attachments/assets/4f655518-d9df-4681-8f88-04dc1b84254f" />

<img width="1917" height="922" alt="Ex 8(b) Maths for AI" src="https://github.com/user-attachments/assets/a55d19b6-b3e3-43d5-9654-cac2e30f3e99" />


```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
