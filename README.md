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
Developed by: Mohana k.v.s.l
RegisterNumber: 24900659
'''
import numpy as np
def QR_Decomposition(A):
    # Write your code 
    m, n = A.shape
    Q = np.zeros((m, n))
    R = np.zeros((n, n))
    for j in range(n):
        v = A[:, j]
        for i in range(j):
            R[i, j] = np.dot(Q[:, i], A[:, j])
            v = v - R[i, j] * Q[:, i]
        R[j, j] = np.linalg.norm(v)
        Q[:, j] = v / R[j, j]
    return Q, R
    
a = np.array(eval(input()))

Q, R = QR_Decomposition(a)
print(Q)
print(R)






```

## Output
![Screenshot 2025-05-16 200002](https://github.com/user-attachments/assets/c1645359-eda7-4c78-9842-94e3a1877da2)


```

```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
