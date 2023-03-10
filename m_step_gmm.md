### Proof of M-step of GMM

We have to maximize

$$
Q(\theta|\theta_k) = \sum_{i=1}^n \sum_{c=1}^C p_{i, c} \log \pi_c
+ \sum_{i=1}^n \sum_{c=1}^C p_{i, c} \log \phi(x_i|\mu_c, \Sigma_c)
$$


wrt $\theta^{k+1}=\{\pi_c,\mu_c, \Sigma_c\}$, subject to $\sum \pi_c = 1$\\

Hence we can use the Lagrange approach, with the Lagrange function given as:

$$
L(\lambda) = \sum_{i=1}^n \sum_{c=1}^C p_{i, c} \log \pi_c
+ \sum_{i=1}^n \sum_{c=1}^C p_{i, c} \log \phi(x_i|\mu_c, \Sigma_c) - \lambda(\sum_{c=1}^C \pi_c-1)
$$

First order optimality condition:
\begin{equation}
\begin{split}
\nabla_{\lambda } Q= 0\\
\nabla_{\pi_c } Q = 0\\
\nabla_{\mu_c } Q= 0\\
\nabla_{\sigma_c } Q= 0\\
\end{split}
\end{equation}

With 
$$
\nabla_{\lambda } Q = \sum_{c=1}^C \pi_c=1
$$

With 
\begin{equation}
\begin{split}
\nabla_{\pi_c } Q = \nabla_{\pi_c } (\sum_{i=1}^n \sum_{c=1}^C p_{i, c} \log \pi_c - \lambda(\sum_{c=1}^C \pi_c-1))\\
= \frac{\sum_{i=1}^n p_{i, c}}{\pi_c} - \lambda = 1
\implies \pi_c = \frac{\sum_{i=1}^n p_{i, c}}{\lambda}\\
\text{But from constraint } \sum_{c=1}^C \pi_c=1\\
\implies \sum_{c=1}^C \pi_c = \sum_{c=1}^C \frac{\sum_{i=1}^n p_{i, c}}{\lambda} = 1\\
\lambda = \sum_{c=1}^C \sum_{i=1}^n p_{i, c} = \sum_{i=1}^n \sum_{c=1}^C p_{i,c} = n\\
\implies \pi_c = \frac{\sum_{i=1}^n p_{i, c}}{n}
\end{split}
\end{equation}

Similarly for $\mu_c$
\begin{equation}
\begin{split}
\nabla_{\mu_c } Q =0\\
\log \phi(x_i|\mu_c, \Sigma_c) \propto -\frac{1}{2}log(det(\Sigma_c)) -\frac{1}{2} ((x_i-\mu)^T\Sigma_c^{-1}(x_i-\mu_c))\\
\propto -log(det(\Sigma_c)) -((x_i-\mu)^T\Sigma^{-1}(x_i-\mu_c))\\
\nabla_{\mu_c} Q = -\nabla_{\mu_c} \big(\sum_{i=1}^n \sum_{c=1}^C p_{i, c} (log(det(\Sigma_c)) +((x_i-\mu)^T\Sigma^{-1}(x_i-\mu_c)))\big)\\
= \sum_{i=1}^n (p_{i, c} * (2 \Sigma_c^{-1}(x_i-\mu_c))) = 0\\
= \sum_{i=1}^n (p_{i, c} * (x_i-\mu_c)) = 0\\
\implies \sum_{i=1}^n p_{i, c} * x_i = (\sum_{i=1}^n p_{i, c})\mu_c\\
\implies \mu_c = \frac{\sum_{i=1}^n p_{i, c} * x_i}{\sum_{i=1}^n p_{i, c}}
\end{split}
\end{equation}

Similarly for $\Sigma_c$
\begin{equation}
\begin{split}
\nabla_{\Sigma_c^{-1} } Q =0\\
\nabla_{\Sigma_c^{-1} } Q = -\nabla_{\Sigma_c^{-1}} \big(\sum_{i=1}^n \sum_{c=1}^C p_{i, c} (log(det(\Sigma_c)) +((x_i-\mu)^T\Sigma_c^{-1}(x_i-\mu_c)))\big)\\
= \sum_{i=1}^n (p_{i, c} * \big(\Sigma_c^T + ((x_i-\mu_c)(x_i-\mu_c)^T)^T\big)) = 0\\
\sum_{i=1}^n (p_{i, c})\Sigma_c^T = \sum_{i=1}^n (p_{i, c} * (x_i-\mu_c)(x_i-\mu_c)^T)^T\\
\implies \Sigma_c = \frac{ \sum_{i=1}^n (p_{i, c} * (x_i-\mu_c)(x_i-\mu_c)^T}{\sum_{i=1}^n p_{i, c}}
\end{split}
\end{equation}
