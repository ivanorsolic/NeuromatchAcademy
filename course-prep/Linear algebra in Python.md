# Linear algebra

Watch 3Blue1Brown: **[The essence of linear algebra.](https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab)**

Solve the excercises below.

### Numpy exercises

#### Write a NumPy program to compute the multiplication of two given matrixes.

![NumPy Linear algebra: Compute the multiplication of two given matrixes](https://www.w3resource.com/w3r_images/linear-algebra-image-exercise-1.png)

```python
import numpy as np
a = [[1, 0], [0, 1]]
b = [[1, 2], [3, 4]]

def multiplyMatrices(matrixA, matrixB):
	return np.dot(matrixA, matrixB)
	
print(multiplyMatrices(a, b))
```

#### Write a NumPy program to compute the outer product of two given vectors.

![NumPy Linear algebra: Compute the outer product of two given vectors](https://www.w3resource.com/w3r_images/linear-algebra-image-exercise-2.png)

​	

```python
import numpy as np
a = [[1, 0], [0, 1]]
b = [[1, 2], [3, 4]]

def outerProduct(vectorA, vectorB):
	return np.outer(vectorA, vectorB)

print(outerProduct(a, b))
```

#### Write a NumPy program to compute the cross product of two given vectors.

<img src="https://www.w3resource.com/w3r_images/linear-algebra-image-exercise-3.png" alt="NumPy Linear algebra: Compute the cross product of two given vectors" style="zoom:50%;" />

```python
import numpy as np
a = [[1, 0], [0, 1]]
b = [[1, 2], [3, 4]]

def crossProduct(vectorA, vectorB):
	return np.cross(vectorA, vectorB)

print(crossProduct(a, b))
```

#### Write a NumPy program to compute the determinant of a given square array.

![NumPy Linear algebra: Compute the determinant of a given square array](https://www.w3resource.com/w3r_images/linear-algebra-image-exercise-4.png)

```python
import numpy as np
from numpy import linalg as la
a = np.array([[1, 0], [1, 2]])

def squareDeterminant(array):
	return la.det(array)

print(squareDeterminant(a))
```

#### Write a NumPy program to evaluate Einstein's summation convention of two given multidimensional arrays.

> In mathematics, especially in applications of linear algebra to physics, the [Einstein notation](https://www.wikiwand.com/en/Einstein_notation) or **[Einstein summation convention](https://www.wikiwand.com/en/Einstein_notation) is a notational convention that implies summation over a set of indexed terms in a formula**, thus achieving notational brevity.
>
> ![image-20200709000823150](https://i.imgur.com/aFfhaHW.png)

```python
import numpy as np
a = np.array([1,2,3])
b = np.array([0,1,0])

def einsteinSummation(subscript, vectorA, vectorB):
    return np.einsum(subscript, vectorA, vectorB)

print(einsteinSummation("n,n", a, b))
```

[No idea.](https://numpy.org/doc/stable/reference/generated/numpy.einsum.html)

#### Write a NumPy program to compute the inner product of vectors for 1-D arrays (without complex conjugation) and in higher dimension.

```python
import numpy as np
a = np.array([1,2,5])
b = np.array([2,1,0])

def innerProduct(vectorA, vectorB):
    return np.inner(vectorA, vectorB)

print(innerProduct(a, b))
```

#### Write a NumPy program to compute the eigenvalues and right eigenvectors of a given square array.

```python
import numpy as np
a = np.array([[3, -2], [1, 0]])

def eigen(vector):
	eigenvalues, eigenvectors = np.linalg.eig(vector)
	return eigenvalues, eigenvectors

print(eigen(a))
```

#### Write a NumPy program to compute the Kronecker product of two given multidimension arrays.

> In mathematics, the Kronecker product, denoted by ⊗, is an operation on two matrices of arbitrary size resulting in a block matrix. It is a generalization of the outer product (which is denoted by the same symbol) from vectors to matrices, and gives the matrix of the tensor product with respect to a standard choice of basis. The Kronecker product should not be confused with the usual matrix multiplication, which is an entirely different operation.
>
> If A is an m × n matrix and B is a p × q matrix, then the Kronecker product A ⊗ B is the mp × nq block matrix:
>
> ![NumPy Linear algebra: Compute the Kronecker product of two given mulitdimension arrays](https://www.w3resource.com/w3r_images/linear-algebra-image-exercise-8.png)

```python
import numpy as np
a = np.array([1,2,3])
b = np.array([0,1,0])

def kroneckerProduct(vectorA, vectorB):
	return np.kron(vectorA, vectorB)

print(kroneckerProduct(a, b))
```

#### Write a NumPy program to compute the condition number of a given matrix.

> In the field of numerical analysis, the condition number of a function with respect to an argument measures how much the output value of the function can change for a small change in the input argument. This is used to measure how sensitive a function is to changes or errors in the input, and how much error in the output results from an error in the input. Very frequently, one is solving the inverse problem – given $ f(x) = y$, one is solving for x, and thus the condition number of the (local) inverse must be used. In linear regression the condition number can be used as a diagnostic for multicollinearity.

```python
import numpy as np
from numpy import linalg as la
a = np.array([[1, 0, -1], [0, 1, 0], [1, 0, 1]])

def conditionNumber(matrix):
    return la.cond(matrix)

print(conditionNumber(a))
```

#### Write a NumPy program to find a [matrix or vector norm](https://www.cs.utexas.edu/users/flame/Notes/NotesOnNorms.pdf).

```
import numpy as np

a = np.array([1,2,3,4,5,6,7])
b = np.array([[1, 2], [3, 4]])

def norm(vectorOrMatrix):
	return np.linalg.norm(vectorOrMatrix)
	
print("Vector norm: %d" % (norm(a)))
print("Matrix norm: %d" % (norm(b)))
```

#### Write a NumPy program to compute the determinant of an array.

> In linear algebra, the determinant is a value that can be computed from the elements of a square matrix. The determinant of a matrix A is denoted $det(A)$, $det A$, or $|A|$. Geometrically, it can be viewed as the scaling factor of the linear transformation described by the matrix.
>
> ![NumPy Linear algebra: Compute the determinant of an array](https://www.w3resource.com/w3r_images/linear-algebra-image-exercise-4.png)

```python
import numpy as np
a = np.array([[1, 2], [3, 4]])

def determinant(array):
	return np.linalg.det(array)

print(determinant(a))
```

#### Write a NumPy program to compute the inverse of a given matrix.

```python
import numpy as np
a = np.array([[1, 2], [3, 4]])

def inverse(matrix):
	return np.linalg.inv(matrix)

print(inverse(a))
```

#### Write a NumPy program to calculate the QR decomposition of a given matrix.

> In linear algebra, a QR decomposition (also called a QR factorization) of a matrix is a decomposition of a matrix A into a product $A = QR$ of an orthogonal matrix Q and an upper triangular matrix R. QR decomposition is often used to solve the linear least squares problem and is the basis for a particular eigenvalue algorithm, the QR algorithm.
>
> **Square matrix**
> Any real square matrix A may be decomposed as $A = QR$ where Q is an orthogonal matrix (its columns are orthogonal unit vectors meaning ${\displaystyle Q^{\textsf {T}}Q=QQ^{\textsf {T}}=I})$ and R is an upper triangular matrix (also called right triangular matrix). 
>
> If A is invertible, then the factorization is unique if we require the diagonal elements of R to be positive.
>
> If instead A is a complex square matrix, then there is a decomposition A = QR where Q is a unitary matrix (so $\displaystyle {Q^{*}Q=QQ^{*}=I}$).
>
> If A has n linearly independent columns, then the first n columns of Q form an orthonormal basis for the column space of A. More generally, the first k columns of Q form an orthonormal basis for the span of the first k columns of A for any $1 ≤ k ≤ n.$ 
>
> The fact that any column k of A only depends on the first k columns of Q is responsible for the triangular form of R.

```python
import numpy as np
a = np.array([[1, 2], [3, 4]])

def qrDecomposition(matrix):
	return np.linalg.qr(matrix)

print(qrDecomposition(a))
```

#### Write a NumPy program to compute the condition number of a given matrix.

> In the field of numerical analysis, the condition number of a function with respect to an argument measures how much the output value of the function can change for a small change in the input argument. This is used to measure how sensitive a function is to changes or errors in the input, and how much error in the output results from an error in the input.

```python
import numpy as np
a = np.array([[1, 2], [3, 4]])

def conditionNumber(matrix):
	return np.linalg.cond(matrix)

print(conditionNumber(a))
```

#### Write a NumPy program to compute the sum of the diagonal element of a given array.

```python
import numpy as np
a = np.array([[0, 1, 2], [3, 4, 5]])

def diagonalSum(matrix):
	return np.trace(matrix)

print(diagonalSum(a))
```

#### Write a NumPy program to get the lower-triangular L in the Cholesky decomposition of a given array.

```python
import numpy as np
a = np.array([[0, 1, 2], [3, 4, 5], [6, 7, 8]])

def cholesky(matrix):
	return np.cholesky(matrix)

print(cholesky(a))
```

#### Write a NumPy program to compute the factor of a given array by Singular Value Decomposition.

```python
import numpy as np
a = np.array([[1, 0, 0, 0, 2], [0, 0, 3, 0, 0], [0, 0, 0, 0, 0], [0, 2, 0, 0, 0]], type=np.float32)

def svdFactor(array):
	u, s, v = np.linalg.svd(array, full_matries=False)
	return u, s, v

print(svdFactor(a))
```

#### Write a NumPy program to calculate the Frobenius norm and the condition number of a given array.

```python
import numpy as np
a = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

def frobeniusNormAndCondition(array):
    return np.linalg.norm(array, "fro"), np.linalg.cond(array, "fro")

print(frobeniusNormAndCondition(a))
```
