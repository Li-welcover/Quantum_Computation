## Cyclic Matrices and Fourier Matrices
$$
C = \begin{pmatrix}
c_{0} & c_{1} & c_{2} & \dots  & c_{n-1}\\
c_{n-1} & c_{0} & c_{1} & \dots  & c_{n-2}\\ \\
 & \vdots & & \ddots & \vdots \\
c_{1} & c_{2} & c_{3} & c_{4} & c_{5}
\end{pmatrix}
$$
Each row changes by moving the previous row backwards 1 position and the last element of the row takes the first position. 
### Examples
$$
P = \begin{pmatrix}
0 & 1 & 0 \\
0 & 0 & 1 \\
1 & 0 & 0
\end{pmatrix}
$$
$$
P^{2} = \begin{pmatrix}
0 & 0 & 1 \\
1 & 0 & 0 \\
0 & 1 & 0
\end{pmatrix}
$$
$$
P^3 = I
$$
We could define such matrix $P_{n}$, so $P_{n}^n$ is $I$. 
So all cyclic matrices are simply the polynomial of $P_{n}$. 
$$
C = c_{0}I+c_{1}P+c_{2}P^{2}+\dots
$$
The effect of a cyclic matrix acting on a vector is simply moving the terms forward for one position and grab the first all the way down to the last: 
$$
P\begin{pmatrix}
x_{0} \\
x_{1} \\
\vdots \\
x_{n-1}
\end{pmatrix} = \begin{pmatrix}
x_{n-1} \\
x_{0} \\
\vdots \\
x_{n-2}
\end{pmatrix}
$$
### Eigenvalues and Eigenvectors
$$
\det (\lambda I-P) = \lambda^{n} -1 =0
$$
$$
\lambda_{k} = e^{i\frac{2\pi}{n}k} = \omega^{k}
\tag 1
$$
That's how we find eigenvalues of $P$. And as for eigenvectors they should be straight forward after we contemplate the case when k=1, the first eigenvector is: 
$$
P\begin{pmatrix}
\omega^{0} \\
\omega^{1} \\
\omega^{2} \\
\vdots \\
\omega^{n-1}
\end{pmatrix}
 = 
 \begin{pmatrix}
\omega^{1} \\
\omega^{2} \\
\omega^{3} \\
\vdots \\
\omega^{n-1} \\
\omega^{0}
\end{pmatrix}
 = \omega\begin{pmatrix}
\omega^{0} \\
\omega^{1} \\
\omega^{2} \\
\vdots \\
\omega^{n-1}
\end{pmatrix}
$$
Hence, the jth eigenvector is just 
$$
\begin{pmatrix}
\omega^{0\times j} \\
\omega^{1\times j} \\
\omega^{2\times j }\\
\omega^{3\times j} \\
\vdots
\end{pmatrix}
$$
### Discrete Fourier Transform(DFT)
Note that
$$
\braket{ x_{j} | x_{k} }  = \sum \bar{\omega}^{jl}\omega ^{kl} = 
\left\{
\begin{align}
 & n  & j=k\\
 & 0 & j \neq k
\end{align}
\right.
\tag 2
$$
therefore the eigenvalues are mutually orthogonal. 
We define the Fourier Matrix as a unitary operator: 
$$
F =(\vec{v}_{0},\vec{v}_{1},\vec{v}_{2}\dots \vec{v}_{n-1})
$$
The normalized ver. of Fourier matrix is 
$$
F_{nml} = \frac{1}{\sqrt{ n }} (\vec{v}_{0},\vec{v}_{1},\vec{v}_{2}\dots \vec{v}_{n-1})
$$
It is discrete in the sense that it transforms an array signals to another array discretely: 
$$
\begin{pmatrix}
A_{1} \\
A_{2} \\
A_{3} \\
\vdots \\ 
\end{pmatrix}
 = 
 F 
 \begin{pmatrix}
a_{1} \\
a_{2} \\
a_{3} \\
\vdots \\
\end{pmatrix}
$$
This is equivalent when we divide the interval infinitesimal and we get the continuum FT with a integral symbol. 
#### Inverse Of Fourier matrix
From (2) we know that: 
$$
(\bar{F}F)_{jk} = n\delta_{jk}
$$
which means 

$$
F^{-1} = \frac{1}{n}\bar{F}

$$
However DFT needs to compute $O(n^2)$ steps to get to the final result, here comes a method for computing DFT in $O(n)log_2n$ operations. 

### FFT
$$
F = \frac{1}{\sqrt{ n }}\begin{pmatrix}
1 & 1 & 1 & 1 \\
1 & \omega & \omega^{2} & \omega^3 \\
1 & \omega^{2}  & \omega^4 & \omega^6 \\
1 & \omega^{3} & \omega^6 & \omega^9
\end{pmatrix}
\to

$$
$$
F_{n} = 
\begin{pmatrix}
I_{n/2} &  \Lambda_{n/2} \\
I_{n/2}  & - \Lambda _{n/2}
\end{pmatrix}
\begin{pmatrix}
F_{n/2} &  0 \\
0 &  F_{n/2} 
\end{pmatrix}
(P)
$$
$(P)$ is the permutation matrix which gather the odd and even columns of the vector being operated in piles. For example
$$
P_{4} = 
\begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 0 & 1
\end{pmatrix}
$$
$$
P_{6} = 
\begin{pmatrix}
1 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 1 & 0 \\
0 & 1 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 1 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 1
\end{pmatrix}
$$
$$
P = \begin{pmatrix}
I_{odd} \\
I_{even}
\end{pmatrix}
$$
where the odd and even part are stretched to become a sheered identity. 
#### Calculate its complexity
For the permutation matrix, it is equivalent to reshuffling the signal array(or vector, say). So it could be done in some constant time, the complexity is $O(1)$. 
The middle matrix has half its terms 0, the complexity is just $O(2n)$. I don't know nothing about computation theory so far so let's just accept it. 
And the leftmost one gives the complexity of $n$. 
Sum them up to get 
$$
O = O(1) + O(2n) + O(n) = O(3n+1)
$$
More generally $O(n^{2})$ is then reduced to $O(n\log n)$. 



