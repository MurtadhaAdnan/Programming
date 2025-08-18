$$
\Longleftrightarrow\left[\begin{array}{ccc}
a_{11} & \cdots & a_{1 n}  \tag{2.10}\\
\vdots & & \vdots \\
a_{m 1} & \cdots & a_{m n}
\end{array}\right]\left[\begin{array}{c}
x_{1} \\
\vdots \\
x_{n}
\end{array}\right]=\left[\begin{array}{c}
b_{1} \\
\vdots \\
b_{m}
\end{array}\right] .
$$

In the following, we will have a close look at these matrices and define computation rules. We will return to solving linear equations in Section 2.3.

### 2.2 Matrices

Matrices play a central role in linear algebra. They can be used to compactly represent systems of linear equations, but they also represent linear functions (linear mappings) as we will see later in Section 2.7. Before we discuss some of these interesting topics, let us first define what a matrix is and what kind of operations we can do with matrices. We will see more properties of matrices in Chapter 4.

Definition 2.1 (Matrix). With $m, n \in \mathbb{N}$ a real-valued ( $m, n$ ) matrix $\boldsymbol{A}$ is an $m \cdot n$-tuple of elements $a_{i j}, i=1, \ldots, m, j=1, \ldots, n$, which is ordered according to a rectangular scheme consisting of $m$ rows and $n$ columns:

$$
\boldsymbol{A}=\left[\begin{array}{cccc}
a_{11} & a_{12} & \cdots & a_{1 n}  \tag{2.11}\\
a_{21} & a_{22} & \cdots & a_{2 n} \\
\vdots & \vdots & & \vdots \\
a_{m 1} & a_{m 2} & \cdots & a_{m n}
\end{array}\right], \quad a_{i j} \in \mathbb{R}
$$

By convention ( $1, n$ )-matrices are called rows and ( $m, 1$ )-matrices are called columns. These special matrices are also called row/column vectors.
$\mathbb{R}^{m \times n}$ is the set of all real-valued ( $m, n$ )-matrices. $\boldsymbol{A} \in \mathbb{R}^{m \times n}$ can be equivalently represented as $\boldsymbol{a} \in \mathbb{R}^{m n}$ by stacking all $n$ columns of the matrix into a long vector; see Figure 2.4.

### 2.2.1 Matrix Addition and Multiplication

The sum of two matrices $\boldsymbol{A} \in \mathbb{R}^{m \times n}, \boldsymbol{B} \in \mathbb{R}^{m \times n}$ is defined as the elementwise sum, i.e.,

$$
\boldsymbol{A}+\boldsymbol{B}:=\left[\begin{array}{ccc}
a_{11}+b_{11} & \cdots & a_{1 n}+b_{1 n}  \tag{2.12}\\
\vdots & & \vdots \\
a_{m 1}+b_{m 1} & \cdots & a_{m n}+b_{m n}
\end{array}\right] \in \mathbb{R}^{m \times n}
$$

For matrices $\boldsymbol{A} \in \mathbb{R}^{m \times n}, \boldsymbol{B} \in \mathbb{R}^{n \times k}$, the elements $c_{i j}$ of the product $\boldsymbol{C}=\boldsymbol{A} \boldsymbol{B} \in \mathbb{R}^{m \times k}$ are computed as

$$
\begin{equation*}
c_{i j}=\sum_{l=1}^{n} a_{i l} b_{l j}, \quad i=1, \ldots, m, \quad j=1, \ldots, k . \tag{2.13}
\end{equation*}
$$

### 2.2 Matrices

This means, to compute element $c_{i j}$ we multiply the elements of the $i$ th row of $\boldsymbol{A}$ with the $j$ th column of $\boldsymbol{B}$ and sum them up. Later in Section 3.2, we will call this the dot product of the corresponding row and column. In cases, where we need to be explicit that we are performing multiplication, we use the notation $\boldsymbol{A} \cdot \boldsymbol{B}$ to denote multiplication (explicitly showing ".").
Remark. Matrices can only be multiplied if their "neighboring" dimensions match. For instance, an $n \times k$-matrix $\boldsymbol{A}$ can be multiplied with a $k \times m$ matrix $\boldsymbol{B}$, but only from the left side:

$$
\begin{equation*}
\underbrace{A}_{n \times k} \underbrace{B}_{k \times m}=\underbrace{C}_{n \times m} \tag{2.14}
\end{equation*}
$$

The product $\boldsymbol{B} \boldsymbol{A}$ is not defined if $m \neq n$ since the neighboring dimensions do not match.
Remark. Matrix multiplication is not defined as an element-wise operation on matrix elements, i.e., $c_{i j} \neq a_{i j} b_{i j}$ (even if the size of $\boldsymbol{A}, \boldsymbol{B}$ was chosen appropriately). This kind of element-wise multiplication often appears in programming languages when we multiply (multi-dimensional) arrays with each other, and is called a Hadamard product.

## Example 2.3

For $\boldsymbol{A}=\left[\begin{array}{lll}1 & 2 & 3 \\ 3 & 2 & 1\end{array}\right] \in \mathbb{R}^{2 \times 3}, \boldsymbol{B}=\left[\begin{array}{cc}0 & 2 \\ 1 & -1 \\ 0 & 1\end{array}\right] \in \mathbb{R}^{3 \times 2}$, we obtain

$$
\begin{align*}
\boldsymbol{A} \boldsymbol{B} & =\left[\begin{array}{lll}
1 & 2 & 3 \\
3 & 2 & 1
\end{array}\right]\left[\begin{array}{cc}
0 & 2 \\
1 & -1 \\
0 & 1
\end{array}\right]=\left[\begin{array}{ll}
2 & 3 \\
2 & 5
\end{array}\right] \in \mathbb{R}^{2 \times 2}  \tag{2.15}\\
\boldsymbol{B} \boldsymbol{A} & =\left[\begin{array}{cc}
0 & 2 \\
1 & -1 \\
0 & 1
\end{array}\right]\left[\begin{array}{ccc}
1 & 2 & 3 \\
3 & 2 & 1
\end{array}\right]=\left[\begin{array}{ccc}
6 & 4 & 2 \\
-2 & 0 & 2 \\
3 & 2 & 1
\end{array}\right] \in \mathbb{R}^{3 \times 3} . \tag{2.16}
\end{align*}
$$

From this example, we can already see that matrix multiplication is not commutative, i.e., $\boldsymbol{A} \boldsymbol{B} \neq \boldsymbol{B} \boldsymbol{A}$; see also Figure 2.5 for an illustration.

Definition 2.2 (Identity Matrix). In $\mathbb{R}^{n \times n}$, we define the identity matrix

$$
\boldsymbol{I}_{n}:=\left[\begin{array}{cccccc}
1 & 0 & \cdots & 0 & \cdots & 0  \tag{2.17}\\
0 & 1 & \cdots & 0 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & 1 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & 0 & \cdots & 1
\end{array}\right] \in \mathbb{R}^{n \times n}
$$

as the $n \times n$-matrix containing 1 on the diagonal and 0 everywhere else.
Now that we defined matrix multiplication, matrix addition and the identity matrix, let us have a look at some properties of matrices:

- Associativity:

$$
\begin{equation*}
\forall \boldsymbol{A} \in \mathbb{R}^{m \times n}, \boldsymbol{B} \in \mathbb{R}^{n \times p}, \boldsymbol{C} \in \mathbb{R}^{p \times q}:(\boldsymbol{A} \boldsymbol{B}) \boldsymbol{C}=\boldsymbol{A}(\boldsymbol{B} \boldsymbol{C}) \tag{2.18}
\end{equation*}
$$

- Distributivity:

$$
\begin{array}{r}
\forall A, B \in \mathbb{R}^{m \times n}, C, D \in \mathbb{R}^{n \times p}:(A+B) C=A C+B C \\
A(C+D)=A C+A D \tag{2.19b}
\end{array}
$$

- Multiplication with the identity matrix:

$$
\begin{equation*}
\forall \boldsymbol{A} \in \mathbb{R}^{m \times n}: \boldsymbol{I}_{m} \boldsymbol{A}=\boldsymbol{A} \boldsymbol{I}_{n}=\boldsymbol{A} \tag{2.20}
\end{equation*}
$$

Note that $\boldsymbol{I}_{m} \neq \boldsymbol{I}_{n}$ for $m \neq n$.

### 2.2.2 Inverse and Transpose

Definition 2.3 (Inverse). Consider a square matrix $\boldsymbol{A} \in \mathbb{R}^{n \times n}$. Let matrix $\boldsymbol{B} \in \mathbb{R}^{n \times n}$ have the property that $\boldsymbol{A} \boldsymbol{B}=\boldsymbol{I}_{n}=\boldsymbol{B} \boldsymbol{A}$. $\boldsymbol{B}$ is called the inverse of $\boldsymbol{A}$ and denoted by $\boldsymbol{A}^{-1}$.

Unfortunately, not every matrix $\boldsymbol{A}$ possesses an inverse $\boldsymbol{A}^{-1}$. If this inverse does exist, $\boldsymbol{A}$ is called regular/invertible/nonsingular, otherwise singular/noninvertible. When the matrix inverse exists, it is unique. In Section 2.3, we will discuss a general way to compute the inverse of a matrix by solving a system of linear equations.
Remark (Existence of the Inverse of a $2 \times 2$-matrix). Consider a matrix

$$
\boldsymbol{A}:=\left[\begin{array}{ll}
a_{11} & a_{12}  \tag{2.21}\\
a_{21} & a_{22}
\end{array}\right] \in \mathbb{R}^{2 \times 2}
$$

If we multiply $\boldsymbol{A}$ with

$$
\boldsymbol{A}^{\prime}:=\left[\begin{array}{cc}
a_{22} & -a_{12}  \tag{2.22}\\
-a_{21} & a_{11}
\end{array}\right]
$$

we obtain

$$
\boldsymbol{A} \boldsymbol{A}^{\prime}=\left[\begin{array}{cc}
a_{11} a_{22}-a_{12} a_{21} & 0  \tag{2.23}\\
0 & a_{11} a_{22}-a_{12} a_{21}
\end{array}\right]=\left(a_{11} a_{22}-a_{12} a_{21}\right) \boldsymbol{I} .
$$

Therefore,

$$
\boldsymbol{A}^{-1}=\frac{1}{a_{11} a_{22}-a_{12} a_{21}}\left[\begin{array}{cc}
a_{22} & -a_{12}  \tag{2.24}\\
-a^{21} & a^{11}
\end{array}\right]
$$

if and only if $a_{11} a_{22}-a_{12} a_{21} \neq 0$. In Section 4.1, we will see that $a_{11} a_{22}-$

### 2.2 Matrices

$a_{12} a_{21}$ is the determinant of a $2 \times 2$-matrix. Furthermore, we can generally use the determinant to check whether a matrix is invertible.

## Example 2.4 (Inverse Matrix)

The matrices

$$
\boldsymbol{A}=\left[\begin{array}{lll}
1 & 2 & 1  \tag{2.25}\\
4 & 4 & 5 \\
6 & 7 & 7
\end{array}\right], \quad \boldsymbol{B}=\left[\begin{array}{ccc}
-7 & -7 & 6 \\
2 & 1 & -1 \\
4 & 5 & -4
\end{array}\right]
$$

are inverse to each other since $\boldsymbol{A} \boldsymbol{B}=\boldsymbol{I}=\boldsymbol{B} \boldsymbol{A}$.

Definition 2.4 (Transpose). For $\boldsymbol{A} \in \mathbb{R}^{m \times n}$ the matrix $\boldsymbol{B} \in \mathbb{R}^{n \times m}$ with $b_{i j}=a_{j i}$ is called the transpose of $\boldsymbol{A}$. We write $\boldsymbol{B}=\boldsymbol{A}^{\top}$.

In general, $\boldsymbol{A}^{\top}$ can be obtained by writing the columns of $\boldsymbol{A}$ as the rows of $\boldsymbol{A}^{\top}$. The following are important properties of inverses and transposes:

$$
\begin{align*}
\boldsymbol{A} \boldsymbol{A}^{-1} & =\boldsymbol{I}=\boldsymbol{A}^{-1} \boldsymbol{A}  \tag{2.26}\\
(\boldsymbol{A} \boldsymbol{B})^{-1} & =\boldsymbol{B}^{-1} \boldsymbol{A}^{-1}  \tag{2.27}\\
(\boldsymbol{A}+\boldsymbol{B})^{-1} & \neq \boldsymbol{A}^{-1}+\boldsymbol{B}^{-1}  \tag{2.28}\\
\left(\boldsymbol{A}^{\top}\right)^{\top} & =\boldsymbol{A}  \tag{2.29}\\
(\boldsymbol{A} \boldsymbol{B})^{\top} & =\boldsymbol{B}^{\top} \boldsymbol{A}^{\top}  \tag{2.30}\\
(\boldsymbol{A}+\boldsymbol{B})^{\top} & =\boldsymbol{A}^{\top}+\boldsymbol{B}^{\top} \tag{2.31}
\end{align*}
$$

Definition 2.5 (Symmetric Matrix). A matrix $\boldsymbol{A} \in \mathbb{R}^{n \times n}$ is symmetric if $\boldsymbol{A}=\boldsymbol{A}^{\top}$.

Note that only ( $n, n$ )-matrices can be symmetric. Generally, we call ( $n, n$ )-matrices also square matrices because they possess the same number of rows and columns. Moreover, if $\boldsymbol{A}$ is invertible, then so is $\boldsymbol{A}^{\top}$, and $\left(\boldsymbol{A}^{-1}\right)^{\top}=\left(\boldsymbol{A}^{\top}\right)^{-1}=: \boldsymbol{A}^{-\top}$.
Remark (Sum and Product of Symmetric Matrices). The sum of symmetric matrices $\boldsymbol{A}, \boldsymbol{B} \in \mathbb{R}^{n \times n}$ is always symmetric. However, although their product is always defined, it is generally not symmetric:

$$
\left[\begin{array}{ll}
1 & 0  \tag{2.32}\\
0 & 0
\end{array}\right]\left[\begin{array}{ll}
1 & 1 \\
1 & 1
\end{array}\right]=\left[\begin{array}{ll}
1 & 1 \\
0 & 0
\end{array}\right]
$$

### 2.2.3 Multiplication by a Scalar

Let us look at what happens to matrices when they are multiplied by a scalar $\lambda \in \mathbb{R}$. Let $\boldsymbol{A} \in \mathbb{R}^{m \times n}$ and $\lambda \in \mathbb{R}$. Then $\lambda \boldsymbol{A}=\boldsymbol{K}, K_{i j}=\lambda a_{i j}$. Practically, $\lambda$ scales each element of $\boldsymbol{A}$. For $\lambda, \psi \in \mathbb{R}$, the following holds:

- Associativity:
$(\lambda \psi) \boldsymbol{C}=\lambda(\psi \boldsymbol{C}), \quad \boldsymbol{C} \in \mathbb{R}^{m \times n}$
- $\lambda(\boldsymbol{B} \boldsymbol{C})=(\lambda \boldsymbol{B}) \boldsymbol{C}=\boldsymbol{B}(\lambda \boldsymbol{C})=(\boldsymbol{B} \boldsymbol{C}) \lambda, \quad \boldsymbol{B} \in \mathbb{R}^{m \times n}, \boldsymbol{C} \in \mathbb{R}^{n \times k}$.

Note that this allows us to move scalar values around.

- $(\lambda \boldsymbol{C})^{\top}=\boldsymbol{C}^{\top} \lambda^{\top}=\boldsymbol{C}^{\top} \lambda=\lambda \boldsymbol{C}^{\top}$ since $\lambda=\lambda^{\top}$ for all $\lambda \in \mathbb{R}$.
- Distributivity:

$$
\begin{aligned}
& (\lambda+\psi) \boldsymbol{C}=\lambda \boldsymbol{C}+\psi \boldsymbol{C}, \quad \boldsymbol{C} \in \mathbb{R}^{m \times n} \\
& \lambda(\boldsymbol{B}+\boldsymbol{C})=\lambda \boldsymbol{B}+\lambda \boldsymbol{C}, \quad \boldsymbol{B}, \boldsymbol{C} \in \mathbb{R}^{m \times n}
\end{aligned}
$$

## Example 2.5 (Distributivity)

If we define

$$
C:=\left[\begin{array}{ll}
1 & 2  \tag{2.33}\\
3 & 4
\end{array}\right],
$$

then for any $\lambda, \psi \in \mathbb{R}$ we obtain

$$
\begin{align*}
(\lambda+\psi) \boldsymbol{C} & =\left[\begin{array}{ll}
(\lambda+\psi) 1 & (\lambda+\psi) 2 \\
(\lambda+\psi) 3 & (\lambda+\psi) 4
\end{array}\right]=\left[\begin{array}{cc}
\lambda+\psi & 2 \lambda+2 \psi \\
3 \lambda+3 \psi & 4 \lambda+4 \psi
\end{array}\right]  \tag{2.34a}\\
& =\left[\begin{array}{cc}
\lambda & 2 \lambda \\
3 \lambda & 4 \lambda
\end{array}\right]+\left[\begin{array}{cc}
\psi & 2 \psi \\
3 \psi & 4 \psi
\end{array}\right]=\lambda \boldsymbol{C}+\psi \boldsymbol{C} . \tag{2.34b}
\end{align*}
$$

### 2.2.4 Compact Representations of Systems of Linear Equations

If we consider the system of linear equations

$$
\begin{align*}
& 2 x_{1}+3 x_{2}+5 x_{3}=1 \\
& 4 x_{1}-2 x_{2}-7 x_{3}=8  \tag{2.35}\\
& 9 x_{1}+5 x_{2}-3 x_{3}=2
\end{align*}
$$

and use the rules for matrix multiplication, we can write this equation system in a more compact form as

$$
\left[\begin{array}{ccc}
2 & 3 & 5  \tag{2.36}\\
4 & -2 & -7 \\
9 & 5 & -3
\end{array}\right]\left[\begin{array}{l}
x_{1} \\
x_{2} \\
x_{3}
\end{array}\right]=\left[\begin{array}{l}
1 \\
8 \\
2
\end{array}\right] .
$$

Note that $x_{1}$ scales the first column, $x_{2}$ the second one, and $x_{3}$ the third one.

Generally, a system of linear equations can be compactly represented in their matrix form as $\boldsymbol{A} \boldsymbol{x}=\boldsymbol{b}$; see (2.3), and the product $\boldsymbol{A} \boldsymbol{x}$ is a (linear) combination of the columns of $\boldsymbol{A}$. We will discuss linear combinations in more detail in Section 2.5.

