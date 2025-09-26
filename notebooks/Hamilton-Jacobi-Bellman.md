# Hamilton-Jacobi-Bellman Stochastic Control Equations

The setup of the problem follows that of a traditional optimisation problem. The difference is that dynamics may be governed by an SDE. 

Let $B_t$ be an n-dimension Brownian Motion, on a filtered probability space $(\Omega, \mathcal{F}, P)$. The stochastic dynamics of the state variable $X(t) \in O$ are given by the following SDE

$$X(t) = \mu(X(t), u(t), t)dt + \sigma(X(t), u(t), t)dB(t) \quad t \geq 0, X(0) = x_0$$

where $f$ and $\sigma$ are continuous with bound differentials in $x$ and $t$, and grow at most linearly with $u$.

<!-- Derive briefly HJB -->

The final HJB equation is therefore a partial differential equation: 

$$0 = \sup_{u \in \mathcal{U} }\{ A^uV(X_t,t) + L(X_t,u(t),t) \}$$ Where $A^u$ is the backward Kolmogorove