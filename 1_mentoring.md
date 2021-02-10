**Understanding NumPy library**

**NumPy** is a Python library used for working with arrays. It also has functions for working in domain of linear algebra, fourier transform, and matrices. NumPy contains a multi-dimensional array and matrix data structures. It can be utilised to perform a number of mathematical operations on arrays such as trigonometric, statistical, and algebraic routines. ...

**A numpy array** is a grid of values, all of the same type, and is indexed by a tuple of non-negative integers. The number of dimensions is the rank of the array; the shape of an array is a tuple of integers giving the size of the array along each dimension.

NumPy arrays are the building blocks of most of the NumPy operations. The NumPy arrays can be divided into two types: One-dimensional arrays and Two-Dimensional arrays.

One of the biggest advantages of the NumPy arrays is their ability to perform linear algebra operations, such as the vector dot product and the matrix dot product, much faster than you can with the default Python lists. A vector in NumPy is basically just a 1-dimensional array.

**There are a few things to keep in mind when multiplying matrix.**
1.	Order matters: e.g AB != BA
2.	Matrices can be multiplied if the number of columns in the 1st equals the number of rows in the 2nd
3.	Multiplication is the dot product of rows and columns. Rows of the 1st matrix with columns of the 2nd

**Possible cause of this error: ValueError: shapes (1,3) and (1,3) not aligned: 3 (dim 1) != 1 (dim 0)**

You are trying to compute the vector dot product of the corresponding rows of two 2 dimensional arrays A and B in numpy. The column of the first matrix and the row of the second matrix should be equal to follow this rule: Multiplying 1 x 3 with a 3 x 1 matrix. Basically, dot follows normal rules for matrix multiplication along the last two dimensions, but the leading dimensions are always combined.

When you create a numpy array from numpy arrays, the result is a 2D array. Going forward, you have two options:

i.	You can either be more careful with your inputs, 

ii.	Or you can sanitize the array after you've created it.

A*B simply broadcast the 2D array and axis in np.sum() allows you to select the dimension in which you want to calculate the dot product.
