# 3D Rotation

## Rotation matrix (Direction Cosine Matrix)

The Direction Cosine Matrix (DCM) is a rotation matrix that transforms one coordinate 
reference frame to another. Rotation matrices are a complete representation of a 3D 
orientation, thus there is no singularity (such as Gimble Lock) in that model.

### Vectors in a coordinate frame  

A coordinate frame can be represented by the unit vectors of its X, Y, and Z axes.  
Each of these unit vectors in its own coordinate frame can be represented by the 
following vectors:

$$
\hat{X} =
\left[ \begin{array}{r}
1 \\
0 \\
0
\end{array} \right] ;  
\hat{Y} =
\left[ \begin{array}{r}
0 \\
1 \\
0
\end{array} \right] ;  
\hat{Z} =
\left[ \begin{array}{r}
0 \\
0 \\
1
\end{array} \right]  
$$  

Or, this coordinate frame can be represented, in a compact way, by a matrix by putting 
these unit vectors as columns of a matrix, and give this frame a name, say $A$ as:  

$$ A = 
\left[ \begin{array}{rrr}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{array} \right]  
$$

Any vector in this coordinate frame can be described/represented by its projection on each 
of the axes. For example, a vector $V$ = $\left[ \begin{array}{rrr} 2 & 3 & 4 \end{array} \right]^T$ 
can be represented by three vectors along its axes as:  

$$
X =
\left[ \begin{array}{r}
2 \\
0 \\
0
\end{array} \right] ;  
Y =
\left[ \begin{array}{r}
0 \\
3 \\
0
\end{array} \right] ;  
Z =
\left[ \begin{array}{r}
0 \\
0 \\
4
\end{array} \right]  
$$

It can be seen that they can be obtained by multiplying the vector $V$ with the 
coordinate matrix $A$ on the left, as:  

$$
\left[ \begin{array}{rrr}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{array} \right]  
\left[ \begin{array}{rrr}
2 & 3 & 4
\end{array} \right]
$$

### Matrix multiplication

The general definition of matrix multiplication, multiplying a matrix $A$ of 
$m \times n$ with another matrix $B$ of $n \times p$ to give a third matrix $C$:  

$$
c_{ij} = a_{i1}b_{1j} + a_{i2}b_{2j} + \cdot \cdot \cdot  + a_{in}b_{nj} = \sum_{k=1}^{n}a_{ik}b_{kj}
$$

Therefore, it can be seen that if matrix $B$ is a row only, then the resulting 
matrix $C$ is built up of columns of $A$ multiplied by elements of $B$  

### A coordinate frame in another coordinate frame

If a coordinate frame is described/represented in another coordinate frame, it 
is only necessary to represent each of its axes unit vectors in the other coordinate 
frame. Then any vector in the original coordinate frame can be represented by 
the axes components.
  
### Rotation matrix

If the original coordinate frame is rotated about the X axis by an angle $\alpha$. 
This means anything on the X axis is not changed including all projections 
from any vector. Therefore, the matrix to left multiply to the vector will only 
have 1 on the X component column. And because the Y and Z axes are perpendicular 
to the X axis, their projections on X axis are zero.

A DCM locates three unit vectors that define a coordinate frame. The DCM is the 
combination of the three rotation matrices $RM(\alpha)$, $RM(\beta)$, and $RM(\gamma)$ 
respectively around X, Y and Z axes: