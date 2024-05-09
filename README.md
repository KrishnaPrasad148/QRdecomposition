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
Program to QR decomposition using the Gram-Schmidt method
Developed by: Krishna Prasad.S
RegisterNumber: 212223230108
```
```

import numpy as np
def QR_Decomposition(arr):
    n,m = arr.shape
    u = np.empty((n,m))
    e = np.empty((n,m))
    u[:,0] = arr[:,0]
    e[:,0] = u[:,0]/np.linalg.norm(u[:,0])
    for i in range(n):
        u[:,i] = arr[:,i]
        for j in range(i):
            u[:,i] -= (arr[:,i]@e[:,j])*e[:,j]
            e[:,i] = u[:,i]/np.linalg.norm(u[:,i])
    r = np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            r[i,j] = arr[:,j]@e[:,i]
    print(e)
    print(r)
arr = np.array(eval(input()))
QR_Decomposition(arr)
```

## Output
![Screenshot 91827210](https://github.com/KrishnaPrasad148/QRdecomposition/assets/147332763/c280d4ca-63bc-4d59-8390-060b9f284852)
![Screenshot 2024-05-09 112204](https://github.com/KrishnaPrasad148/QRdecomposition/assets/147332763/a56ca4cd-597e-4b96-aa87-c66920e8357e)


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
