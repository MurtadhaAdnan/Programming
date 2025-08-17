# 4

# Matrix Decompositions

In Chapters 2 and 3, we studied ways to manipulate and measure vectors projections of vectors, and linear mappings. Mappings and transforma tions of vectors can be conveniently described as operations performed by matrices. Moreover, data is often represented in matrix form as well, e.g., where the rows of the matrix represent different people and the columns describe different features of the people, such as weight, height, and socioeconomic status. In this chapter, we present three aspects of matrices: how to summarize matrices,how matrices can be decomposed, and how these decompositions can be used for matrix approximations We first consider methods that allow us to describe matrices with just

a few numbers that characterize the overall properties of matrices.We will do this in the sections on determinants (Section 4.1) and eigenval ues (Section 4.2) for the important special case of square matrices. These characteristic numbers have important mathematical consequences and allow us to quickly grasp what useful properties a matrix has. From here we will proceed to matrix decomposition methods: An analogy for matrix decomposition is the factoring of numbers, such as the factoring of 21 into prime numbers $7\cdot3$ For this reason matrix decomposition is also. often referred to as matrix factorization. Matrix decompositions are used to describe a matrix by means of a different representation using factors of interpretable matrices. We will first cover a square-root-like operation for symmetric, positive

definite matrices, the Cholesky decomposition (Section 4.3). From here we will look at two related methods for factorizing matrices into canonical forms. The first one is known as matrix diagonalization (Section 4.4) which allows us to represent the linear mapping using a diagonal transformation matrix if we choose an appropriate basis. The second method, singular value decomposition (Section 4.5), extends this factorization to non-square matrices, and it is considered one of the fundamental concepts in linear algebra. These decompositions are helpful, as matrices represent ing numerical data are often very large and hard to analyze. We conclude the chapter with a systematic overview of the types of matrices and the characteristic properties that distinguish them in the form of a matrix taxonomy (Section 4.7). The methods that we cover in this chapter will become important in

------------------------------------------------------------------

![](https://storage.simpletex.cn/view/f0ct34Kw2SdGoO4VntnQVNuF1rDnhEpuF)

both subsequent mathematical chapters,such as Chapter 6,but also in applied chapters, such as dimensionality reduction in Chapters 10 or density estimation in Chapter 11. This chapter's overall structure is depicted in the mind map of Figure 4.1

Figure 4.1 A mind map of the concepts introduced in this chapter, along with where they are used in other parts of the book

## 4.1 Determinant and Trace

The determinant notation $|A|$ must not be confused with the absolute equations. Determinants are only defined for square matrices $A\in\mathbb{R}^{n\times n}$ withe

Determinants are important concepts in linear algebra.A determinant is amathematical object in the analysis and solution of systems of linear i.e., matrices with the same number of rows and columns. In this book, we write the determinant as $\det(\boldsymbol{A})$ or sometimes as $\left|A\right|$ so that

$$\det(\boldsymbol A)=\left|\begin{array}{cccc}a_{11}&a_{12}&\dots&a_{1n}\\a_{21}&a_{22}&\dots&a_{2n}\\\vdots&&\ddots&\vdots\\a_{n1}&a_{n2}&\dots&a_{nn}\end{array}\right|.$$

The determinant of a square matrix $A\in\mathbb{R}^{n\times n}$ is a function that maps $A$ determinan

------------------------------------------------------------------

onto arealnumber Before providing adefinition of the determinant for general $n\times n$ matrices, let us have a look at some motivating examples and define determinants for some special matrices.

### Example 4.1 (Testing for Matrix Invertibility Let us begin with exploring if a square matrix $A$ is invertible (see Sec

tion 2.2.2). For the smallest cases, we already know when a matrix is invertible. If $A$ is a $1\times1$ matrix, i.e., it is a scalar number, then $\boldsymbol{A}=a\implies\boldsymbol{A}^{-1}=\frac{1}{a}$ Thus $a$ $\frac 1a= 1$ holds, if and only if $a\neq0$ For $2\times2$ matrices,by the definition of the inverse (Definition 2.3),we

know that $AA^{-1}=I.$ Then, with (2.24), the inverse of $A$ is

$$\mathbf{A}^{-1}=\frac{1}{a_{11}a_{22}-a_{12}a_{21}}\begin{bmatrix}a_{22}&&-a_{12}\\-a_{21}&&a_{11}\end{bmatrix}.$$

Hence, $A$ is invertible if and only if

$$a_{11}a_{22}-a_{12}a_{21}\neq0\:.$$

This quantity is the determinant of $A\in\mathbb{R}^{2\times2}$ ,i.e.,

$$\det(\boldsymbol A)=\begin{vmatrix}a_{11}&a_{12}\\a_{21}&a_{22}\end{vmatrix}=a_{11}a_{22}-a_{12}a_{21}\:.$$

Example 4.1 points already at the relationship between determinant and the existence of inverse matrices.The next theorem states the same result for $n\times n$ matrices

Theorem 4.1.For any square matrix $A\in\mathbb{R}^{n\times n}$ it holds that $A$ is invertible if and only if $\operatorname*{det}(\boldsymbol{A})\neq0$

We have explicit (closed-form) expressions for determinants of smal matrices in terms of the elements of the matrix.For $n=1$

$$\det(\boldsymbol A)=\det(a_{11})=a_{11}\:.$$

For $n=2$

$$\det(\boldsymbol A)=\begin{vmatrix}a_{11}&a_{12}\\a_{21}&a_{22}\end{vmatrix}=a_{11}a_{22}-a_{12}a_{21}\:,$$

which we have observed in the preceding example

For $n=3$ (known as Sarrus’rule),
$$\begin{aligned}\begin{vmatrix}a_{11}&a_{12}&a_{13}\\a_{21}&a_{22}&a_{23}\\a_{31}&a_{32}&a_{33}\end{vmatrix}&=a_{11}a_{22}a_{33}+a_{21}a_{32}a_{13}+a_{31}a_{12}a_{23}\\&-\:a_{31}a_{22}a_{13}-a_{11}a_{32}a_{23}-a_{21}a_{12}a_{33}\:.\end{aligned}$$

------------------------------------------------------------------

For a memory aid of the product terms in Sarrus’ rule, try tracing the elements of the triple products in the matrix. We call a square matrix $T$ an upper-triangular matrix if $T_{ij}=0$ for

$i>j$ ,i.e., the matrix is zero below its diagonal. Analogously, we define a lower-triangular matrix as a matrix with zeros above its diagonal. For a triangular matrix $T\in\mathbb{R}^{n\times n}$ ,the determinant is the product of the diagonal elements, i.e.,

$$\det(\boldsymbol T)=\prod_{i=1}^nT_{ii}\:.$$

upper-triangular matrix

lower-triangulai matrix

### Example 4.2 (Determinants as Measures of Volume) The notion of a determinant is natural when we consider it as a mapping

from a set of TL vectors spanning an object in $\mathbf{IR}^{n}$ .It turns out that the de terminant $\det(A)$ is the signed volume of an $Tl.$ -dimensional parallelepiped formed by columns of the matrix $A$ For $n=2$ ,the columns of the matrix form a parallelogram; see Fig-

ure 4.2. As the angle between vectors gets smaller, the area of a parallelogram shrinks, too. Consider two vectors $b,g$ that form the columns of a matrix $A=[b,g]$ . Then, the absolute value of the determinant of $A$ is the area of the parallelogram with vertices $\mathbf{0},\boldsymbol{b},\boldsymbol{g},\boldsymbol{b}+\boldsymbol{g}$ . In particular, if $b,g$ are linearly dependent so that $b=\lambda g$ for some $\lambda\in\mathbb{R}$ ,they no longer form a two-dimensional parallelogram. Therefore, the corresponding area is 0. On the contrary, if $b,g$ are linearly independent and are multiples ofFigure 4.3 The the cnonica bas vectors $\boldsymbol{e}_{1},\boldsymbol{e}_{2}$ then they an e wite as $b=\begin{bmatrix}\ddot{b}\\0\end{bmatrix}$ andVonneoahe $g=\begin{bmatrix}0\\g\end{bmatrix}$ and the etermiantis $\begin{vmatrix}b&0\\0&g\end{vmatrix}=bg-0=bg.$ The sign of the determinant indicates the orientation of the spanning

vectors $b,g$ with respect to the standard basis $(\boldsymbol{e}_1,\boldsymbol{e}_2)$ . In our figure, flipping the order to $g,\boldsymbol{b}$ swaps the columns of $A$ and reverses the orientation of the shaded area.This becomes the familiar formula: area = height $x$ length. This intuition extends to higher dimensions.In $\mathbf{R}^{3}$ ,we consider three vectors $r,\boldsymbol{b},\boldsymbol{g}\in\mathbf{R}^{3}$ spanning the edges of a parallelepiped, i.e., a solid with faces that are parallel parallelograms (see Figure 4.3). The absolute value of the determinant of the $3\times3$ matrix $[r$ [r $[ \boldsymbol{r}$, $\boldsymbol{b}$, $g]$ 9] $g]$ is the volume of the solid. Thus, the determinant acts as a function that measures the signed volume formed by column vectors composed in a matrix. Consider the three linearly independent vectors $r,\boldsymbol{g},\boldsymbol{b}\in\mathbb{R}^{3}$ given as

$$\boldsymbol r=\begin{bmatrix}2\\0\\-8\end{bmatrix},\quad\boldsymbol g=\begin{bmatrix}6\\1\\0\end{bmatrix},\quad\boldsymbol b=\begin{bmatrix}1\\4\\-1\end{bmatrix}\:.$$

The determinant is the signed volume of the parallelepiped formed by the columns of the matrix Figure 4.2 The area of the parallelogram (shaded region) spanned by the vectors $b$ and $g$ is $|\det([\boldsymbol{b},\boldsymbol{g}]\rangle|$

![](https://storage.simpletex.cn/view/fdQer2SopeOiPMUrNneo1Vk42nWIof2wQ)

(shaded volume) spanned by vectors $\boldsymbol{r},b,\boldsymbol{g}$ is $|\det([\boldsymbol{r},\boldsymbol{b},\boldsymbol{g}])|$

![](https://storage.simpletex.cn/view/fwGIfHfTeD6rDBu5fCqW5swKWYwXny9aY)

The of the determinant indicates the orientation of the spanning vectors.

------------------------------------------------------------------

$\det(\boldsymbol{A}_{k,j})$ is called a minor and $(-1)^{k+j}\det(\boldsymbol{A}_{k,j})$ a cofactor.

Writing thesevectors as the columns of a matrix

$$A=[r,\:g,\:b]=\begin{bmatrix}2&6&1\\0&1&4\\-8&0&-1\end{bmatrix}$$

allows us to compute the desired volume as

$$V=\left|\det(A)\right|=186\:.$$

Computing the determinant of an $n\times n$ matrix requires a general algo rithm to solve the cases for $n>3$ which we aregoing to explore in the fol lowing.Theorem 4.2below reduces the problem of computing the deter minant of an $n\times n$ matrix to computing the determinant of $(n-1)\times(n-1)$ matrices. By recursively applying the Laplace expansion (Theorem 4.2) we can therefore compute determinants of $n\times n$ matrices by ultimately computing determinants of $2\times2$ matrices

Theorem 4.2 (Laplace Expansion). Consider a matrix $A\in\mathbb{R}^{n\times n}$ .Then for all $j=1,\ldots,n$

1. Expansion along column $j$

$$\det(\boldsymbol A)=\sum_{k=1}^n(-1)^{k+j}a_{kj}\det(\boldsymbol A_{k,j})\:.$$

2.Expansion along row $j$

$$\det(\boldsymbol A)=\sum_{k=1}^n(-1)^{k+j}a_{jk}\det(\boldsymbol A_{j,k})\:.$$

Here $A_{k,j}\in\mathbb{R}^{(n-1)\times(n-1)}$ is the submatrix of $A$ that we obtain when deleting row $k$ and column $j$

### Example 4.3 (Laplace Expansion)

Let us compute the determinant of

$$\boldsymbol A=\begin{bmatrix}1&2&3\\3&1&2\\0&0&1\end{bmatrix}$$

using the Laplace expansion along the first row. Applying (4.13) yield
$$\begin{aligned}\begin{vmatrix}1&2&3\\3&1&2\\0&0&1\end{vmatrix}&=(-1)^{1+1}\cdot1\begin{vmatrix}1&2\\0&1\end{vmatrix}\\&+(-1)^{1+2}\cdot2\begin{vmatrix}3&2\\0&1\end{vmatrix}+(-1)^{1+3}\cdot3\begin{vmatrix}3&1\\0&0\end{vmatrix}\:.\end{aligned}$$

------------------------------------------------------------------

We use (4.6) to compute the determinants of all $2\times2$ matrices and obtain

$$\det(\boldsymbol A)=1(1-0)-2(3-0)+3(0-0)=-5\:.$$

For completeness we can compare thisresult to computing the determi nant using Sarrus’rule (4.7):

$$\det(\boldsymbol{A})=1\cdot1\cdot1+3\cdot0\cdot3+0\cdot2\cdot2-0\cdot1\cdot3-1\cdot0\cdot2-3\cdot2\cdot1=1-6=-5.$$

For $A\in\mathbb{R}^{n\times n}$ the determinant exhibits the following properties:

·The determinant of a matrix product is the product of the corresponding determinants, $\operatorname*{det}(\boldsymbol{A}\boldsymbol{B})=\operatorname*{det}(\boldsymbol{A})$det$(\boldsymbol{B})$ · Determinants are invariant to transposition, i.e., $\det(\boldsymbol{A})=\det(\boldsymbol{A}^{^{\prime}})$ ·If $A$ is regular (invertible), then $\operatorname*{det}(\boldsymbol{A}^{-1})=\frac{1}{\operatorname*{det}(\boldsymbol{A})}$ Similar matrices (Definition 2.22) possess the same determinant. Therefore, for a linear mapping $\Phi:V\to V$ all transformation matrices $A_{\Phi}$ of $\Phi$ have the same determinant. Thus, the determinant is invariant to the choice of basis of a linear mapping ·Addinga multiple of a column/row to another one does not change $\det(\boldsymbol{A})$ · Multiplication of a column/row with $\lambda\in$ R scales $\det(\boldsymbol{A})$ by $\lambda$ .In particular, $\operatorname*{det}(\lambda\boldsymbol{A})=\lambda^{n}\operatorname*{det}(\boldsymbol{A})$ · Swapping two rows/columns changes the sign of $\det(\boldsymbol{A})$

Because of the last three properties,we can use Gaussian elimination (see Section 2.1) to compute $\det(\boldsymbol{A})$ by bringing $A$ into row-echelon form. We can stop Gaussian elimination when we have $A$ in a triangular form where the elements below the diagonal are all 0.Recall from(4.8) that the determinant of a triangularmatrix is the product of the diagonal elements.

Theorem 4.3.A square matrix $A\in\mathbb{R}^{n\times n}$ has $\operatorname*{det}(\boldsymbol{A})\neq0$ if andonly if $\operatorname{rk}(\boldsymbol{A})=n$ .In other words, $A$ is invertible if and only if it is full rank

When mathematics was mainly performed by hand, the determinant calculation was considered an essential way to analyze matrix invertibil ity. However, contemporary approaches in machine learning use direct numerical methods that superseded the explicit calculation of the determinant.For example,in Chapter 2,we learned that inverse matrices can be computed by Gaussian elimination. Gaussian elimination can thus be used to compute the determinant of a matrix. Determinants will play an important theoretical role for the following

sections, especially when we learn about eigenvalues and eigenvectors (Section 4.2) through the characteristic polynomial

Definition 4.4.The trace of a square matrix $A\in\mathbb{R}^{n\times n}$ is defined as

------------------------------------------------------------------

The trace is invariant under cyclic permutations

$$\operatorname{tr}(A):=\sum_{i=1}^na_{ii}\:,$$

i.e., the trace is the sum of the diagonal elements of $A$

The trace satisfies the following properties

· tr$(\boldsymbol{A}+\boldsymbol{B})=$tr$(\boldsymbol{A})+$tr$(\boldsymbol{B})$ for $\boldsymbol{A},\boldsymbol{B}\in\mathbb{R}^{n\times n}$ · tr$(\alpha\boldsymbol{A})=\alpha$tr$(\boldsymbol{A}),\alpha\in\mathbb{R}$ for $A\in\mathbb{R}^{n\times n}$ · tr$(I_n)=n$ tr$(AB)=$tr$(BA)$ for $A\in\mathbb{R}^{n\times k},\boldsymbol{B}\in\mathbb{R}^{k\times n}$

It can be shown that only one function satisfies these four properties to gether - the trace (Gohberg et al., 2012) The properties of the trace of matrix products are more general. Specif

ically, the trace is invariant under cyclic permutations, i.e.,

$$\mathrm{tr}(AKL)=\mathrm{tr}(KLA)$$

for matrices $A\in\mathbb{R}^{\alpha\times k},\boldsymbol{K}\in\mathbb{R}^{k\times l},\boldsymbol{L}\in\mathbb{R}^{l\times a}.$ This property generalizes to products of an arbitrary number of matrices. As a special case of (4.19), it follows that for two vectors $\boldsymbol{x},y\in\mathbb{R}^{n}$

$$\mathrm{tr}(\boldsymbol{x}\boldsymbol{y}^\top)=\mathrm{tr}(\boldsymbol{y}^\top\boldsymbol{x})=\boldsymbol{y}^\top\boldsymbol{x}\in\mathbb{R}\:.$$

Given a linear mapping $\Phi:V\rightarrow V$ ,where $V$ is a vector space,we define the trace of this map by using the trace of matrix representation of $\Phi$ .For a given basis of $V$ ,we can describe $\Phi$ by means of the transfor mation matrix $A$ .Then the trace of $\Phi$ is the trace of $A$ For a different basis of $V$ ,it holds that the corresponding transformation matrix $B$ of $\Phi$ can be obtained by a basis change of the form $S^{-1}AS$ for suitable S (see Section 2.7.2). For the corresponding trace of $\Phi$ , this means

$$\operatorname{tr}(B)=\operatorname{tr}(S^{-1}AS)\stackrel{(4.19)}{=}\operatorname{tr}(ASS^{-1})=\operatorname{tr}(A)\:.$$

Hence,while matrix representations of linear mappings are basis depen dent the trace of a linear mapping $\Phi$ is independent of the basis.

In this section, we covered determinants and traces as functions char acterizing a square matrix.Taking together our understanding of determi nants and traces we can now define an important equation describing a matrix $A$ in terms of a polynomial, which we will use extensively in the following sections,

Definition 4.5 (Characteristic Polynomial). For $\lambda\in\mathbb{R}$ and a square ma trix $A\in\mathbb{R}^{n\times n}$

$$\begin{aligned}
p_{A}(\lambda)& :=\det(A-\lambda I) \\
&=c_{0}+c_{1}\lambda+c_{2}\lambda^{2}+\cdots+c_{n-1}\lambda^{n-1}+(-1)^{n}\lambda^{n}\:,
\end{aligned}$$

$c_{0},\ldots,c_{n-1}\in\mathbb{R}$ ,is the characteristic polynomial of $A$ . In particular

characteristic polynomial

------------------------------------------------------------------

Eigen is a German word meaning "characteristic" “self", or “own”

eigenvalue eigenvectot

eigenvalue equatior

$$\begin{aligned}
c_{0}& =\det(A)\:, \\
c_{n-1}& =(-1)^{n-1}\mathrm{tr}(A)\:. 
\end{aligned}$$

The characteristic polynomial (4.22a) will allow us to compute eigenvalues and eigenvectors, covered in the next section.

## 4.2 Eigenvalues and Eigenvectors

We will now get to know a new way to characterize a matrix and its associated linear mapping. Recall from Section 2.7.1 that every linear mapping has a unique transformation matrix given an ordered basis. We can interpret linear mappings and their associated transformation matrices by performing an “eigen” analysis. As we will see, the eigenvalues of a linear mapping will tell us how a special set of vectors, the eigenvectors, is transformed by the linear mapping

Definition 4.6. Let $A\in\mathbb{R}^{n\times n}$ be a square matrix. Then $\lambda\in\mathbb{R}$ is an eigenvalue of $A$ and $x\in\mathbb{R}^{n}\backslash\{\mathbf{0}\}$ is the corresponding eigenvector of $A$ if

$$Ax=\lambda x\:.$$

We call(4.25) the eigenvalue equation.

Remark. In the linear algebra literature and software,it is often a convention that eigenvalues are sorted in descending order, so that the largest eigenvalue and associated eigenvector are called the first eigenvalue and its associated eigenvector, and the second largest called the second eigenvalue and its associated eigenvector, and so on. However, textbooks and publications may have different or no notion of orderings. We do not want to presume an ordering in this book if not stated explicitly $\diamondsuit$

The following statements are equivalent:

$\lambda$ is an eigenvalue of $A\in\mathbb{R}^{n\times n}$ · There exists an $x\in\mathbb{R}^n\backslash\{\mathbf{0}\}$ with $Ax=\lambda x$ ,or equivalently, $(A-$ $\lambda I_{n})\boldsymbol{x}=0$ can be solved non-trivially, i.e., $x\neq0$ $\operatorname{rk}(\boldsymbol{A}-\lambda\boldsymbol{I}_{n})<n$ · $\operatorname*{det}(\boldsymbol{A}-\lambda\boldsymbol{I}_{n})=0$

Definition 4.7 (Collinearity and Codirection).Two vectors that point in the same direction are called codirected. Two vectors are collinear if they point in the same or the opposite direction

Remark (Non-uniqueness of eigenvectors). If $JL$ is an eigenvector of $A$ associated with eigenvalue $\lambda$ , then for any $c\in\mathbb{R}\backslash\{0\}$ it holds that CuE is an eigenvector of $A$ with the same eigenvalue since

$$\boldsymbol{A}(c\boldsymbol{x})=c\boldsymbol{A}\boldsymbol{x}=c\lambda\boldsymbol{x}=\lambda(c\boldsymbol{x})\:.$$

Thus, all vectors that are collinear to $3U$ are also eigenvectors of $A$

codirected collinear

------------------------------------------------------------------

algebraic multiplicity

eigenspace eigenspectrum spectrum

Theorem 4.8. $\lambda\in\mathbb{R}$ is an eigenvalue of $A\in\mathbb{R}^{n\times n}$ if andonlyif $\lambda$ is $a$ root of the characteristic polynomial $p_{\boldsymbol{A}}(\lambda)$ of $A$

Definition 4.9.Let a square matrix $A$ have an eigenvalue $\lambda_{i}$ .The algebrai multiplicity of $\lambda_{i}$ is the number of times the root appears in the character istic polynomial

Definition 4.10 (Eigenspace and Eigenspectrum). For $A\in\mathbb{R}^{n\times n}$ ,the set of all eigenvectors of $A$ associated with an eigenvalue $\lambda$ spans a subspace of $\mathbf{IR}^{n}$ ,which is called the eigenspace of $A$ with respect to $\lambda$ and is denoted by $E_{\lambda}$ . The set of all eigenvalues of $A$ is called the eigenspectrum,or just spectrum, of $A$

If $\lambda$ is an eigenvalueof $A\in\mathbb{R}^{n\times n}$ ,then the corresponding eigenspace $E_{\lambda}$ is the solution space of the homogeneous system of linear equations $(A-\lambda I)\boldsymbol{x}=0$ . Geometrically, the eigenvector corresponding to a nonzerc eigenvalue points in a direction that is stretched by the linear mapping The eigenvalue is the factor by which it is stretched. If the eigenvalue is negative, the direction of the stretching is flipped.

### Example 4.4 (The Case of the Identity Matrix) The identity matrix $I\in\mathbb{R}^{n\times n}$ has characteristic polynomial $p_{I}(\lambda)=$

$\operatorname*{det}(\boldsymbol{I}-\lambda\boldsymbol{I})=(1-\lambda)^{n}=0$ which has only one eigenvalue $\lambda=1$ that oc curs $7L$ times. Moreover, $Ix=\lambda\boldsymbol{x}=1\boldsymbol{x}$ holds for all vectors $x\in\mathbb{R}^n\backslash\{0\}$ Because of this, the sole eigenspace $E_{1}$ of the identity matrix spans $m$ dimensions, and all $7l$ standard basis vectors of $\mathbf{IR}^{n}$ are eigenvectors of $I$

Useful properties regarding eigenvalues and eigenvectors include the following

· A matrix $A$ and its transpose $A^{\top}$ possess the same eigenvalues, but not necessarily the same eigenvectors ·The eigenspace $E_{\lambda}$ is the null space of $A-\lambda I$ since

$$\begin{aligned}
Ax=\lambda\boldsymbol{x}& \Longleftrightarrow Ax-\lambda\boldsymbol{x}=\boldsymbol{0} \\
&\iff(A-\lambda\boldsymbol{I})\boldsymbol{x}=\boldsymbol{0}\iff\boldsymbol{x}\in\ker(\boldsymbol{A}-\lambda\boldsymbol{I}).
\end{aligned}$$

·Similar matrices (see Definition 2.22) possess the same eigenvalues Therefore, a linear mapping $\Phi$ has eigenvalues that are independent of the choice of basis of its transformation matrix. This makes eigenvalues together with the determinant and the trace, key characteristic param eters of a linear mapping as they are all invariant under basis change. - Symmetric, positive definite matrices always have positive, real eigen values.

------------------------------------------------------------------

## Example 4.5Computing Eigenvalues,Eigenvectors,and Eigenspaces) Let us find the eigenvalues and eigenvectors of the $2\times2$ matrix

$$\boldsymbol A=\begin{bmatrix}4&2\\1&3\end{bmatrix}\:.$$

Step 1: Characteristic Polynomial. From our definition of the eigen vector $x\neq0$ and eigenvalue $\lambda$ of $A$ ,there willbe a vector such that $Ax=\lambda x$ ,i.e., $(\boldsymbol{A}-\lambda\boldsymbol{I})\boldsymbol{x}=\boldsymbol{0}$ .Since $x\neq\mathbf{0}$ ,this requires that the kernel (null space) of $A-\lambda I$ contains more elements than just O.This means that $A-\lambda I$ is not invertible and therefore $\operatorname*{det}(\boldsymbol{A}-\lambda\boldsymbol{I})=0$ . Hence, we need to compute the roots of the characteristic polynomial (4.22a) to find the eigenvalues. Step 2: Eigenvalues, The characteristic polynomial is

$$\begin{aligned}
p_{A}(\lambda)& =\det(A-\lambda I) \\
&=\det\left(\begin{bmatrix}4&2\\1&3\end{bmatrix}-\begin{bmatrix}\lambda&0\\0&\lambda\end{bmatrix}\right)=\begin{vmatrix}4-\lambda&2\\1&3-\lambda\end{vmatrix} \\
&=(4-\lambda)(3-\lambda)-2\cdot1\:.
\end{aligned}$$

We factorize the characteristic polynomial and obtain

$$p(\lambda)=(4-\lambda)(3-\lambda)-2\cdot1=10-7\lambda+\lambda^2=(2-\lambda)(5-\lambda)$$

giving the roots $\lambda_{1}=2$ and $\lambda_{2}=5$

Step 3: Eigenvectors and Eigenspaces. We find the eigenvectors that correspond to these eigenvalues by looking at vectors $3E$ such that

$$\begin{bmatrix}4-\lambda&2\\1&3-\lambda\end{bmatrix}\boldsymbol x=\boldsymbol0\:.$$

For $\lambda=5$ we obtain

$$\begin{bmatrix}4-5&2\\1&3-5\end{bmatrix}\begin{bmatrix}x_1\\x_2\end{bmatrix}=\begin{bmatrix}-1&2\\1&-2\end{bmatrix}\begin{bmatrix}x_1\\x_2\end{bmatrix}=\mathbf{0}\:.$$

We solve this homogeneous system and obtain a solution space

$$E_5=\mathrm{span}[\begin{bmatrix}2\\1\end{bmatrix}]\:.$$

This eigenspace is one-dimensional as it possesses a single basis vector Analogously, we find the eigenvector for $\lambda=2$ by solving the homoge-

neous system of equations

$$\begin{bmatrix}4-2&2\\1&3-2\end{bmatrix}\boldsymbol x=\begin{bmatrix}2&2\\1&1\end{bmatrix}\boldsymbol x=\boldsymbol0\:.$$

------------------------------------------------------------------

geometric multiplicity

In geometry, the area-preserving properties of this type of shearing parallel to an axis is also known as Cavalieri's principled of equal areas for parallelograms (Katz, 2004).

Thismans any vector $x=\begin{bmatrix}x_1\\x_2\end{bmatrix}$ ,where $x_{2}=-x_{1}$ such as $\begin{bmatrix}1\\-1\end{bmatrix}$ ,is an eigenvector with eigenvalue 2.The corresponding eigenspace is given as
$$E_2=\operatorname{span}[\begin{bmatrix}1\\-1\end{bmatrix}]\:.$$

The two eigenspaces $E_{5}$ and $E_{2}$ in Example 4.5 are one-dimensiona as they are each spanned by a single vector. However, in other cases we may have multiple identical eigenvalues (see Definition 4.9) and the eigenspace may have more than one dimension.

Definition 4.11. Let $\lambda_{i}$ be an eigenvalue of a square matrix $A$ .Then the geometric multiplicity of. $\lambda_{i}$ is the number of linearly independent eigenvectors associated with $\lambda_{i}$ .In other words,it is the dimensionality of the eigenspace spanned by the eigenvectors associated with $\lambda_{i}$

Remark.A specific eigenvalue's geometric multiplicity must be at least one because every eigenvalue has at least one associated eigenvector. An eigenvalue's geometric multiplicity cannot exceed its algebraic multiplic $\diamondsuit$ ity, but it may be lower.

### Example 4.6 The matrix $A=\begin{bmatrix}2&1\\0&2\end{bmatrix}$ has two repeated eigenvalues $\lambda_{1}=\lambda_{2}=2$ and ar

algebraic multiplicity of 2. The eigenvalue has, however, only one distinct uni gigenvetor $x_1=\begin{bmatrix}1\\0\end{bmatrix}$ and, tus cometie mutiplit it

### Graphical Intuition in Two Dimensions

Let us gain some intuition for determinants, eigenvectors, and eigenval ues using different linear mappings. Figure 4.4 depicts five transformatior matrices $A_{1},\ldots,A_{5}$ and their impact on a square grid of points, centered at the origin:

. $A_1=\begin{bmatrix}\frac{1}{2}&0\\0&2\end{bmatrix}$ The directon o the swo ieanvetors corespon tothe canonical basis vectors in $\mathbf{R}^{2}$ ,i.e.,to two cardinal axes. The vertical axis is extended by a factor of 2 (eigenvalue $\lambda_{1}=2$ ),and the horizontal axis is compressed by factor $\frac{1}{2}$ (eigenvalue $\lambda_{2}=\frac{1}{2}.$ 0. The mapping is area preserving $(\operatorname*{det}(\boldsymbol{A}_{1})=1=2\cdot\frac{1}{2})$ $\boldsymbol{A}_2=\begin{bmatrix}1&\frac{1}{2}\\0&1\end{bmatrix}$ corespons o a shearing maping ie it shearsthe points along the horizontal axis to the right if they are on the positive

------------------------------------------------------------------

![](https://storage.simpletex.cn/view/fziCi5ZxZByd4EIVmQ4rrBgEkgWIQ4I16)

half of the vertical axis, and to the left vice versa. This mapping is area preserving $(\det(\boldsymbol{A}_{2})=1)$ .The eigenvalue $\lambda _{1}$ = 1 = $\lambda _{2}$ is repeated and the eigenvectors are collinear (drawn here for emphasis in two opposite directions). This indicates that the mapping acts only along one direction (the horizontal axis). · $\boldsymbol{A}_{3}= \begin{bmatrix} \cos ( \frac \pi 6) & - \sin ( \frac \pi 6) \\ \sin ( \frac \pi 6) & \cos ( \frac \pi 6) \end{bmatrix} =$ $\frac 12\begin{bmatrix} \sqrt {3}& - 1\\ 1& \sqrt {3}\end{bmatrix}$ The matrix $A_3$ rotate the

points by $\frac{\pi}{6}$rad$=30^\circ$ counter-clockwise and has only complex eigen-

values,reflecting that the mapping is a rotation (hence,no eigenvectors are drawn).A rotation has to be volume preserving, and so the deter minant is 1. For more details on rotations, we refer to Section 3.9. . $A_{4}=\begin{bmatrix}1&-1\\-1&1\end{bmatrix}$ represens a maping in he tandad ais tha ol lapses a two-dimensional domain onto one dimension.Since one eigen

Figure 4.4 Determinants and eigenspaces Overview of five linear mappings and their associated transformatior matrices $A_{i}\in\mathbb{R}^{2\times2}$ projecting 400 color-coded points $\boldsymbol{x}\in\mathbb{R}^{2}$ (left column) onto targe points $A_i\boldsymbol{x}$ (right column). The central column depicts the first eigenvector stretched by its associatec eigenvalue $\lambda_1$ ,and the second eigenvectot stretched by its eigenvalue $\lambda_2$ .Each row depicts the effect of one of five transformatior matrices $A_{i}$ with respect to the standard basis

------------------------------------------------------------------

Figure 4.5 Caenorhabditis elegans neural network (Kaiser and Hilgetag, 2006).(a) Symmetrized connectivity matrix; (b) Eigenspectrum

value is 0 ,the space in direction of the (blue) eigenvector corresponding to $\lambda_{1}=0$ collapses, while the orthogonal (red) eigenvector stretches. space by a factor $\lambda_{2}=2$ .Therefore, the area of the image is 0. · $\boldsymbol{A}_5=\begin{bmatrix}1&\frac{1}{2}\\\frac{1}{2}&1\end{bmatrix}$ $| \det ( \boldsymbol{A}_5) |$ = $\frac 34$ $75\%$ of $\lambda_{2}$ by a factor 1.5 and compresses it along the orthogonal (blue) eigenvector by a factor 0.5.

### Example 4.7 (Eigenspectrum of a Biological Neural Network)

![](https://storage.simpletex.cn/view/ffbkiv4YnB5iNUqilQ1hUTAqSoF34MHNF)

Methods to analyze and learn from network data are an essential component of machine learning methods. The key to understanding networks is the connectivity between network nodes, especially if two nodes are connected to each other or not.In data science applications, it is often useful to study the matrix that captures this connectivity data. We build a connectivity/adjacency matrix $A\in\mathbb{R}^{277\times277}$ of the complete

neural network of the worm C.Elegans.Each row/column represents one of the 277 neurons of this worm’s brain.The connectivity matrix $A$ has a value of $a_{ij}=1$ if neuron $i$ talks to neuron $j$ through a synapse, and $a_{ij}=0$ otherwise. The connectivity matrix is not symmetric, which implies that eigenvalues may not be real valued. Therefore, we compute a symmetrized version of the connectivity matrix as $A_{sym}:=A+A^{'}.$ This new matrix $A_{sym}$ is shown in Figure 4.5(a) and has a nonzero value $u_{ij}$ if and only if two neurons are connected (white pixels), irrespective of the direction of the connection. In Figure 4.5(b), we show the corresponding eigenspectrum of $A_{sym}$ . The horizontal axis shows the index of the eigenvalues, sorted in descending order. The vertical axis shows the corresponding eigenvalue. The $S$ -like shape of this eigenspectrum is typical for many biological neural networks. The underlying mechanism responsible for this is an area of active neuroscience research

------------------------------------------------------------------

Theorem 4.12. The eigenvectors $x_{1},\ldots,x_{n}$ ofa matrix $A\in\mathbb{R}^{n\times n}$ with $7L$ distinct eigenvalues $\lambda_{1},\ldots,\lambda_{\mathrm{n}}$ are linearly independent

This theorem states that eigenvectors of a matrix with $TL$ distinct eigen values form a basis of $\mathbf{R}^{n}$

Definition 4.13.A square matrix $A\in\mathbb{R}^{n\times n}$ is defective if it possesses defective fewer than $7l$ linearly independent eigenvectors.

A non-defective matrix $A\in\mathbb{R}^{n\times n}$ does not necessarily require 72 distinct eigenvalues,but it does require that the eigenvectors form a basis of $\mathbf{R}^{n}$ . Looking at the eigenspaces of a defective matrix, it follows that the sum of the dimensions of the eigenspaces is less than $7t$ Specifically, a defective matrix has at least one eigenvalue $\lambda_{i}$ with an algebraic multiplicity $m>1$ and a geometric multiplicity of less than $777L$

Remark. A defective matrix cannot have. $7L$ distinct eigenvalues, as distinct eigenvalues have linearly independent eigenvectors (Theorem 4.12). $\diamondsuit$

Theorem 4.14.Given a matrix $A\in\mathbb{R}^{m\times n}$ ,we can always obtaina symmetric, positive semidefinite matrix $S\in\mathbb{R}^{n\times n}$ by defining

$$S:=A^{\top}A.$$

Remark. If rk$(A)=n$ ,then $S:=A^{'}A$ is symmetric, positive definite.

Understanding why Theorem 4.14 holds is insightful for how we can use symmetrized matrices: Symmetry requires $S=S^{|}$ ,and by inserting (4.36) we obtain $S=A^{\top}A=A^{\top}(A^{\top})^{\top}=(A^{\top}A)^{\top}=S^{\top}$ More over, positive semidefiniteness (Section 3.2.3) requires that $x^\top Sx\geqslant0$ and inserting (4.36) we obtain $x^\top Sx=x^\top A^\top Ax=(x^\top\boldsymbol{A}^\top)(\boldsymbol{A}x)=$ $(\boldsymbol{A}x)^{\top}(\boldsymbol{A}x)\geqslant0$ ,because the dot product computes a sum of squares (which are themselves non-negative)

Theorem 4.15 (Spectral Theorem). If $A\in\mathbb{R}^{n\times n}$ is symmetric, there exists an orthonormal basis of the corresponding vector space $V$ consisting of eigenvectors of $A$ , and each eigenvalue is real

A direct implication of the spectral theorem is that the eigendecomposition of a symmetric matrix $A$ exists (with real eigenvalues), and that we can find an ONB of eigenvectors so that $A=PDP^{\prime}$ ,where $D$ is diagonal and the columns of $P$ contain the eigenvectors

### Example 4.8 Consider the matrix

$$\boldsymbol A=\begin{bmatrix}3&2&2\\2&3&2\\2&2&3\end{bmatrix}\:.$$

------------------------------------------------------------------

The characteristic polynomial of $A$ is

$$p_{A}(\lambda)=-(\lambda-1)^{2}(\lambda-7)\:,$$

so that we obtain the eigenvalues $\lambda _1$ = 1 and $\lambda_2=7$ ，where $\lambda_1$ isa repeated eigenvalue. Following our standard procedure for computing eigenvectors, we obtain the eigenspaces

$$E_1=\mathrm{span}[\underbrace{\begin{bmatrix}-1\\1\\0\end{bmatrix}}_{=:\boldsymbol{x}_1},\underbrace{\begin{bmatrix}-1\\0\\1\end{bmatrix}}_{=:\boldsymbol{x}_2}],\quad E_7=\mathrm{span}[\underbrace{\begin{bmatrix}1\\1\\1\end{bmatrix}}_{=:\boldsymbol{x}_3}]\:.$$

We see that $U3$ is orthogonal to both $x_1$ and $\mathcal{L}_{2}$ .However, since $\boldsymbol{x}_1^\top\boldsymbol{x}_2=$ $1\neq0$ ，they are not orthogonal. The spectral theorem (Theorem 4.15) states that there exists an orthogonal basis,but the one we have is not orthogonal. However, we can construct one.

To construct such a basis, we exploit the fact that $\boldsymbol{U}_{1},\boldsymbol{L}_{2}$ are eigenvec tors associatedwith the same eigenvalue $\lambda$ . Therefore, for any $\alpha,\beta\in\mathbb{R}$ it holds that

$$A(\alpha\boldsymbol{x}_1+\beta\boldsymbol{x}_2)=A\boldsymbol{x}_1\alpha+\boldsymbol{A}\boldsymbol{x}_2\beta=\lambda(\alpha\boldsymbol{x}_1+\beta\boldsymbol{x}_2)\:,$$

i.e., any linear combination of $iL1$ and ${\mathcal{U}}_{2}$ is also an eigenvector of $A$ associated with $\lambda$ .The Gram-Schmidt algorithm (Section 3.8.3) is a method for iteratively constructing an orthogonal/orthonormal basis from a set of basis vectors using such linear combinations. Therefore, even if ${\boldsymbol{x}}_{1}$ and $x_{2}$ are not orthogonal, we can apply the Gram-Schmidt algorithm and find eigenvectors associated with $\lambda_{1}=1$ that are orthogonal to each other (and to $U3$ ). In our example, we will obtain

$$\boldsymbol{x}_1'=\begin{bmatrix}-1\\1\\0\end{bmatrix},\quad\boldsymbol{x}_2'=\frac12\begin{bmatrix}-1\\-1\\2\end{bmatrix}\:,$$

which are orthogonal to each other,orthogonal to ${\mathcal{L}}_{3}$ ,and eigenvectors of $A$ associated with $\lambda_{1}=1$

Before we conclude our considerations of eigenvalues and eigenvector it is useful to tie these matrix characteristics together with the concepts of the determinant and the trace

Theorem 4.16. The determinant of a matrix $A\in\mathbb{R}^{n\times n}$ is theproductof its eigenvalues, i.e.,

$$\det(\boldsymbol A)=\prod_{i=1}^n\lambda_i\:,$$

where $\lambda_{i}\in\mathbb{C}$ are (possibly repeated) eigenvalues of $A$

------------------------------------------------------------------

![](https://storage.simpletex.cn/view/fXRkwkGT74QqvwOXnxb076zzknYKTPgot)

Theorem 4.17. The trace of a matrix $A\in\mathbb{R}^{n\times n}$ is the sum ofits eigenval ues, i.e.,

$$tr(A)=\sum_{i=1}^{n}\lambda_{i}\:,$$

where $\lambda_{i}\in\mathbb{O}$ are (possibly repeated) eigenvalues of $A$

Let us provide a geometric intuition of these two theorems. Consider a matrix $A\in\mathbb{R}^{2\times2}$ that possesses two linearly independent eigenvectors ${\mathcal{L}}_{1},{\mathcal{L}}_{2}$ .For this example, we assume $(\boldsymbol{x}_1,\boldsymbol{x}_2)$ are an ONB of $\mathbf{R}^{2}$ so that they are orthogonal and the area of the square they span is 1; see Figure 4.6. From Section 4.1, we know that the determinant computes the change of area of unit square under the transformation $A$ .In this example, we can compute the change of area explicitly: Mapping the eigenvectors using $A$ gives us vectors $\boldsymbol{v}_1=\boldsymbol{A}x_1=\lambda_1\boldsymbol{x}_1$ and $\boldsymbol{v}_{2}=Ax_{2}=\lambda_{2}\boldsymbol{x}_{2}$ ,i.e., the new vectors $v_{i}$ are scaled versions of the eigenvectors ${\mathcal{L}}_{i}$ ,and the scaling factors are the corresponding eigenvalues $\lambda_{i}$ . $v_{1},v_{2}$ are still orthogonal and the area of the rectangle they span is $\left|\lambda_{1}\lambda_{2}\right|$ Given that $x_1,x_2$ (in our example) are orthonormal, we can directly

compute the perimeter of the unit square as 2(1+1) .Mapping the eigenvectors using $A$ creates a rectangle whose perimeter is $2(|\lambda_{1}|+|\lambda_{2}|)$ Therefore, the sum of the absolute values of the eigenvalues tells us how the perimeter of the unit square changes under the transformation matrix $A$

### Example 4.9 (Google's PageRank -Webpages as Eigenvectors) Google uses the eigenvector corresponding to the maximal eigenvalue of

a matrix $A$ to determine the rank of a page for search. The idea for the PageRank algorithm, developed at Stanford University by Larry Page and Sergey Brin in 1996, was that the importance of any web page can be approximated by the importance of pages that link to it. For this, they write down all web sites as a huge directed graph that shows which page links to which. PageRank computes the weight (importance) $x_i\geqslant0$ of a web site $a_i$ by counting the number of pages pointing to $u_{i}$ . Moreover, PageRank takes into account the importance of the web sites that link to $u_{i}$ . The navigation behavior of a user is then modeled by a transition matrix $A$ of this graph that tells us with what (click) probability somebody will end up

Figure 4.6 Geometric interpretation of eigenvalues. The eigenvectors of $A$ get stretched by the corresponding eigenvalues. The area of the unit square changes by $|\lambda_1\lambda_2|$ ,the perimeter change by a factor of $\frac{1}{2}(|\lambda_1|+|\lambda_2|)$

------------------------------------------------------------------

PageRank

on a different web site. The matrix $A$ has the property that for any initial rank/importance vector $JE$ of a web site the sequence $\boldsymbol{x},\boldsymbol{A}x,\boldsymbol{A}^2\boldsymbol{x},\ldots$ converges to a vector $x^*$ .This vector is called the PageRank and satisfies

$Ax^*=x^*$ ,i.e.,it is an eigenvector (with corresponding eigenvalue 1) of $A$ . After normalizing $x^*$ , such that $\|\boldsymbol{x}^*\|=1$ ,wecan interpret the entries as probabilities. More details and different perspectives on PageRank can be found in the original technical report (Page et al., 1999).

Cholesky decompositione Cholesky factorization

### 4.3 Cholesky Decomposition

There are many ways to factorize special types of matrices that we en counter often in machine learning.In the positive real numbers,we have the square-root operation that gives us a decomposition of the number into identical components, e.g., $9=3\cdot3$ .For matrices, we need to be careful that we compute a square-root-like operation on positive quantities. For symmetric, positive definite matrices (see Section 3.2.3), we can. choose from a number of square-root equivalent operations.The Cholesky decomposition/Cholesky factorization provides a square-root equivalent op. eration on symmetric, positive definite matrices that is useful in practice

Theorem 4.18 (Cholesky Decomposition). A symmetric, positive definite matrix $A$ can be factorized into a product $A=LL^{\prime}$ ，where $L$ is a lower triangular matrix with positive diagonal elements

$$\begin{bmatrix}a_{11}&\cdots&a_{1n}\\\vdots&\ddots&\vdots\\a_{n1}&\cdots&a_{nn}\end{bmatrix}=\begin{bmatrix}l_{11}&\cdots&0\\\vdots&\ddots&\vdots\\l_{n1}&\cdots&l_{nn}\end{bmatrix}\begin{bmatrix}l_{11}&\cdots&l_{n1}\\\vdots&\ddots&\vdots\\0&\cdots&l_{nn}\end{bmatrix}.$$

$L$ is called the Choleskyfactorof $A$ ,and $L$ is unique

### Example 4.10 (Cholesky Factorization

Consider a symmetric, positive definite matrix $A\in\mathbb{R}^{3\times3}$ .We are inter ested in finding its Cholesky factorization $A=LL^{\top}$ ,i.e.,

$$\boldsymbol A=\begin{bmatrix}a_{11}&a_{21}&a_{31}\\a_{21}&a_{22}&a_{32}\\a_{31}&a_{32}&a_{33}\end{bmatrix}=\boldsymbol L\boldsymbol L^\top=\begin{bmatrix}l_{11}&0&0\\l_{21}&l_{22}&0\\l_{31}&l_{32}&l_{33}\end{bmatrix}\begin{bmatrix}l_{11}&l_{21}&l_{31}\\0&l_{22}&l_{32}\\0&0&l_{33}\end{bmatrix}.$$

Multiplying out the right-hand side yields
$$\boldsymbol A=\begin{bmatrix}l_{11}^2&l_{21}l_{11}&l_{31}l_{11}\\l_{21}l_{11}&l_{21}^2+l_{22}^2&l_{31}l_{21}+l_{32}l_{22}\\l_{31}l_{11}&l_{31}l_{21}+l_{32}l_{22}&l_{31}^2+l_{32}^2+l_{33}^2\end{bmatrix}\:.$$

Cholesky factor

------------------------------------------------------------------

Comparing the left-hand side of (4.45) and the right-hand side of (4.46) shows that there is a simple pattern in the diagonal elements $l_{ii}$

$$l_{11}=\sqrt{a_{11}}\:,\quad l_{22}=\sqrt{a_{22}-l_{21}^{2}}\:,\quad l_{33}=\sqrt{a_{33}-(l_{31}^{2}+l_{32}^{2})}\:.$$

Similarly for the elements below the diagonal ( $l_{ij}$ ,where $i>j$ ), there is also a repeating pattern:

$$l_{21}=\frac{1}{l_{11}}a_{21}\:,\quad l_{31}=\frac{1}{l_{11}}a_{31}\:,\quad l_{32}=\frac{1}{l_{22}}(a_{32}-l_{31}l_{21})\:.$$

Thus, we constructed the Cholesky decomposition for any symmetric, positive definite $3\times3$ matrix. The key realization is that we can backward calculate what the components $l_{ij}$ for the $L$ should be, given the values $u_{ij}$ for $A$ and previously computed values of $l_{ij}$

The Cholesky decomposition is an important tool for the numerical computations underlying machine learning. Here, symmetric positive def-. inite matrices require frequent manipulation, e.g., the covariance matrix of a multivariate Gaussian variable (see Section 6.5) is symmetric, positive definite. The Cholesky factorization of this covariance matrix allows us to generate samples from a Gaussian distribution. It also allows us to perform a linear transformation of random variables, which is heavily exploited. when computing gradients in deep stochastic models, such as the variational auto-encoder (Jimenez Rezende et al., 2014; Kingma and Welling, 2014).The Cholesky decomposition also allows us to compute determinants very efficiently. Given the Cholesky decomposition $A=LL^{|}$ ，we know that $\det(\boldsymbol{A})=\det(\boldsymbol{L})\det(\boldsymbol{L}^{\top})=\det(\boldsymbol{L})^{2}$ Since $L$ is a triangular matrix, the determinant is simply the product of its diagonal entries so that $\operatorname*{det}(\boldsymbol{A})=\prod_{i}l_{ii}^{2}$ . Thus, many numerical software packages use the Cholesky decomposition to make computations more efficient..

### 4.4 Eigendecomposition and Diagonalization

A diagonal matrix is a matrix that has value zero on all off-diagonal ele-diagonal matrix ments, i.e., they are of the form

$$\boldsymbol{D}=\begin{bmatrix}c_1&\cdots&0\\\vdots&\ddots&\vdots\\0&\cdots&c_n\end{bmatrix}.$$

They allow fast computation of determinants, powers, and inverses.The determinant is the product of its diagonal entries, a matrix power $D^{k}$ is given by each diagonal element raised to the power $k$ ,and the inverse $D^{-1}$ is the reciprocal of its diagonal elements if all of them are nonzero.

In this section,wewill discuss how to transform matrices into diagonal

------------------------------------------------------------------

form. This is an important application of the basis change we discussed in Section 2.7.2 and eigenvalues from Section 4.2. Recall that two matrices $A,D$ are similar (Definition 2.22) if there ex-

 ists an invertible matrix $P$ , such that $D=P^{-1}AP$ More specifically, we will look at matrices $A$ that are similar to diagonal matrices $D$ that contain the eigenvalues of $A$ on the diagonal.

Definition 4.19 (Diagonalizable). A matrix $A\in\mathbb{R}^{n\times n}$ is diagonalizable if it is similar to a diagonal matrix, i.e., if there exists an invertible matrix $P\in\mathbb{R}^{n\times n}$ such that $D=P^{-1}AP$

In the following,we will see that diagonalizing a matrix $A\in\mathbb{R}^{n\times n}$ is a way of expressing the same linear mapping but in another basis (see Section 2.6.1), which will turn out to be a basis that consists of the eigen vectors of $A$ Let $A\in\mathbb{R}^{n\times n}$ ,let $\lambda_{1},\ldots,\lambda_{n}$ be a set of scalars, and let $P_{1},\cdots,P_{\mathrm{ru}}$ be a

set of vectors in $\mathbf{IR}^{n}$ . We define $P:=[p_{1},\ldots,p_{n}]$ and let $D\in\mathbb{R}^{n\times n}$ be a diagonal matrix with diagonal entries $\lambda_{1},\ldots,\lambda_{n}$ . Then we can show that

$$AP=PD$$

if and only if $\lambda_{1},\ldots,\lambda_{n}$ are the eigenvalues of $A$ and $P_{1},\cdots,P_{\mathrm{n}}$ are cor responding eigenvectors of $A$ We can see that this statement holds because

$$\begin{aligned}
&\text{AP} =A[p_{1},\ldots,p_{n}]=[Ap_{1},\ldots,Ap_{n}]\:, \\
&PD =[\boldsymbol{p}_1,\ldots,\boldsymbol{p}_n]\begin{bmatrix}\lambda_1&&0\\&\ddots&\\0&&\lambda_n\end{bmatrix}=[\lambda_1\boldsymbol{p}_1,\ldots,\lambda_n\boldsymbol{p}_n]\:. 
\end{aligned}$$

Thus, (4.50) implies that

$$\begin{aligned}Ap_1&=\lambda_1p_1\\&\vdots\\Ap_n&=\lambda_np_n\:.\end{aligned}$$

Therefore, the columns of $P$ must be eigenvectors of $A$ Our definition of diagonalization requires that. $P\in\mathbb{R}^{n\times n}$ is invertible

i.e., $P$ has full rank (Theorem 4.3). This requires us to have $TL$ linearly independent eigenvectors $P_{1},\ldots,P_{n}$ ,i.e., the $P_{i}$ form a basis of $\mathbf{R}^{n}$

Theorem 4.20 (Eigendecomposition). A square matrix $A\in\mathbb{R}^{n\times n}$ canbe factored into

$$A=PDP^{-1}\:,$$

where $P\in\mathbb{R}^{n\times n}$ and $D$ is a diagonal matrix whose diagonal entries are. the eigenvalues of $A$ if and only if the eigenvectors of $A$ form abasisof $\mathbf{R}^{n}$

------------------------------------------------------------------

![](https://storage.simpletex.cn/view/f4wqFzVSyA5zBzYOqIYVgo6290v3SGFBu)

Theorem 4.20 implies that only non-defective matrices can be diagonalized and that the columns of $P$ are the $n$ eigenvectors of $A$ .For symmetric matrices we can obtain even stronger outcomes for the eigenvalue decom position.

Theorem 4.21.A symmetric matrix $S\in\mathbb{R}^{n\times n}$ can always be diagonalized.

Theorem 4.21 follows directly from the spectral theorem 4.15. Moreover, the spectral theorem states that we can find an ONB of eigenvectors of $\mathbf{IR}^{n}$ .This makes $P$ an orthogonal matrix so that $D=P^{\top}AP$

Remark.The Jordan normal form of a matrixoffers a decomposition that works for defective matrices (Lang, 1987) but is beyond the scope of this book. $\diamondsuit$

Figure 4.7 Intuition behind the eigendecompositior as sequential transformations Top-left to bottom-left: $P^{-1}$ performs a basis change (here drawn in $R^{2}$ and depicted as a rotation-like operation) from the standard basis into the eigenbasis Bottom-left to bottom-right: $D$ performs a scaling along the remappec orthogonal eigenvectors depicted here by a circle being stretched to an ellipse. Bottom-right to top-right: $P$ undoes the basis change (depicted as a reverse rotation and restores the original coordinate frame.

### Geometric Intuition for the Eigendecomposition

We can interpret the eigendecomposition of a matrix as follows (see also Figure 4.7): Let $A$ be the transformation matrix of a linear mapping with respect to the standard basis $e_i$ (blue arrows). $P^{-1}$ performs a basis change from the standard basis into the eigenbasis. Then, the diagonal $D$ scales the vectors along these axes by the eigenvalues $\lambda_{i}$ . Finally, $P$ transforms these scaled vectors back into the standard/canonical coordi nates yielding $\lambda_ip_i$

### Example 4.11 (Eigendecomposition) Let us compute te eiedecompostionoo ${\boldsymbol{A}}=\frac{1}{2}\begin{bmatrix}{5}&{-2}\\{-2}&{5}\end{bmatrix}$

Step 1: Compute eigenvalues and eigenvectors. The characteristic

------------------------------------------------------------------

Figure 4.7 visualizes the eigendecomposition oF $A=\begin{bmatrix}5&-2\\-2&5\end{bmatrix}$ as a sequence of linear transformations

polynomial of $A$ is

$$\begin{aligned}
&\operatorname*{det}(\boldsymbol{A}-\lambda\boldsymbol{I})=\operatorname*{det}\left({\begin{bmatrix}{\frac{5}{2}-\lambda}&{-1}\\{-1}&{\frac{5}{2}-\lambda}\end{bmatrix}}\right) \\
&=(\frac52-\lambda)^2-1=\lambda^2-5\lambda+\frac{21}4=(\lambda-\frac72)(\lambda-\frac32)\:.
\end{aligned}$$

Therefore, the eigenvalues of $A$ are入1=and入2=3（theroots of the characteristic polynomial), and the associated (normalized) eigenvectors are obtained via

$$Ap_1=\frac{7}{2}p_1\:,\quad Ap_2=\frac{3}{2}p_2\:.$$

This yields

$$\boldsymbol{p}_1=\frac{1}{\sqrt{2}}\begin{bmatrix}1\\-1\end{bmatrix}\:,\quad\boldsymbol{p}_2=\frac{1}{\sqrt{2}}\begin{bmatrix}1\\1\end{bmatrix}\:.$$

Step 2: Check for existence.The eigenvectors ${\boldsymbol{p}}_{1},{\boldsymbol{p}}_{2}$ form a basis of $\mathbf{R}^{2}$ Therefore, $A$ can be diagonalized. Step 3:Construct the matrix $P$ to diagonalize $A$ .We collect the eigen

vectors of $A$ in $P$ sothat

$$P=[p_1,\:p_2]=\frac{1}{\sqrt{2}}\begin{bmatrix}1&1\\-1&1\end{bmatrix}\:.$$

We then obtain

$$P^{-1}AP=\begin{bmatrix}\frac{7}{2}&0\\0&\frac{3}{2}\end{bmatrix}=D\:.$$

Equivalently, we get (exploiting that $P^{-1}=P^{\top}$ since the eigenvectors $p_1$ and $p_2$ in this example form an ONB

$$\underbrace{\frac{1}{2}\begin{bmatrix}5&-2\\-2&5\end{bmatrix}}_{A}=\underbrace{\frac{1}{\sqrt{2}}\begin{bmatrix}1&1\\-1&1\end{bmatrix}}_{P}\underbrace{\begin{bmatrix}\frac{7}{2}&0\\0&\frac{3}{2}\end{bmatrix}}_{D}\underbrace{\frac{1}{\sqrt{2}}\begin{bmatrix}1&-1\\1&1\end{bmatrix}}_{P^{-1}}.$$

- Diagonal matrices $D$ can efficiently be raised to a power.Therefore we can find a matrix power for a matrix $A\in\mathbb{R}^{n\times n}$ via the eigenvalue decomposition (if it exists) so that

$$A^k=(PDP^{-1})^k=PD^kP^{-1}\:.$$

Computinge $D^{k}$ is efficient because we apply this operation individually to any diagonal element. : Assume that the eigendecomposition $A=PDP^{-1}$ exists. Then,

$$\det(\boldsymbol{A})=\det(\boldsymbol{PDP}^{-1})=\det(\boldsymbol{P})\det(\boldsymbol{D})\det(\boldsymbol{P}^{-1})$$

------------------------------------------------------------------

$$=\det(D)=\prod_id_{ii}$$

allows for an efficient computation of the determinant of. $A$

The eigenvalue decomposition requires square matrices. It would be useful to perform a decomposition on general matrices. In the next section, we introduce a more general matrix decomposition technique, the singular value decomposition

### 4.5 Singular Value Decompositior

The singular value decomposition (SVD) of a matrix is a central matrix decomposition method in linear algebra. It has been referred to as the “fundamental theorem of linear algebra” (Strang, 1993) because it can be applied to all matrices, not only to square matrices, and it always exists. Moreover, as we will explore in the following, the SVD of a matrix $A$ which represents a linear mapping $\Phi:V\to W$ ，quantifies the change between the underlying geometry of these two vector spaces.We recommend the work by Kalman (1996) and Roy and Banerjee (2014) for a deeper overview of themathematics of theSVD

Theorem 4.22 (SVD Theorem).Let $A\in\mathbb{R}^{m\times n}$ be a rectangular matrix of. rank $r\in[0,\operatorname*{min}(m,n)]$ .The SVD of $A$ isa decomposition of theform

A= $U$ VT

with an orthogonal matrix $U\in\mathbb{R}^{m\times m}$ with column vectors $u_{i}$ $i=1,\ldots,m$, andan orthogonal matrix $V\in\mathbb{R}^{n\times n}$ with column vectors $v_{j}$, $j=1,\ldots,n$ Moreover, $\Sigma$ is an $m\times n$ matrix with $\Sigma_{ii}=\sigma_{i}\geqslant0$ and $\Sigma _{ij}= 0$, $i\neq j$ i≠j $i\neq j$

The diagonal entries $\tau_{i},i=1,\ldots,r$ of $\Sigma$ are called the singularvalues, vectors. By convention, the singular values are ordered, i.e., $\sigma_{1}\geqslant\sigma_{2}\geqslant$ $\sigma_{r}\geqslant0$ The singular value matrix $\Sigma$ is unique, but it requires some attention.

Observe that the $\Sigma\in\mathbb{R}^{m\times n}$ is rectangular. In particular, $\Sigma$ is of the same size as $A$ .This means that $\Sigma$ has a diagonal submatrix that contains the singular values and needs additional zero padding. Specifically, if $m>n$ then the matrix $\Sigma$ has diagonal structure up to row $m$ and then consists of

SVD theorem

SVD singular value decompositior

singular values $u_{i}$ are called the left-singular vectors, and $v_{j}$ are called the right-singular left-singular vector: right-singular vectors

singular value matrix

------------------------------------------------------------------

Figure 4.8 Intuition behind the SVD of a matrix $A\in\mathbb{R}^{3\times2}$ as sequential transformations Top-left to bottom-left: $V^{\dagger}$ performs a basis change in $R^{2}$ Bottom-left to bottom-right: $\Sigma$ scales and maps from $\mathbb{R}^{2}$ to $\mathbb{R}^3$ The ellipse in the bottom-right lives in $\mathbb{R}^3$ . The third dimension is orthogonal to the surface of the elliptical disk. Bottom-right to top-right: $U$ performs a basis change within $\mathbb{R}^3$

![](https://storage.simpletex.cn/view/fgZU0x7Uka4woDgZxlwfMwUpXXVQhvsB6)

$0^{\top}$ row vectors from $n+1$ to $m$ below so that
$$\boldsymbol{\Sigma}=\begin{bmatrix}\sigma_1&0&0\\0&\ddots&0\\0&0&\sigma_n\\0&\dots&0\\\vdots&&\vdots\\0&\dots&0\end{bmatrix}\:.$$

If $m<n$ ，the matrix $\Sigma$ has a diagonal structure up to column $m$ and columns that consist of O from $m+1$ to $m$

$$\boldsymbol{\Sigma}=\begin{bmatrix}\sigma_1&0&0&0&\dots&0\\0&\ddots&0&\vdots&&\vdots\\0&0&\sigma_m&0&\dots&0\end{bmatrix}.$$

Remark.The SVD exists for any matrix $A\in\mathbb{R}^{m\times n}$

### 4.5.1 Geometric Intuitions for the SVD

The SVD offers geometric intuitions to describe a transformation matrix $A$ .In the following, we will discuss the SVD as sequential linear transformations performed on the bases. In Example 4.12, we will then apply transformation matrices of the SVD to a set of vectors in $\mathbb{R}^{2}$ ,which allows us to visualize the effect of each transformation more clearly The SVD of a matrix can be interpreted as a decomposition of a corre-

sponding linear mapping (recall Section 2.7.1) $\Phi:\mathbb{R}^n\to\mathbb{R}^m$ into three operations; see Figure 4.8. The SVD intuition follows superficially a similar structure to our eigendecomposition intuition, see Figure 4.7: Broadly. speaking, the SVD performs a basis change via $V^{\top}$ followed by a scaling and augmentation (or reduction) in dimensionality via the singular

------------------------------------------------------------------

value matrix $\Sigma$ Finally, it performs a second basis change via $U$ .The SVD entails a number of important details and caveats, which is why we wil review our intuition in more detail. Assume we are given a transformation matrix of a linear mapping $\Phi$ ：

$\mathbb{R}^{n}\to\mathbb{R}^{m}$ with respect to the standard bases $B$ and $C$ of $\mathbb{R}^n$ and $\mathbb{R}^{m}$ respectively. Moreover, assume a second basis $\bar{B}$ of $\mathbf{IR}^{n}$ and $\tilde{C}$ of $\mathbb{R}^m$ .Then

1. The matrix $V$ performs a basis change in the domain $\mathbb{R}^n$ from $\tilde{B}$ (represented by the red and orange vectors $v_{1}$ and $v_{2}$ in the top-left of Figure 4.8) to the standard basis $B$ $V^{|}=V^{-1}$ performs a basis change from $B$ to $\bar{B}$ .The red and orange vectors are now aligned with the canonical basis in the bottom-left of Figure 4.82.Having changed the coordinate system to $\bar{B}$ ， $\Sigma$ scales the new coordi-

nates by the singular values $\sigma_{i}$ (and adds or deletes dimensions), i.e., $\Sigma$ is the transformation matrix of $\Phi$ with respect to $\bar{B}$ and $\tilde{C}$ ,represented by the red and orange vectors being stretched and lying in the $e_1-e_2$ plane, which is now embedded in a third dimension in the bottom-right of Figure 4.83. $U$ performs a basis change in the codomain $\mathbb{R}^{m}$ from $\bar{C}$ into the canoni

cal basis of $\mathbb{R}^{m}$ ,represented by a rotation of the red and orange vectors out of the $e_1-e_2$ plane. This is shown in the top-right of Figure 4.8.

The SVD expresses a change of basis in both the domain and codomain This is in contrast with the eigendecomposition that operates within the same vector space, where the same basis change is applied and then undone.What makes the SVD special is that these two different bases are simultaneously linked by the singular value matrix $\Sigma$

### Example 4.12(Vectors and the SVD)

Consider a mapping of a square grid of vectors $\mathcal{X}\in\mathbb{R}^{2}$ that fit in a box of size $2\times2$ centered at the origin. Using the standard basis, we map these vectors using

$$\begin{aligned}\boldsymbol{A}&=\begin{bmatrix}1&-0.8\\0&1\\1&0\end{bmatrix}=\boldsymbol{U}\boldsymbol{\Sigma}\boldsymbol{V}^{\top}\\&=\begin{bmatrix}-0.79&0&-0.62\\0.38&-0.78&-0.49\\-0.48&-0.62&0.62\end{bmatrix}\begin{bmatrix}1.62&0\\0&1.0\\0&0\end{bmatrix}\begin{bmatrix}-0.78&0.62\\-0.62&-0.78\end{bmatrix}\:.\end{aligned}$$

We start with a set of vectors $X$ (colored dots; see top-left panel of Figure 4.9) arranged in a grid. We then apply $V^{|}\in\mathbb{R}^{2\times2}$ ,which rotates $X$ The rotated vectors are shown in the bottom-left panel of Figure 4.9.We now map these vectors using the singular value matrix $\Sigma$ to the codomain $\mathbb{R}^3$ (see the bottom-right panel in Figure 4.9). Note that all vectors lie in

------------------------------------------------------------------

Figure 4.9 SVD and mapping of vectors (represented by discs). The panels follow the same anti-clockwise structure of Figure 4.8.

the $x_1$-$x_2$ plane. The third coordinate is always 0. The vectors in the $x_1-x_2$ plane have been stretched by the singular values The direct mapping of the vectors $X$ by $A$ to the codomain $\mathbb{R}^3$ equals

the transformation of $X$ by $U\Sigma V^{\top}$ ,where $U$ performs a rotation within the codomain $R^{3}$ so that the mapped vectors are no longer restricted to the $x_1$-$x_2$ plane; they still are on a plane as shown in the top-right panel of Figure 4.9

![](https://storage.simpletex.cn/view/f6UQ4L2G98Dgolac91D2hNhO3YBns1d7y)

4.5.2 Construction of the SVD

We will next discuss why the SVD exists and show how to compute it in detail.The SVD of a general matrix shares some similarities with the eigendecomposition of a square matrix.

Remark. Compare the eigendecomposition of an SPD matrix

$$S=S^{\top}=PDP^{\top}$$

------------------------------------------------------------------

with the corresponding SVD

$$S=U\Sigma V^{\top}\:.$$

If we set

$$U=P=V\:,\quad D=\boldsymbol{\Sigma}\:,$$

we see that the SVD of SPD matrices is their eigendecomposition

$\diamondsuit$

In the following, we will explore why Theorem 4.22 holds and how the SVD is constructed.Computing the SVD of $A\in\mathbb{R}^{m\times n}$ is equivalent to finding two sets of orthonormal bases $U$ = $( \boldsymbol{u}_{1}, \ldots , \boldsymbol{u}_{m})$ and $V=$ $(\boldsymbol{v}_1,\ldots,\boldsymbol{v}_n)$ of the codomain $\mathbf{IR}^{m}$ and the domain $\mathbf{R}^{n}$ respectively. From these ordered bases, we will construct the matrices $U$ and $V$ Our plan is to start with constructing the orthonormal set of right-

singular vectorse $\boldsymbol{v}_1,\ldots,\boldsymbol{v}_n\in\mathbb{R}^n$ We then construct the orthonormal set of left-singular vectors $\boldsymbol{u}_1,\ldots,\boldsymbol{u}_m\in\mathbf{R}^m.$ Thereafter, we will link the two and require that the orthogonality of the $v_{i}$ is preserved under the transformation of $A$ .This is important because we know that the images $Av_i$ form a set of orthogonal vectors. We will then normalize these images by scalar factors, which will turn out to be the singular values. Let us begin with constructing the right-singular vectors. The spectral

theorem (Theorem 4.15) tells us that the eigenvectors of a symmetric matrix form an ONB, which also means it can be diagonalized. Moreover from Theorem 4.14 we can always construct a symmetric, positive semidefinite matrix $A^{\top}A\in\mathbb{R}^{n\times n}$ from any rectangular matrix $A\in$ $\mathbb{R}^{m\times n}$ .Thus, we can always diagonalize $A^{^{\prime}}A$ and obtain

$$A^\top A=PDP^\top=P\begin{bmatrix}\lambda_1&\cdots&0\\\vdots&\ddots&\vdots\\0&\cdots&\lambda_n\end{bmatrix}P^\top,$$

where $P$ is an orthogonalmatrix,which is composed of the orthonormal eigenbasis. Thee $\lambda_{i}\geqslant0$ are the eigenvalues of $A^{\top}A$ .Let us assume the SVD of $A$ exists and inject (4.64) into (4.71). This yields

$$A^\top A=(U\Sigma V^\top)^\top(U\Sigma V^\top)=V\Sigma^\top U^\top U\Sigma V^\top\:,$$

where $U,V$ are orthogonal matrices. Therefore, with $U^{^{\prime}}U=I$ weob tain
$$A^\top A=V\boldsymbol{\Sigma}^\top\boldsymbol{\Sigma}V^\top=\boldsymbol{V}\begin{bmatrix}\sigma_1^2&0&0\\0&\ddots&0\\0&0&\sigma_n^2\end{bmatrix}\boldsymbol{V}^\top.$$

Comparing now (4.71) and (4.73),we identify

$$\begin{array}{c}V^\top=P^\top\:,\\\sigma_i^2=\lambda_i\:.\end{array}$$

------------------------------------------------------------------

Therefore, the eigenvectors of $A^{^{\prime}}A$ that compose $P$ are the right-singulan vectors $V$ of $A$ (see (4.74)). The eigenvalues of $A^{\top}A$ are the squared singular values of $\Sigma$ (see (4.75)). To obtain the left-singular vectors $U$ ，we follow a similar procedure

We start by computing the SVD of the symmetric matrix $AA^{\top}\in\mathbb{R}^{m\times m}$ (instead of the previous $A^{^{\prime}}A\in\mathbb{R}^{n\times n})$ . The SVD of $A$ yields

$$\begin{aligned}
AA^{\top}& =(U\Sigma V^{\top})(U\Sigma V^{\top})^{\top}=U\Sigma V^{\top}V\Sigma^{\top}U^{\top} \\
&=\boldsymbol{U}\begin{bmatrix}\sigma_1^2&0&0\\0&\ddots&0\\0&0&\sigma_m^2\end{bmatrix}\boldsymbol{U}^\top.
\end{aligned}$$

The spectral theorem tells us that $AA^{\top}=SDS^{\top}$ can be diagonalized and we can find an ONB of eigenvectors of $AA^{\top}$ ,which are collected in S The orthonormal eigenvectors of $AA^\top$ are the left-singular vectors $U$ and form an orthonormal basis in the codomain of the SVD. This leaves the question of the structure of the matrix $\Sigma$ .Since $AA^{\top}$

and $A^{\top}A$ have the same nonzero eigenvalues (see page 106), the nonzero entries of the $\Sigma$ matrices in the SVD forboth cases have to be the same The last step is to link up all the parts we touched upon so far. We have

an orthonormal set of right-singular vectors in $V$ .To finish the construc tion of the SVD,we connect them with the orthonormal vectors $U$ .To reach this goal, we use the fact the images of the $v_{i}$ under $A$ have to be orthogonal, too. We can show this by using the results from Section 3.4 We require that the inner product between $Av_i$ and $Av_{j}$ must be 0 for $i\neq j$ .For any two orthogonal eigenvectors $v_{i},v_{j}$ $i\neq j$ ,it holds that

$$(\boldsymbol{A}\boldsymbol{v}_i)^\top(\boldsymbol{A}\boldsymbol{v}_j)=\boldsymbol{v}_i^\top(\boldsymbol{A}^\top\boldsymbol{A})\boldsymbol{v}_j=\boldsymbol{v}_i^\top(\lambda_j\boldsymbol{v}_j)=\lambda_j\boldsymbol{v}_i^\top\boldsymbol{v}_j=0\:.$$

For the case $m\not=\gamma$ ，it holds that $\{Av_1,\ldots,Av_r\}$ is a basis of an 7 dimensional subspace of $R^{m}$

To complete the SVD construction,we need left-singular vectors that are orthonormal: We normalize the images of the right-singular vectors $Av_i$ and obtain

$$u_i:=\frac{Av_i}{\|Av_i\|}=\frac{1}{\sqrt{\lambda_i}}Av_i=\frac{1}{\sigma_i}Av_i\:,$$

where the last equality was obtained from (4.75) and (4.76b), showing us that the eigenvalues of $AA^{\prime}$ are such that $\sigma_{i}^{2}=\lambda_{i}$ Therefore, the eigenvectors of $A^{\top}A$ ，which we know are the right

singular vectorse $v_{i}$ , and their normalized images under $A$ , the left-singular vectors $u_{i}$ , form two self-consistent ONBs that are connected through the singular value matrix $\Sigma$ Let us rearrange (4.78) to obtain the singular value equation

$$A\boldsymbol{v}_i=\sigma_i\boldsymbol{u}_i\:,\quad i=1,\ldots,r\:.$$

------------------------------------------------------------------

This equation closely resembles the eigenvalue equation (4.25), but the vectors on the left- and the right-hand sides are not the same For $n<m$ , (4.79) holds only for $i\leqslant n$ , but (4.79) says nothing about

the $u_{i}$ for $i>n$ .However, we know by construction that they are orthonormal. Conversely, for $m<n$ , (4.79) holds only for $i\leqslant m$ .For $i>m$ we have $Av_{i}=0$ and we still know that the $v_{i}$ form an orthonormal set. This means that the SVD also supplies an orthonormal basis of the kernel (null space) of $A$ ,the set of vectors $2L$ with $Ax=0$ (see Section 2.7.3) Concatenating the $v_{i}$ as the columns of $V$ and the $u_{i}$ as the columns of

$U$ yields

$$AV=U\Sigma\:,$$

where $\Sigma$ has the same dimensions as $A$ and a diagonal structure for rows $1,\ldots,r$ . Hence, right-multiplying with $V^{\top}$ yields $A=U\Sigma V^{|}$ , which is the SVD of $A$

### Example 4.13 (Computing the SVD)

Let us find the singular value decomposition of

$$A=\begin{bmatrix}1&0&1\\-2&1&0\end{bmatrix}\:.$$

The SVD requires us to compute the right-singular vectors $v_{j}$ , the singular values $\sigma_k$ , and the left-singular vectors $u_{i}$ Step 1: Right-singular vectors as the eigenbasis of $A^{^{\prime}}A$

We start by computing

$$\boldsymbol A^\top\boldsymbol A=\begin{bmatrix}1&-2\\0&1\\1&0\end{bmatrix}\begin{bmatrix}1&0&1\\-2&1&0\end{bmatrix}=\begin{bmatrix}5&-2&1\\-2&1&0\\1&0&1\end{bmatrix}\:.$$

We compute the singular values and right-singular vectors $v_{j}$ through the eigenvalue decomposition of $A^{\top}A$ ,which isgiven as

![](https://storage.simpletex.cn/view/fip1PDWfTo3w2bRvGi96QEGKGBDXkmYte)

and we obtain the right-singular vectors as the columns of $P$ so that

$$V=P=\begin{bmatrix}\frac{5}{\sqrt{30}}&0&\frac{-1}{\sqrt{6}}\\\frac{-2}{\sqrt{30}}&\frac{1}{\sqrt{5}}&\frac{-2}{\sqrt{6}}\\\frac{1}{\sqrt{30}}&\frac{2}{\sqrt{5}}&\frac{1}{\sqrt{6}}\end{bmatrix}.$$

### Step 2: Singular-value matrix

As the singular values $\sigma_{i}$ are the square roots of the eigenvalues of

------------------------------------------------------------------

$A^{^{\prime}}A$ we obtain them straight from $D$ .Since $\operatorname{rk}(\boldsymbol{A})=2$ , there are only two nonzero singular values: $\sigma_{1}=\sqrt{6}$ and $\sigma_{2}=1$ .The singular value matrix must be the same size as $A$ ,and we obtain

$$\boldsymbol{\Sigma}=\begin{bmatrix}\sqrt{6}&0&0\\0&1&0\end{bmatrix}\:.$$

### Step 3: Left-singular vectors as the normalized image of the right singular vectors We find the left-singular vectors by computing the image of the right

singular vectors under $A$ and normalizing them by dividing them by thei. corresponding singular value. We obtain

$$\begin{aligned}
&\text{1} \\
&u_{1}=\frac{1}{\sigma_{1}}Av_{1}&& =\frac{1}{\sqrt{6}}\begin{bmatrix}1&0&1\\-2&1&0\end{bmatrix}\begin{bmatrix}\frac{5}{\sqrt{30}}\\\frac{-2}{\sqrt{30}}\\\frac{1}{\sqrt{30}}\end{bmatrix}=\begin{bmatrix}\frac{1}{\sqrt{5}}\\-\frac{2}{\sqrt{5}}\end{bmatrix}\:, \\
&u_{2}={\frac{1}{\sigma_{2}}}Av_{2}&& =\frac{1}{1}\begin{bmatrix}1&0&1\\-2&1&0\end{bmatrix}\begin{bmatrix}0\\\frac{1}{\sqrt{5}}\\\frac{2}{\sqrt{5}}\end{bmatrix}=\begin{bmatrix}\frac{2}{\sqrt{5}}\\\frac{1}{\sqrt{5}}\end{bmatrix}\:, \\
&U=[u_{1},u_{2}]&& =\frac{1}{\sqrt{5}}\begin{bmatrix}1&2\\-2&1\end{bmatrix}\:. 
\end{aligned}$$

Note that on a computer the approach illustrated here has poor numerica behavior, and the SVD of $A$ isnormally computed without resorting to the eigenvalue decomposition of $A^{\top}A$

### 4.5.3 Eigenvalue Decomposition vs. Singular Value Decomposition

Let us consider the eigendecomposition $A=PDP^{-1}$ and the SVD $A=$ $U\Sigma V^{\top}$ and review the core elements of the past sections.

The SVD always exists for any matrix $\mathbb{R}^{m\times n}$ . The eigendecomposition is only defined for square matrices $\mathbb{R}^{n\times n}$ and only exists if we can find a basis of eigenvectors of $\mathbf{IR}^{n}$ - The vectors in the eigendecomposition matrix. $P$ are not necessarily orthogonal, i.e., the change of basis is not a simple rotation and scaling On the other hand,the vectors in the matrices $U$ and $V$ in the SVD are orthonormal, so they do represent rotations. ·Both the eigendecomposition and the SVD are compositions of three linear mappings: 1.Change of basis in the domain 2.Independent scaling of each new basis vector and mapping from domain to codomain 3.Change of basis in the codomain

------------------------------------------------------------------

![](https://storage.simpletex.cn/view/fGpbl6uEhCmNGN1lP0uKOXDVt9U0N9Ldy)

A key difference between the eigendecomposition and the SVD is that in the SVD,domain and codomain can be vector spaces of different dimensions. ·In the SVD,the left-and right-singular vector matrices $U$ and $V$ are

generally not inverse of each other (they perform basis changes in different vector spaces). In the eigendecomposition, the basis change matrices $P$ and $P^{-1}$ are inverses of each other.. ·In the SVD,the entries in the diagonal matrix $\Sigma$ are all real and nonnegative,which is not generally true for the diagonal matrix in the eigendecomposition. ·The SVD and the eigendecomposition are closely related through their projections - The left-singular vectors of $A$ are eigenvectors of $AA^\top$ -The right-singular vectors of $A$ are eigenvectors of $A^\top A$ -The nonzero singular values of $A$ are the square roots of the nonzero eigenvalues of both $AA^\top$ and $A^{\top}A$ ·For symmetric matrices $A\in\mathbb{R}^{n\times n}$ , the eigenvalue decomposition and the SVD are one and the same,which follows from the spectral theo rem 4.15.

### Example 4.14 (Finding Structurein Movie Ratings and Consumers)

Let us add a practical interpretation of the SVD by analyzing data on people and their preferred movies. Consider three viewers (Ali, Beatrix Chandra) rating four different movies (Star Wars, Blade Runner, Amelie. Delicatessen). Their ratings are values between 0 (worst) and 5 (best) and encoded in a data matrix $A\in\mathbb{R}^{4\times3}$ as shown in Figure 4.10. Each row represents a movie and each column a user. Thus, the column vectors of movie ratings, one for each viewer, are $x_\mathrm{Ali}$ $x_{\text{Beatrix}}$ , CChandra-

Figure 4.10 Movie ratings of three people for four movies and its SVD decomposition

------------------------------------------------------------------

These two “spaces' are only meaningfully spanned by the respective viewer and movie data if the data itself covers a sufficient diversity of viewers and movies.

Factoring $A$ using the SVD offers us a way to capture the relationships of how people rate movies, and especially if there is a structure linking which people like which movies. Applying the SVD to our data matrix $A$ makes a number of assumptions

1. All viewers rate movies consistently using the same linear mapping 2. There are no errors or noise in the ratings. 3. We interpret the left-singular vectors $u_i$ as stereotypical movies and the right-singular vectors $v_j$ as stereotypical viewers

We then make the assumption that any viewer's specific movie preferences can be expressed as a linear combination of the $v_j$ .Similarly, any movie's like-ability can be expressed as a linear combination of the $u_i$ . Therefore a vector in the domain of the SVD can be interpreted as a viewer in the “space”of stereotypical viewers, and a vector in the codomain of the SVD correspondingly as a movie in the “space” of stereotypical movies. Let us inspect the SVD of our movie-user matrix. The first left-singular vector $u_1$ has large absolute values for the two science fiction movies and a large first singular value (red shading in Figure 4.10). Thus, this groups a type of users with a specific set of movies (science fiction theme). Similarly, the first right-singular $v_1$ shows large absolute values for Ali and Beatrix, who give high ratings to science fiction movies (green shading in Figure 4.10)) This suggests that $v_1$ reflects the notion of a science fiction lover Similarly, $u_2$ , seems to capture a French art house film theme, and $v_2$ in-

dicates that Chandra is close to an idealized lover of such movies.An ide alized science fiction lover is a purist and only loves science fiction movies, so a science fiction lover $v_1$ gives a rating of zero to everything but science fiction themed—this logic is implied by the diagonal substructure for the singular value matrix $\Sigma$ .A specific movie is therefore represented by how it decomposes (linearly) into its stereotypical movies. Likewise, a persor would be represented by how they decompose (via linear combination) into movie themes.

It is worth to briefly discuss SVD terminology and conventions,as there are different versions used in the literature.While these differences can be confusing, the mathematics remains invariant to them.

·For convenience in notation and abstraction, we use an SVD notation where the SVD is described as having two square left- and right-singulan vector matrices,but a non-square singular value matrix. Our definition (4.64) for the SVD is sometimes called the full SVD ·Some authors define the SVD a bit differently and focus on square singular matrices. Then, for $A\in\mathbb{R}^{m\times n}$ and $m\geqslant m$

$$A_{m\times n}=U_{m\times n}\sum_{n\times n}V_{n\times n}^{\top}\:.$$

full SVD

------------------------------------------------------------------

Sometimes this formulation is called the reduced SVD (e.g., Datta (2010)) reduced SVD or the SVD (e.g., Press et al. (2007)). This alternative format changes merely how the matrices are constructed but leaves the mathematical structure of the SVD unchanged.The convenience of this alternative formulation is that $\Sigma$ is diagonal, as in the eigenvalue decomposition.

·In Section 4.6, we will learn about matrix approximation techniques truncated SVD using the SVD, which is also called the truncated SVD. ·It is possible to define the SVD of a rank- $\cdot Y$ matrix $A$ so that $U$ is an $m\times r$ matrix, $\Sigma$ a diagonal matrix $r\times r$ ，and $V$ an $r\times n$ matrix. This construction is very similar to our definition, and ensures that the diagonal matrix $\Sigma$ has only nonzero entries along the diagonal.The main convenience of this alternative notation is that $\Sigma$ is diagonal, as in the eigenvalue decomposition ·A restriction that the SVD for $A$ only applies to $m\times n$ matrices with $m>n$ is practically unnecessary. When $m<n$ ,the SVD decomposition will yield $\Sigma$ with more zero columns than rows and, consequently, the singular values $\sigma_{m+1},\ldots,\sigma_{n}$ are 0

The SVD is used in a variety of applications in machine learning from least-squares problems in curve fitting to solving systems of linear equations. These applications harness various important properties of the SVD, its relation to the rank of a matrix, and its ability to approximate matrices of a given rank with lower-rank matrices. Substituting a matrix with its SVD has often the advantage of making calculation more robust to numerical rounding errors. As we will explore in the next section, the SVD's ability to approximate matrices with “simpler” matrices in a principled manner opens up machine learning applications ranging from dimension ality reduction and topic modeling to data compression and clustering

### 4.6 Matrix Approximation

We considered the SVD as a way to factorize $A=U\Sigma V^{\top}\in\mathbb{R}^{m\times n}$ into the product of three matrices, where $U\in\mathbb{R}^{m\times m}$ and $V\in\mathbb{R}^{n\times n}$ are orthogonal and $\Sigma$ contains the singular values on its main diagonal. Instead of doing the full SVD factorization, we will now investigate how the SVD allows us to represent a matrix $A$ as a sum of simpler (low-rank) matrices $A_{i}$, which lends itself to a matrix approximation scheme that is cheaper to compute than the full SVD We construct a rank-1 matrix $A_{i}\in\mathbb{R}^{m\times n}$ as

$$A_i:=u_iv_i^\top\:,$$

which is formed by the outer product of the ith orthogonal column vecto1 of $U$ and $V$ .Figure 4.11 shows an image of Stonehenge,which can be represented by a matrix $A\in\mathbb{R}^{1432\times1910}$ ,and some outer products $A_i$ ,as defined in (4.90).

------------------------------------------------------------------

Figure 4.11 Image processing with the SVD. (a) The original grayscale image is a $1,432\times1,910$ matrix of values between 0 (black) and 1 (white), (b)-(f) Rank-1 matrices $A_1,\ldots,A_5$ and their corresponding singular values $\sigma_1,\ldots,\sigma_5$ . The grid-like structure of each rank-1 matrix is imposed by the outer-product of the left and right-singular vectors.

![](https://storage.simpletex.cn/view/fQGtHGHWgvGgswv9Hkui0RyNdh4IAY1Ok)

rank-k approximation

A matrix $A\in\mathbb{R}^{m\times n}$ ofrank $Y$ canbe written as a sum of rank-1 matrices $A_{i}$ so that

$$\boldsymbol{A}=\sum\limits_{i=1}^r\sigma_i\boldsymbol{u}_i\boldsymbol{v}_i^\top=\sum\limits_{i=1}^r\sigma_i\boldsymbol{A}_i\:,$$

where the outer-product matrices. $A_{i}$ are weighted by the ith singular value $\sigma_{i}$ .We can see why (4.91) holds: The diagonal structure of the singular value matrix $\Sigma$ multiplies only matching left- and right-singula vectors $u_i\boldsymbol{v}_i^|$ and scales them by the corresponding singular value $\sigma_{i}$ . All terms $\Sigma_{ij}\boldsymbol{u}_i\boldsymbol{v}_j^\top$ vanish for $i\neq j$ because $\Sigma$ is a diagonal matrix. Any terms $i>r$ vanish because the corresponding singular values are 0 In (4.90), we introduced rank-1 matrices $A_{i}$ . We summed up the 7 in-

dividual rank-1 matrices to obtain a rank- 7 matrix $A$ ;see (4.91).If the sum does not run over all matrices $A_{i}$ ， $i$ = $1, \ldots , r$ , but only up to an intermediate value $k<r$ ,we obtain a rank- $k$ approximation

$$\hat{\boldsymbol{A}}(k):=\sum_{i=1}^k\sigma_i\boldsymbol{u}_i\boldsymbol{v}_i^\top=\sum_{i=1}^k\sigma_i\boldsymbol{A}_i$$

of $A$ with rk$( \widehat{\boldsymbol{A}} ( k) )$ = $k$ . Figure 4.12 shows low-rank approximations ${\hat{\boldsymbol{A}}}(k)$ of an original image $A$ of Stonehenge. The shape of the rocks becomes increasingly visible and clearly recognizable in the rank-5 approximation. While the original image requires $1,432\cdot1,910=2,735,120$ numbers, the rank-5 approximation requires us only to store the five singular values and the five left- and right-singular vectors (1,432 and 1,910 dimensional each) for a total of $5\cdot(1,432+1,910+1)=16,715$ numbers - just above $0.6\%$ of the original To measure the difference (error) between $A$ and its rank- $\cdot k$ approxima

tion $\hat{\boldsymbol{A}}(k)$ , we need the notion of a norm. In Section 3.1, we already used

------------------------------------------------------------------

![](https://storage.simpletex.cn/view/fHIIyLbiaRytMw7v081hXRrmkZ1iA7Icf)

(d) Rank-3 approximation A(3).(e) Rank-4 approximation A(4). (f) Rank-5 approximation $\hat{A}(5)$

Figure 4.12 Image reconstruction with the SVD. (a) Original image (b)(f) Image reconstruction using the low-rank approximation of the SVD, where the rank-k approximation is given by $\hat{A}(k)=$ $\sum_{i=1}^k\sigma_iA_i$

norms on vectors that measure the length of a vector. By analogy we can also define norms on matrices.

Definition 4.23 (Spectral Norm of a Matrix). For $x\in\mathbb{R}^n\backslash\{\mathbf{0}\}$, the spectralspectral norn norm of a matrix $A\in\mathbb{R}^{m\times n}$ is defined as

$$\left\|A\right\|_{2}:=\max_{x}\frac{\left\|Ax\right\|_{2}}{\left\|x\right\|_{2}}\:.$$

We introduce the notation of a subscript in the matrix norm (left-hand side),similar to the Euclidean norm for vectors (right-hand side),which has subscript 2. The spectral norm (4.93) determines how long any vecto1 ${:}L$ can at most become when multiplied by $A$

Theorem 4.24. The spectral norm of $A$ is its largest singular value $\sigma_{1}$

We leave the proof of this theorem as an exercise.

Eckart-Young theorem

Theorem 4.25 (Eckart-Young Theorem (Eckart and Young, 1936)). Con sider amatrix $A\in\mathbb{R}^{m\times n}$ ofrank 7 andlet $B\in\mathbb{R}^{m\times n}$ be a matrix of rank $k$ .For any $k\leqslant r$ with ${\hat{\boldsymbol{A}}}(k)=\sum_{i=1}^{k}\sigma_{i}u_{i}v_{i}^{\top}$ itholds that

$$\begin{aligned}
\hat{A}(k)& =\mathrm{argmin}_{\mathrm{rk}(B)=k}\left\|A-B\right\|_{2}\:, \\
\left\|A-\hat{A}(k)\right\|_{2}& =\sigma_{k+1}\:. 
\end{aligned}$$

The Eckart-Young theorem states explicitly how much error we introduce by approximating $A$ using a rank- $\cdot k$ approximation. We can inter pret the rank- $\cdot k$ approximation obtained with the SVD as a projection of the full-rank matrix $A$ onto a lower-dimensional space of rank-at-most- $\cdot k$ matrices. Of all possible projections, the SVD minimizes the error (with respect to the spectral norm)between $A$ and any rank $k$ approximation. We can retrace some of the steps to understand why (4.95) should hold.

------------------------------------------------------------------

We observe that the difference between $A-\hat{\boldsymbol{A}}(k)$ is a matrix containing the sum of the remaining rank-1 matrices

$$\boldsymbol{A}-\widehat{\boldsymbol{A}}(k)=\sum_{i=k+1}^r\sigma_i\boldsymbol{u}_i\boldsymbol{v}_i^\top\:.$$

By Theorem 4.24, we immediately obtain $\sigma_{k+1}$ as the spectral norm of the difference matrix.Let us have a closer look at (4.94).If we assume that there is another matrix $B$ with rk$(B)\leqslant k$ such that

$$\left\|A-B\right\|_{2}<\left\|A-\widehat{A}(k)\right\|_{2}\:,$$

then there exists an at least $(n-k)$ -dimensional null space $Z\subseteq\mathbb{R}^{n}$ ,such that $x\in Z$ implies that $Bx=0$ .Then it follows that

$$\left\|Ax\right\|_2=\left\|(A-B)x\right\|_2\:,$$

and by using a version of the Cauchy-Schwartz inequality (3.17) that encompasses norms of matrices,we obtain

$$\left\|Ax\right\|_2\leqslant\left\|A-B\right\|_2\left\|x\right\|_2<\sigma_{k+1}\left\|x\right\|_2\:.$$

However, there exists a $(k+1)$ -dimensional subspace where $\left\|\boldsymbol{A}x\right\|_{2}\geqslant$ $\sigma_{k+1}\left\|\boldsymbol{x}\right\|_{2}$ , which is spanned by the right-singular vectors $\boldsymbol{v}_{j},j\leqslant k+1$ of $A$ .Adding up dimensions of these two spaces yields a number greater than $7L$ , as there must be a nonzero vector in both spaces. This is a contradiction of the rank-nullity theorem (Theorem 2.24) in Section 2.7.3 The Eckart-Young theorem implies that we can use SVD to reduce a

rank- 7 matrix $A$ to a rank- $\cdot k$ matrix $\tilde{A}$ in a principled,optimal (in the spectral norm sense) manner. We can interpret the approximation of $A$ by a rank- $\cdot k$ matrix as a form of lossy compression. Therefore, the low-rank approximation of a matrix appears in many machine learning applications e.g., image processing, noise filtering, and regularization of ill-posed prob-. lems. Furthermore, it plays a key role in dimensionality reduction and principal component analysis, as we will see in Chapter 10.

## Example 4.15 (Finding Structure in Movie Ratings and Consumers (continued)) Coming back to our movie-rating example, we can now apply the con-

cept of low-rank approximations to approximate the original data matrix Recall that our first singular value captures the notion of science fiction theme in movies and science fiction lovers. Thus, by using only the first singular value term in a rank-1 decomposition of the movie-rating matrix, we obtain the predicted ratings

$$A_1=\boldsymbol{u}_1\boldsymbol{v}_1^\top=\begin{bmatrix}-0.6710\\-0.7197\\-0.0939\\-0.1515\end{bmatrix}\begin{bmatrix}-0.7367&-0.6515&-0.1811\end{bmatrix}$$

------------------------------------------------------------------

$$=\begin{bmatrix}0.4943&0.4372&0.1215\\0.5302&0.4689&0.1303\\0.0692&0.0612&0.0170\\0.1116&0.0987&0.0274\end{bmatrix}.$$

This first rank-1 approximation $A_1$ is insightful: it tells us that Ali and Beatrix like science fiction movies,such as Star Wars and Bladerunner (entries have values >0.4 , but fails to capture the ratings of the other movies by Chandra. This is not surprising, as Chandra's type of movies is not captured by the first singular value. The second singular value gives us a better rank-1 approximation for those movie-theme lovers:

$$\begin{aligned}
A_{2}& =\boldsymbol{u}_{2}\boldsymbol{v}_{2}^{\top}=\begin{bmatrix}0.0236\\0.2054\\-0.7705\\-0.6030\end{bmatrix}\begin{bmatrix}0.0852&0.1762&-0.9807\end{bmatrix} \\
&=\begin{bmatrix}0.0020&0.0042&-0.0231\\0.0175&0.0362&-0.2014\\-0.0656&-0.1358&0.7556\\-0.0514&-0.1063&0.5914\end{bmatrix}\:.
\end{aligned}$$

In this second rank-1 approximation. $A_2$ ,we capture Chandra's ratings and movie types well, but not the science fiction movies. This leads us to consider the rank-2 approximation $\hat{\boldsymbol{A}}(2)$ , where we combine the first two rank-1 approximations

$$\hat{\boldsymbol A}(2)=\sigma_1\boldsymbol A_1+\sigma_2\boldsymbol A_2=\begin{bmatrix}4.7801&4.2419&1.0244\\5.2252&4.7522&-0.0250\\0.2493&-0.2743&4.9724\\0.7495&0.2756&4.0278\end{bmatrix}.$$

$\hat{\boldsymbol{A}}(2)$ is similar to the original movie ratings table

$$\boldsymbol A=\begin{bmatrix}5&4&1\\5&5&0\\0&0&5\\1&0&4\end{bmatrix}\:,$$

and this suggests that we can ignore the contribution of $A_3$ .We can interpret this so that in the data table there is no evidence of a third movietheme/movie-lovers category. This also means that the entire space of moyie-themes/movie-lovers in our example is a two-dimensional space spanned by science fiction and French art house movies and lovers.

------------------------------------------------------------------

Figure 4.13 A functional phylogeny of matrices encountered in machine learning

![](https://storage.simpletex.cn/view/fpymc5m0YRaOnLVoZK49nzXGHgsZ2hOvu)

4.7 Matrix Phylogeny

In Chapters 2 and 3, we covered the basics of linear algebra and analytic geometry. In this chapter, we looked at fundamental characteristics of matrices and linear mappings. Figure 4.13 depicts the phylogenetic tree of “is a subset of") and the covered operations we can perform on them (in blue).We consider all real matrices $A\in\mathbb{R}^{n\times m}$ For non-square matrices (where $n\neq m$ ), the SVD always exists, as we saw in this chapter. Focusing on square matrices $A\in\mathbb{R}^{n\times n}$ , the determinant informs us whether a square matrix possesses an inverse matrix, i.e., whether it belongs to the class of regular,invertible matrices. If the square $n\times n$ matrix possesses $n$ linearly independent eigenvectors, then the matrix is non-defective and an eigendecomposition exists (Theorem 4.12). We know that repeated eigen values may result in defective matrices, which cannot be diagonalized Non-singular and non-defective matrices are not the same.For exam

ple, a rotation matrix will be invertible (determinant is nonzero) but not diagonalizable in the real numbers (eigenvalues are not guaranteed to be real numbers)

The word "phylogenetic describes how we capture the relationships among relationships between different types of matrices (black arrows indicating individuals or. groups and derived from the Greek words for “tribe” and “source"

------------------------------------------------------------------

We dive further into the branch of non-defective square $n\times n$ matrices $A$ is normal if the condition $A^{\top}A=AA^{\top}$ holds. Moreover, if the more restrictive condition holds that $A^{\top}A=AA^{\top}=I$ ,then $A$ is called orthogonal (see Definition 3.8). The set of orthogonal matrices is a subset of the regular (invertible) matrices and satisfies $A^{|}=A^{-1}$ Normal matrices have a frequently encountered subset, the symmetric

matrices $S\in\mathbb{R}^{n\times n}$ , which satisfy $S=S^{\top}$ .Symmetric matrices have only real eigenvalues. A subset of the symmetric matrices consists of the positive definite matrices $P$ that satisfy the condition of $x^{\top}Px>0$ for all $x\in\mathbb{R}^{n}\backslash\{\mathbf{0}\}$ . In this case, a unique Cholesky decomposition exists (Theorem 4.18).Positive definite matrices have only positive eigenvalues and are always invertible (i.e., have a nonzero determinant) Another subset of symmetric matrices consists of the diagonal matrices

$D$ .Diagonal matrices are closed under multiplication and addition,but do not necessarily form a group (this is only the case if all diagonal entries are nonzero so that the matrix is invertible). A special diagonal matrix is the identity matrix $I$

### 4.8 Further Reading

Most of the content in this chapter establishes underlying mathematics and connects them to methods for studying mappings,many of which are at the heart of machine learning at the level of underpinning software solutions and building blocks for almost all machine learning theory. Matrix characterization using determinants, eigenspectra, and eigenspaces provides fundamental features and conditions for categorizing and analyzing matrices. This extends to all forms of representations of data and mappings involving data, as well as judging the numerical stability of computational operations on such matrices (Press et al., 2o07). Determinants are fundamental toolsin order to invert matrices and

compute eigenvalues “by hand". However, for almost all but the smallest instances, numerical computation by Gaussian elimination outperforms determinants (Press et al., 2007). Determinants remain nevertheless a powerful theoretical concept, e.g., to gain intuition about the orientation of a basis based on the sign of the determinant. Eigenvectors can be used to perform basis changes to transform data into the coordinates of meaningful orthogonal, feature vectors. Similarly, matrix decomposition methods, such as the Cholesky decomposition,reappear often when we compute or simulate random events (Rubinstein and Kroese, 2016). Therefore the Cholesky decomposition enables us to compute the reparametrization trick where we want to perform continuous differentiation over random variables, e.g., in variational autoencoders (Jimenez Rezende et al., 2014; Kingma and Welling, 2014). Eigendecomposition is fundamental in enabling us to extract mean-

ingful and interpretable information that characterizes linear mappings

------------------------------------------------------------------

principal component analysis

Fisher discriminant analysis multidimensional scaling

Isomap Laplacian eigenmaps Hessian eigenmaps spectral clustering

Tucker decomposition CP decompositior

Therefore, the eigendecomposition underlies a general class of machine learning algorithms called spectral methods that perform eigendecomposi tion of a positive-definite kernel. These spectral decomposition methods encompass classical approaches to statistical data analysis, such as the following

- Principal component analysis (PCA (Pearson, 1901), see also Chapter 10), in which a low-dimensional subspace, which explains most of the variability in the data,is sought ·Fisher discriminant analysis, which aims to determine a separating hyperplane for data classification (Mika et al., 1999). - Multidimensional scaling (MDs) (Carroll and Chang, 1970)

The computational efficiency of these methods typically comes from finding the best rank $\cdot k$ approximation to a symmetric, positive semidefinite matrix. More contemporary examples of spectral methods have different origins, but each of them requires the computation of the eigenvectors and eigenvalues of a positive-definite kernel, such as Isomap (Tenenbaum et al., 2000), Laplacian eigenmaps (Belkin and Niyogi, 2003), Hessiar eigenmaps (Donoho and Grimes, 2003), and spectral clustering (Shi and Malik, 20oo). The core computations of these are generally underpinned by low-rank matrix approximation techniques (Belabbas and Wolfe, 2009) as we encountered here via the SVD The SVD allows us to discover some of the same kind of information as

the eigendecomposition. However, the SVD is more generally applicable to non-square matrices and data tables. These matrix factorization meth ods become relevant whenever we want to identify heterogeneity in data when we want to perform data compression by approximation, e.g., instead of storing $n\times m$ values just storing $(n+m)k$ values,or when we want to perform data pre-processing, e.g., to decorrelate predictor variables of a design matrix (Ormoneit et al., 2001). The SVD operates on matrices. which we can interpret as rectangular arrays with two indices (rows and columns). The extension of matrix-like structure to higher-dimensiona. arrays are called tensors. It turns out that the SVD is the special case of a more general family of decompositions that operate on such tensors (Kolda and Bader, 2009). SVD-like operations and low-rank approximations on tensors are, for example, the Tucker decomposition (Tucker, 1966) or the $CP$ decomposition (Carroll and Chang, 1970) The SVD low-rank approximation is frequently used in machine learn

ing for computational efficiency reasons. This is because it reduces the amount of memory and operations with nonzero multiplications we need to perform on potentially very large matrices of data (Trefethen and Bau II, 1997). Moreover, low-rank approximations are used to operate on matrices that may contain missing values as well as for purposes of lossy compression and dimensionality reduction (Moonen and De Moor, 1995; Markovsky, 2011)

------------------------------------------------------------------

### Exercises

4.1Compute the determinant using the Laplace expansion (using the first row) and the Sarrus rule for

$$A=\left[\begin{array}{ccc}1&3&5\\2&4&6\\0&2&4\end{array}\right]\:.$$

4.2Compute the following determinant efficiently

$$\begin{bmatrix}2&0&1&2&0\\2&-1&0&1&1\\0&1&2&1&2\\-2&0&2&-1&2\\2&0&0&1&1\end{bmatrix}.$$

4.3Compute the eigenspaces of

a.

$$A:=\begin{bmatrix}1&&0\\1&&1\end{bmatrix}$$

b.

$$B:=\begin{bmatrix}-2&&2\\2&&1\end{bmatrix}$$

4.4Compute all eigenspaces of

$$\mathbf{A}=\begin{bmatrix}0&-1&1&1\\-1&1&-2&3\\2&-1&0&0\\1&-1&1&0\end{bmatrix}\:.$$

4.5 Diagonalizability of a matrix is unrelated to its invertibility. Determine for the following four matrices whether they are diagonalizable and/or invertible

$$\begin{bmatrix}1&0\\0&1\end{bmatrix},\quad\begin{bmatrix}1&0\\0&0\end{bmatrix},\quad\begin{bmatrix}1&1\\0&1\end{bmatrix},\quad\begin{bmatrix}0&1\\0&0\end{bmatrix}.$$

4.6 Compute the eigenspaces of the following transformation matrices. Are they diagonalizable

a.For

$$\boldsymbol A=\begin{bmatrix}2&3&0\\1&4&3\\0&0&1\end{bmatrix}$$

b. For

$$\boldsymbol A=\begin{bmatrix}1&1&0&0\\0&0&0&0\\0&0&0&0\\0&0&0&0\end{bmatrix}$$

@2024 M. P. Deisenroth, A. A. Faisal, C. S. Ong. Published by Cambridge University Press (2020)

------------------------------------------------------------------

4.7Are the following matrices diagonalizable? If yes, determine their diagona form and a basis with respect to which the transformation matrices are di agonal. If no, give reasons why they are not diagonalizable.

a.

$$A=\begin{bmatrix}0&&1\\-8&&4\end{bmatrix}$$

b.

$$A=\begin{bmatrix}1&1&1\\1&1&1\\1&1&1\end{bmatrix}$$

C.

$$\boldsymbol{A}=\begin{bmatrix}5&4&2&1\\0&1&-1&-1\\-1&-1&3&0\\1&1&-1&2\end{bmatrix}$$

d.

$$A=\begin{bmatrix}5&&-6&&-6\\-1&&4&&2\\3&&-6&&-4\end{bmatrix}$$

4.8 Find the SVD of the matrix

$$\boldsymbol{A}=\begin{bmatrix}3&2&&2\\2&3&&-2\end{bmatrix}\:.$$

4.9Find the singular value decomposition of

$$A=\begin{bmatrix}2&&2\\-1&&1\end{bmatrix}.$$

4.10 Find the rank-1 approximation of

$$\boldsymbol{A}=\begin{bmatrix}3&2&&2\\2&&3&&-2\end{bmatrix}$$

4.11 Show that for any $A\in\mathbb{R}^{m\times n}$ the matrices $A^{\top}A$ and $AA^\top$ possess the same nonzero eigenvalues 4.12 Show that for $x\neq0$ Theorem 4.24 holds, i.e., show that

$$\max_{x}\frac{\|Ax\|_{2}}{\|x\|_{2}}=\sigma_{1}\:,$$

where 01 is the largest singular value of $A\in\mathbb{R}^{m\times n}$