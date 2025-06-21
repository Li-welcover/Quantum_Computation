# Vector Space
> Addition -- Abel Group: Closed, Associative, Identity(0), Inverse
> Scalar Product: $$\alpha\in\mathcal{F},u\in\mathcal V$$$$(\alpha+\beta)(u+V)=\alpha u+\alpha v+\beta u+\beta v$$
> $$$$


# Inner Product
$(u,u)\geq 0$
$(u,v)=(v,u)^*$
$(u,\alpha v+\beta w)=\alpha(u,v)+\beta(u,w)$

>Example
> $$\langle u | v\rangle=\int_{-1}^1dxw(x)uv$$

## Orthogonality
$(u,v)=0$
## Norm
$||u|| = \sqrt{(u,u)}$
## Angle
$cos\theta = \frac{(u,v)}{||u||||v||}$
# Inner Product Space
## Hilbert Space
Complete
# Dirac Symbol
## Basis
### Orthonormal Basis
Gram-Schmitz Process
bra n ket

## Vector
Is independent to coordinates and could be represented as a column vector given a set of bases
## Matrix and Operator
$A=(a_{ij})$ is dependent to coordinate systems. 
### Spectral decomposition

#### Spectrum of a Operator(with respect to one particular *orthonormal* basis)
$A=(\lambda_i|i\rangle...)$
> Invariants
> $trA=\sum\lambda_i$
> $detA=\prod\lambda_i$

A as an operator could be decomposed as a matrix with respect to a set of bases by:
$$
A(|1\rangle,|2\rangle,|3\rangle,|4\rangle,|5\rangle)=(A|i\rangle,A|j\rangle...)
$$
>Theorem
>Eigenvalues of a Hermitian matrix are real

#### Diagonalizable Matrices
Actually most of the matrices we write are diagonalizable, they belong to a big family of matrices in al complex matrices. The true problem is, what is the *largest* family of matrices that could be diagonalized by some *unitary matrix*? Her comes the answer: the normal matrices. 

> Lemma(Schur Decomposition)
> For any arbitrary matrix, there exists some unitary operator, that sandwiches it into some upper-triangular matrix. 
> $$Q^TAQ=(uppertriagular) $$

> Householder Transformation (Reflection about a mirror)
>$H=I-2ww^\dagger$, in which $w\in \mathcal V$, $||w||=1$. For example, $Hx=x-2w(w^\dagger x)$. 
>Properties
>$H^\dagger=H=H^{-1}$, which means a reflection is unitary, and conduct 2 reflections in a row we get the original vector. 
>And hence we have, for all x in $\mathcal V$, there exists an H, so that $Hx=\sigma e_1$

> Theorem
> Any Normal matrix A could be diagonalized. 
> 
> Proof
> From Schur Lemma, $QAQ=T$, in which 

> Theorem(奇异值分解 SVD)
> $\forall A\in \mathbb C^{m\times n}$, $\exists U,V$ and a diagonalized matrix $\Sigma$, so that $A=U^\dagger\Sigma V$
> Proof
> $V^\dagger(A^\dagger A)V=V \text{diag}(\sigma_i^2...,0,0,0...)V^\dagger =$, for$A^\dagger A$ is half positive-determined.
> 定义$\Sigma _r=\text{diag}(\sigma_1,...,\sigma _r)$
> 
>  
> 
# Dagger Symbol
$\langle x|A|y\rangle=\langle A^\dagger x|y\rangle$
$A^{\dagger\dagger}=A$
$a^\dagger_{ij}=a_{ji}^*$
## Hermitian
$A^\dagger = A$
## Unitary
$A^\dagger=A^{-1}$
## Normal
$A^\dagger A=AA^\dagger$

## Lie Algebra
\[A,B]=AB-BA

## Poisson 

## Pauli Operator
$$\sigma_x = \begin{pmatrix}0&1\\1&0\end{pmatrix},\sigma_y = \begin{pmatrix}0&-i\\i&0\end{pmatrix},\sigma_z = \begin{pmatrix}1&0\\0&-1\end{pmatrix}$$

Trace 0, Hermitian
## Properties
$\sigma_i^2=I$, $\sigma_i\sigma_j=i\epsilon_{ij}^k\sigma_k+\delta_{ij}I$
$[\sigma_i,\sigma_j]=2i\sum{\epsilon_{ijk} \sigma_k}$

> Exercise ($\epsilon-\delta$ equality)
> $\epsilon_{ijk}\epsilon_{ipq}=\delta_{jp}\delta{kq}-\delta_{jq}\delta_{kp}$
