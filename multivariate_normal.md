## Joint Normal Distribution

We are given two random vectors $X = (X, \dots, X_n)$ and $Y = (Y_1, \dots, Y_m)$ with joint distribution:

$$
\begin{bmatrix}
			X \\ Y
		\end{bmatrix}
		\sim 
		N \left(
			\begin{bmatrix}
				m_X \\ m_Y
			\end{bmatrix}, 
			\begin{bmatrix}
				C_X & C_{XY}\\ 
				C_{YX} & C_Y
			\end{bmatrix} 	
		\right)
$$

### Marginal Distribution for X & Y

Let us define Z as a RV vector as $[X \quad Y]^T$, with 

$$
m_X = [m_X \quad m_Y]^T \quad \text{$n+m,1$ dimensional vector}
$$

$$
C_Z = \begin{bmatrix}
		C_X & C_{XY}\\ 
		C_{YX} & C_Y
	\end{bmatrix}
 \quad \text{$n+m,n+m$ dimensional vector}
$$

$$
\implies Z \sim \mathcal{N}(m_Z,C_Z)
$$

$$
\text{We can write X as}:
X = S_XZ = \begin{bmatrix}
				1 & 0 & 0 \dots 0\\ 
				0 & 1 & 0 \dots 0\\
                    0 & 0 & 1 \dots 0\\
                    \quad \dots\\
                    \quad \dots\\
                    0 & 0 & \dots 0
			\end{bmatrix} * 
   \begin{bmatrix}
				X\\ \dots\\ X_n\\ 
				Y_1\\ \dots\\ Y_m
			\end{bmatrix}\\
$$

$$
\text{Thus $S_X$ is $(n,n+m)$matrix with $s_{ij} = 1$ if ith element in Z is $X_j$}
$$

$$
\text{Now we know that linear transformation of a Normal RV is Normal,i.e.}
$$

$$
W \sim \mathcal{N}(0,\sigma_w^2) \implies aW + c \sim \mathcal{N}(a*0+c,a^2\sigma_w^2)
$$

$$
\text{Hence it follows:}\\
$$

$$
X \sim \mathcal{N}(S_Xm_Z,S_X * C_Z * S_X^T)\\
$$


$$
\implies S_X * m_Z = \begin{bmatrix}
				1 & 0 & 0 \dots 0\\ 
				0 & 1 & 0 \dots 0\\
                    0 & 0 & 1 \dots 0\\
                    \quad \dots\\
                    \quad \dots\\
                    0 & 0 & \dots 0
			\end{bmatrix}_{n,n+m} {*} \begin{bmatrix}
				m_{X}\\ \dots\\ m_{X_n}\\ 
				m_{Y_1}\\ \dots\\ m_{Y_m}
			\end{bmatrix}\\
   = \begin{bmatrix}
				m_{X}\\ \dots\\ m_{X_n}\\ 
				0\\ \dots\\ 0
			\end{bmatrix} = m_X\\
$$

$$
\implies S_X * C_Z * S_X^T =\begin{bmatrix}
				1 & 0 & 0 \dots 0\\ 
				0 & 1 & 0 \dots 0\\
                    0 & 0 & 1 \dots 0\\
                    \quad \dots\\
                    \quad \dots\\
                    0 & 0 & \dots 0
			\end{bmatrix}_{n,n+m} * \begin{bmatrix}
		C_{X_{n,n}} & C_{{XY}_{n,m}}\\ 
		C_{YX_{m,n}} & C_{Y_{m,m}}
	\end{bmatrix} * \begin{bmatrix}
				1 & 0 & 0 \dots 0\\ 
				0 & 1 & 0 \dots 0\\
                    0 & 0 & 1 \dots 0\\
                    \quad \dots\\
                    \quad \dots\\
                    0 & 0 & \dots 0
			\end{bmatrix}^T_{n+m,n}
$$

$$
= \begin{bmatrix}
		C_{X_{n,n}} & C_{XY_{n,m}}
	\end{bmatrix}_{n,n+m} * \begin{bmatrix}
				1 & 0 & 0 \dots 0\\ 
				0 & 1 & 0 \dots 0\\
                    0 & 0 & 1 \dots 0\\
                    \quad \dots\\
                    \quad \dots\\
                    0 & 0 & \dots 0
			\end{bmatrix}^T_{n+m,n}= C_X\\
$$

Hence we have proved that marginal distribution of X

$$
\implies X \sim \mathcal{N}(S_X m_Z,S_X * C_Z * S_X^T) = \mathcal{N}(m_X,C_X)
$$

We can use the same approach to prove for Y



### Conditional Distribution for X given Y
