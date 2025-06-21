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

# Lie Algebra
\[A,B]=AB-BA


# Matrices In Operation
## Matrix and Operator
$A=(a_{ij})$ is dependent to coordinate systems. 
### Decompositions

#### Spectral decomposition

> [!theorem]
> $$A=(\lambda_i|i\rangle...)$$
> where $|i\rangle$ are orthonormal bases. 

A as an operator could be decomposed as a matrix with respect to a set of bases by:
$$
A(|1\rangle,|2\rangle,|3\rangle,|4\rangle,|5\rangle)=(A|i\rangle,A|j\rangle...)
$$

> [!lemma] Invariants
> $trA=\sum\lambda_i$
> $detA=\prod\lambda_i$

> [!bug]
>>[!quote]
>>>[!theorem] Theorem
>Eigenvalues of a Hermitian matrix are real

#### Schur Decomposition
Actually most of the matrices we write are diagonalizable, they belong to a big family of matrices in all complex matrices. The true problem is, what is the *largest* family of matrices that could be diagonalized by some *unitary matrix*? Her comes the answer: *the normal matrices*. We'll prove this later on. 

> [!Lemma] Lemma (Schur Decomposition)
> For any arbitrary matrix, there exists some unitary operator, that sandwiches it into some upper-triangular matrix. 
> $$Q^TAQ=(\text{uppertriagular}) $$

> [!quote] Householder Transformation (Reflection about a mirror) 
>$H=I-2ww^\dagger$, in which $w\in \mathcal V$, $||w||=1$, and $w$ is the normal vector perpendicular to the mirror plane. 
>For example, $Hx=x-2w(w^\dagger x)$. 
>
> >[!quote] Properties
> >$$H^\dagger=H=H^{-1}$$
> >which means a reflection is unitary, and conduct 2 reflections in a row we get the original vector. And hence we have, for all x in $\mathcal V$, there exists an H, so that $Hx=\sigma e_1$
#### Polar Decomposition
An operator $A$ could be split into a unitary operator and an operator that is uniquely well defined: 

> [!theorem] Polar Decomposition
> $$
> \begin{align}
> A  & = UJ = KU \\
> J &  = \sqrt{ A^{\dagger}A } \\
> K &  = \sqrt{ AA^{\dagger} }
> \end{align}
> $$
> And the corresponding unitary matrix is just with column vectors $| \psi_{i}\rangle = A|i\rangle$, and undergo Gram-Schmidt to get the columns $\ket{e_{i}}$.  
> Note that $J$ and $K$ are *Hermitian*. 

Here comes the proof: 

> [!proof]
> Just let $J$ be $\sqrt{A^{\dagger}A}$, and spectral decomposition gives: 
> $$
> J = \lambda_{i}|i\rangle\langle i|
> $$
> Hence we have: 
> $$
> \begin{align}
> |\psi_{i}\rangle &  = A|i\rangle \\
> \langle\psi_{i}|\psi_{j}\rangle &  = \langle i|A^{\dagger}A|j\rangle \\
>  &  = \bra{i}J^{2}\ket{j}  \\
>  &  = \lambda_{i}^{2}\delta _{i}^{j}
> \end{align}
> $$
> which means that $\ket{\psi_{i}}$ is a set of orthogonal vectors, but not yet a complete set of bases. What we gonna do is to extend it by Gram - Schmidt to get: 
> $$
> \ket{e_{i}}  = \frac{{\ket{\psi_{i}} }}{\lambda_{i}}
> $$
> Construct a unitary matrix with: 
> $$
> \begin{align}
> U  & = \sum\ket{e_{i}} \bra{i}  \\
>  &  =\ket{e_{i}} \bra{i} \tag{Einsein's Summation convention}
> \end{align}
> 
> 
> $$
> 
> > [!proof] To show that $U$ is unitary: 
> > $$
> > \begin{align}
> > U^{\dagger}U\ket{k}   & = \ket{i}\braket{ i | j } \braket{ j | k }   \\
> >  &  = \ket{i} \delta_{i}^{j}\delta_{j}^{k} \\
> >  &  = \ket{k } 
> > \end{align} 
> > $$
> > Now consider a random basis in the vector space: 
> 
> $$
> \begin{align}
> UJ\ket{k}   & = \ket{e_{i}} \braket{ i | j }  \braket{ j | k } \lambda _{j} \\
>  &  = \ket{e_{i}} \braket{ i | k }  \lambda _{k} \\
>  &  = \lambda_{k} \ket{e_{k}}  \\
>  &  = A\ket{k}  
> \end{align}
> $$
> which means $A = UJ$. 


#### SVD(Singular Value Decomposition)

> [!theorem] Theorem(SVD - Singular Value Decomposition)
> $\forall A\in \mathbb C^{m\times n}$, $\exists U,V$ and a diagonalized matrix $\Sigma$, so that $A=U^\dagger\Sigma V$

> [!proof] Proof 1
> Because $A^{\dagger}A$ is Hermitian, it could be diagonalized as follow: 
> $V^\dagger(A^\dagger A)V=diag(\sigma_i^2...,0,0,0...)=$, for $A^\dagger A$ is half positive-deterministic. 
> $$
> \Sigma_{r}: = diag(\sigma_{r}\dots,0\dots)
> $$
> while all eigenvalues with the indices greater than r is 0. 
> $$
> V^{\dagger}A^{\dagger}AV = \begin{pmatrix}
> \Sigma_{r}^2   &  \\
>  & 0
> \end{pmatrix}\tag 1
> $$
> Part $V$ into $\begin{pmatrix}V_{1}V_{2}\end{pmatrix}$,  and so 
> $$
> \begin{pmatrix}
> V_{1}^{\dagger} \\
> V_{2}^{\dagger}
> \end{pmatrix}
> A^{\dagger}A
> \begin{pmatrix}
> V_{1}V_{2}
> \end{pmatrix}
>  = \begin{pmatrix}
> V_{1}^{\dagger}A^{\dagger}AV_{1} & V_{1}^{\dagger}A^{\dagger}AV_{2} \\
> V_{2}^{\dagger}A^{\dagger}AV_{1} & V_{2}^{\dagger}A^{\dagger}AV_{2}
> \end{pmatrix}\tag 2
> $$
> Hence we have by comparing (1) and (2), 
> $$
> \begin{align}
> V_{1}^{\dagger}A^{\dagger}AV_{1}  & = \Sigma^{2}_{r} \\
> AV_{2} & = 0
\end{align}
> $$
> And because we could calculate $()AV_{1}\Sigma^{-1}_{r})^{\dagger}(AV_{1}\Sigma_{r}^{-1}) = I_{r}$, we could define: 
> $$
> U_{1} := AV_{1}\Sigma_{r}^{-1}
> $$

> [!proof] Proof 2
> From polar decomposition we know that A could be written as: 
> $$
> A = SJ = KS
> $$
> And J could be decomposed into $T\Sigma  T^{\dagger}$, so A could be written as: 
> $$
> 
> \begin{align}
> A &  = ST\Sigma T^{\dagger} \\
>  &  = U\Sigma V \\
> \end{align}
> 
> $$

> [!equation] Thin(Compact) SVD
> $$
> A = U_{1}\Sigma_{r}V_{1}^{\dagger}
> $$

> [!exercise] Exercise1
> What is the polar decomposition of a positive matrix $P$? Of a unitary matrx $U$? Of a Hermitian matrix $H$? 

> [!exercise] Excercise2
> Express the polar decomposition of a normal matrix in the outer product representation. 

> [!exercise] Exercise3
> Fin the left and right polar decomposition of 
> $$
> \begin{pmatrix}
> 1 & 0 \\
> 1 & 1
> \end{pmatrix}
> $$

##### Proof that Normal $\Leftrightarrow$ Diagonalizable
> [!Proof]
> 1. $\Leftarrow$, 
> $$
> \begin{align}
> A  & = U\Lambda U^{\dagger},  \\
A^{\dagger}A  & = U\Lambda^{\dagger}\Lambda U^{\dagger} \\
> AA^{\dagger}  & = U\Lambda\Lambda ^{\dagger}U^{\dagger} \\
 & =A^{\dagger}A
> \end{align}
> $$
> 2. $\Rightarrow$
> Prove it yourself? Have a guess


##### Moore - Penrose General Inverse

> [!Quote] Moore - Penrose General Inverse
> 1. $AXA = A$
> 2. $XAX = X$
> 3. $(AX)^{\dagger} = AX$
> 4. $(XA)^{\dagger} = XA$
> Symbolic representation: 
> $A^+$. 



# Some Useful Matrices
## Pauli Operator
$$\sigma_x = \begin{pmatrix}0&1\\1&0\end{pmatrix},\sigma_y = \begin{pmatrix}0&-i\\i&0\end{pmatrix},\sigma_z = \begin{pmatrix}1&0\\0&-1\end{pmatrix}$$

Trace 0, Hermitian

> [!Properties]
> $$\sigma_i^2=I$$$$\sigma_i\sigma_j=i\epsilon_{ij}^k\sigma_k+\delta_{ij}I$$
> $$[\sigma_i,\sigma_j]=2i\sum{\epsilon_{ijk} \sigma_k}$$

> [!exercise] Exercise ($\epsilon-\delta$ equality)
> $$
> \epsilon_{ijk}\epsilon_{ipq}=\delta_{jp}\delta_{kq}-\delta_{jq}\delta_{kp}
> $$

