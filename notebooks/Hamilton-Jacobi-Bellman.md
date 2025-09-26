# Hamilton-Jacobi-Bellman Stochastic Control Equations

The setup of the problem follows that of a traditional optimisation problem. The d^uifference is that dynamics may be governed by an SDE. 

Let $B_t$ be an n-dimension Brownian Motion, on a filtered probability space $(\Omega, \mathcal{F}, P)$. The stochastic dynamics of the state variable $W(t) \in O$ are given by the following SDE

$$W(t) = \alpha(W(t), u(t), t)dt + \sigma(W(t), u(t), t)dB(t) \quad t \geq 0, W(0) = w_0$$

where $f$ and $\sigma$ are continuous with bound differentials in $w$ and $t$, and grow at most linearly with $u$.

<!-- Derive briefly HJB -->

The final HJB equation is therefore a partial differential equation: 

$$0 = \sup_{u \in \mathcal{U} }\{ A^uV(W_t,t) + L(W_t,u(t),t) \}$$ 
Where $A^u = \partial_t + G^u$ appears in the backward Kolmogorov equation. $G^u$ is the infinitesimal generator of the Markov Semi-group.

$$A^uV(w,t) = \partial_t V(w,t) + \nabla_wV(w,t)\cdot \alpha(w,u,t) + Tr(\sigma(w,u,t)\sigma^T(w,u,t)H\{V(w,t)\})$$

## Merton's Optimal Portfolio Problem
In the case of the Merton portfolio problem with two assets 
Our value function is of the following form 
$$
V(W_t,t) = \sup_{(\pi,c)\in \mathcal{U}}\mathbb{E}\left[ \int_t^Te^{-\rho t} u(c_t)dt + B(W_T,T) \middle| W_t = w_0 \right]
$$

The wealth dynamics are defined by the following coefficients

$$\begin{align*}
u(t) &= (\pi(W_t, t), c(W_t,t))\\
\alpha(W_t,u,t) &= (r + \pi_t(\mu - r)W_t - c_t)\\
\sigma(W_t,u,t) &=  W_t\pi_t\sigma\\
\end{align*}
$$

and the consumption and wealth are subject to the constraints $c_t \geq 0$, $W_t > 0$, $w_0>0$.

With this in hand we can write down the HJB equation explicitely. 

$$
0 = \sup_{(\pi,c)\in \mathcal{U}} \left\{ \partial_tV(w,t) + \partial_wV(w,t)\cdot(r + \pi_t(\mu-r)w - c_t) + \partial_{ww}Vw^2\pi_t^2\sigma^2 + e^{-\rho t}u(c_t) \right\}
$$

If we further make the choice that our Utility comes from the CRRA family of functions we can write down the HJB explicitely 

$$u(c) = \frac{c^{1-\gamma}}{1-\gamma}$$
Where $\gamma$ is relative risk aversion.
With this utility function (1) is analytically solvable.

<!-- Derive the analytical solution here. -->

## Computational solutions to the HJB 


