> [!theorem] 密度矩阵的演化方程
> $$\frac{\partial \rho}{\partial t}=\frac{1}{i\hbar}[H,\rho]$$
> 密度矩阵$$\rho(t)=\Sigma_j p_j|\psi_j\rangle\langle \psi_j|$$

>[!proof]
>$$\frac{\partial \rho }{\partial t}=\Sigma _j(p_j\frac{\partial|\psi_j\rangle }{\partial t}\langle \psi_j|+p_j|\psi_j\rangle\frac{\partial \langle \psi_j|}{\partial t})$$
>代入薛定谔方程(注意复共轭的乘法顺序)
>$$\begin{cases}i\hbar\frac{\partial |\psi\rangle}{\partial t}=\hat H|\psi\rangle，\\-i\hbar\frac{\partial \langle \psi|}{\partial t}=\langle \psi|\hat H，\end{cases}$$
>易证上命题
>方程的解：$$\rho(t)=U \rho(0)U^\dagger$$
>其中$$U=e^{\frac{-it\hat{H}}{\hbar}}$$

> [!Properties]
>  波函数的范数$$||\Psi(x,t)||=\sqrt{\langle \Psi|\Psi\rangle}=const.$$
>  态矢正交归一$$\langle \psi_i||\psi_j\rangle=\delta_ij$$

> [!exercise1] 
 > 已知态矢$|\psi_1\rangle,|\psi_2\rangle$满足定态薛定谔方程$$\begin{cases}H_0|\psi_1\rangle=E_1|\psi_1\rangle，\\H_0|\psi_2\rangle=E_2\psi_2\rangle，\end{cases}$$
 > 考虑扰动
 > $$H=H_0+W=
 \begin{bmatrix}
E_1+W_{11}& W_{12}  \\
W_{21}& E_2+W_{22}  \\
\end{bmatrix}$$
  > 其中$W_{11}=W_{22}+0$,求H的本征值和本征矢
 > 
>>[!proof] 解
>>先列出矩阵H的本征方程
>>$$\begin{equation}\begin{aligned}
&\text{det}(H-\lambda I)=
\begin{vmatrix}
E_1-\lambda& W_{12}  \\
W_{21}& E_2-\lambda  \\
\end{vmatrix}=0 \\ &\Rightarrow \lambda^2-(E_1-E_2)\lambda+E_1E_2-W_{12}W_{21}=0\end{aligned}\end{equation}$$
>>求根公式解出
>>$$\begin{equation}\begin{aligned}
 \lambda=E_pm&=\frac{E_1+E_2}{2}\pm \sqrt{(E_1+E_2)^2-4(E_1E_2-W_{11}W_{22})}\\&=E_m+\sqrt{\Delta^2+|W_{12}|^2}
 \\&=E_m\pm \Delta\sec\theta
\end{aligned}\end{equation}$$
 where$E_m=\frac{E_1+E_2}{2}$,$\tan\theta=\frac{|W_{12}|}{\Delta}$,$W_{12}=|W_{12}|e^{i\phi}$
 >> 设本征矢 $\vec x,(H-E_\pm)\vec x=0$,$$H=\begin{pmatrix}
E_1 & W_{12}  \\
W_{21}& E_{2} 
\end{pmatrix}$$ 
>>$$\begin{equation}\begin{aligned}
>>H-E_\pm&=\begin{pmatrix}
\Delta \mp\Delta\sec\theta & \Delta\tan\theta \; e^{i\phi}  \\
\Delta\tan\phi \; e^{-i\phi} & -\Delta\mp\Delta\sec\theta 
\end{pmatrix}\\&=\Delta\sec\theta\begin{pmatrix}
\cos\theta\mp 1 & \sin\theta\;e^{i\phi} \\
\sin\theta\;e^{i\phi} & -\cos\theta\mp1 
\end{pmatrix}
\end{aligned}\end{equation}
>>$$
>>为了拿掉 $\mp1$,用升幂公式$\cos\theta=2\cos^2{\frac{\theta}{2}}-1$
>>$$\begin{equation}\begin{aligned}
>>H-E_+&=\Delta\sec\theta\begin{pmatrix}
-2\sin^2\frac{\theta}{2} & 2\sin\frac{\theta}{2}\cos\frac{\theta}{2}e^{i\phi} \\
\sin\frac{\theta}{2}\cos\frac{\theta}{2} e^{-i\phi}& -2\cos^2\frac{\theta}{2} 
\end{pmatrix}\\&=\begin{pmatrix}
2\sin\frac{\theta}{2} & 0\\
0 &2\cos\frac{\theta}{2} \ 
\end{pmatrix}\begin{pmatrix}
-\sin\frac{\theta}{2} & \cos\frac{\theta}{2}e^{i\phi}  \\
\sin\frac{\theta}{2} e^{-i\phi} & -\cos\frac{\theta}{2}
\end{pmatrix}
\end{aligned}\end{equation}$$
>>代入本征方程解得
>>$$\vec x=
\begin{cases}
|\psi_+\rangle=\begin{pmatrix}
\cos\frac{\theta}{2}  \\
 \sin\frac{\theta}{2} e^{-i\phi}
\end{pmatrix}\\
|\psi_-\rangle=\begin{pmatrix}
\sin\frac{\theta}{2} e^{-i\phi} \\
\cos\frac{\theta}{2}
\end{pmatrix}
\end{cases}$$
>>特别地，当$|\Delta|\gg|W_{12}|$时，可以直接用题目给的条件秒解态矢。
>>泰勒展开：$$E_\pm=E_m\pm\Delta(1+\frac{1}{2}|\frac{W_{12}}{\Delta}|^2+\cdots)$$
>>thus
>>$$
\begin{cases}
|\psi_+\rangle\approx e^{-i\frac{\phi}{2}}(|\psi_1\rangle+e^{i\phi}\frac{|W_{12}|}{2\Delta}|\psi_2\rangle)\\
|\psi_-\rangle\approx e^{-i\frac{\phi}{2}}(|\psi_2\rangle-e^{-i\phi}\frac{|W_{12}|}{2\Delta}|\psi_1\rangle)
\end{cases}
$$

>[!exercise2] 
>求系统的振荡周期
 






