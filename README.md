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
#NAME: BALAJI P
#REG NUMBER: 26007368
import os 
os.environ["OPENBLAS_NUM_THREADS"]="1"

import numpy as np
a=np.array(eval(input()), dtype=float)
m,n=a.shape
q=np.zeros((m,n))
r=np.zeros((n,n))

for j in range(n):
    v=a[:,j].copy()
    for i in range(j):
        r[i,j]=np.dot(q[:,i],a[:,j])
        v-=r[i,j]*q[:,i]
    r[j,j]=np.linalg.norm(v)
    q[:,j]=v/r[j,j]

print("The Q Matrix is")
print("",q)
print("The R Matrix is")
print("",r)
```

## Output

<img width="1235" height="702" alt="image" src="https://github.com/user-attachments/assets/afe41bc3-b2e3-43d1-ad9a-e66270daf18d" />


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
