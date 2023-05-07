### Moment Generating Function (MGF)

Let $X$ be a random variable with pdf $f(x)$. The MGF of $X$ is defined as

$$
G(\theta) = \mathbb E[e^{\theta X}].
$$

Show that 
$$
\mathbb E[X] = \dot{G}(0), \quad \mathbb E[X^2] = \ddot{G}(0). 
$$

#### Answer

We are given, MGF as
$$
G(\theta) = E[e^{\theta X}]
$$

Now by Taylor expansion we have
$$
e^{\theta X} = \sum_{i = 0}^{\infty}\frac{(\theta X)^r}{r!}
$$

This can be expanded as:

$$
e^{\theta X} = 1 + \frac{\theta X}{1} + \frac{(\theta X)^2}{2} + \frac{(\theta X)^3}{6} + ...\\
$$

$$
\text{Taking partial derivative wrt theta}
$$

$$
\frac{\partial e^{\theta X}}{\partial \theta} = 0 + X + (\theta X).X + \theta(...)
$$

similarly,

$$
\frac{\partial^2 e^{\theta X}}{\partial \theta^2} = 0 + 0 + (X).X + \theta(...)
$$

Now

$$
\frac{\partial G(\theta)}{\partial \theta}= E[\frac{\partial e^{\theta X}}{\partial \theta}] \quad \text{By definition of MGF}
$$

$$
\implies \frac{\partial G(\theta)}{\partial \theta}= E[0 + X + (\theta X).X + \theta(...)]
$$

$$
\implies \frac{\partial G(\theta)}{\partial \theta}|_{\theta = 0} = E[X]
$$

$$
\implies \frac{\partial^2 G(\theta)}{\partial \theta^2}|_{\theta = 0} = E[X^2]\\
$$