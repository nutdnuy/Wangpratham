---
title: Example of Solving Stochastic Differential Equation
summary: The project was the WorldQuant University homework in MScFE 622 Continuous-time Stochastic Processes.
date: 2020-08-10
math: true
authors:
  - admin
tags:
  - Stochastic Processes
  - Brownian Motion
image:
  caption: ''
---

<div style="font-size: 16px;">

## Note

The project was the WorldQuant University homework in MScFE 622 Continuous-time Stochastic Processes.


## Question 

Let $W = \{W_t: t \geq 0\}$ be a Brownian motion on $(\Omega, \mathcal{F}, \mathbb{F} = (\mathcal{F}_t)_{t \geq 0}, \mathbb{P})$. Fix $\alpha, \ \beta \in \mathbb{R}$ and consider the following SDE:

$$
d X_t = \frac{\beta - X_t}{T-t}dt + d W_t, \ \ \ 0< t < T, \ (E1)
$$

and 

$$X_0 = \alpha, \ X_T = \beta.$$

A solution to this SDE, with the given boundary conditions, is called a Brownian bridge. By applying Ito's lemma to  $Y_t := f(t,X_t) = \frac{X_t}{T-t}$, solve this SDE and find the distribution, mean, and variance of $X_t$ where $0 < t < T.$\\


## Ans

We apply the Ito lemma to the process $Y_t =\frac{X_t}{T-t}$, 

$$
\begin{align}
d Y_t &= \pdv{f(t,X_t)}{t}dt + \pdv{f(t,X_t)}{X_t} d X_t + \frac{1}{2}\pdv[2]{f(t,X_t)}{X_t} d X_t^2 & \text{Ito's Lemma}\\
&= \frac{X_t}{(T-t)^2}dt + \frac{1}{(T-t)}d X_t + 0   & \text{Differentiating}  \\
&= \frac{X_t}{(T-t)^2}dt + \frac{1}{(T-t)}\left(\frac{\beta - X_t}{T-t}dt + d W_t\right)   & \text{Using (\ref{BB})}  \\
&= \frac{\beta}{(T-t)^2}dt + \frac{1}{(T-t)}d W_t   & \text{Rearranging} \ (E3).
\end{align}
$$

Next we will find the solution of the process $Y_t$ in (E3) by integration,

$$
\begin{align}
Y_t &= Y_0 + \int_0^t \frac{\beta}{(T-s)^2}ds + \int_0^t \frac{1}{(T-s)}d W_s & \text{Integrating (\ref{DYR})}  \nonumber\\
      &= Y_0 + \frac{2\beta}{T-t} -\frac{2\beta}{T} + \int_0^t \frac{1}{(T-s)}d W_s &   \nonumber \\
      &= \frac{\alpha}{T-t} + \frac{2\beta}{T-t} -\frac{2\beta}{T} + \int_0^t \frac{1}{(T-s)}d W_s & Y_0 = \frac{X_0}{T-t} =  \frac{\alpha}{T-t}  \nonumber  \\
      &= \frac{\alpha+2\beta}{T-t} -\frac{2\beta}{T} + \int_0^t \frac{1}{(T-s)}d W_s &  \nonumber
\end{align}
$$

Therefore, 

$$
\begin{align}
X_t &=  (T-t)\left(\frac{\alpha+2\beta}{T-t} -\frac{2\beta}{T} + \int_0^t \frac{1}{(T-s)}d W_s \right)\nonumber \\
&=  \alpha+2\beta \left( \frac{t}{T }\right) + (T-t)\int_0^t \frac{1}{(T-s)}d W_s  \ (E4).\\
\end{align}
$$

Using the boundary condition $X_T = \beta$,

$$
\begin{align}
  \beta &= \alpha+2\beta \left( \frac{T}{T }\right) + (T-T)\int_0^T \frac{1}{(T-s)}d W_s \\
            & = -\alpha.
\end{align}
$$

Then the solution in (E4) can be rewritten as,

$$
X_t = \alpha \left( 1 -\frac{2t}{T }\right) + (T-t)\int_0^t \frac{1}{(T-s)}d W_s.
$$

Therefore, $X_t$ has a normal distribution with the mean,

$$\mathbb{E}(X_t) = \alpha \left( 1 -\frac{2t}{T }\right),$$

and the variance,

$$\text{Var}(X_t) = \text{Var}\left((T-t)\int_0^t \frac{1}{(T-s)}d W_s\right)= (T-t)^2\int_0^t \frac{1}{(T-s)^2}ds  =2(T-t)^2\left(\frac{1}{T-t}  - \frac{1}{T}\right),$$
i.e. $X_t \sim N\left(\alpha \left( 1 -\frac{2t}{T }\right),2(T-t)^2\left(\frac{1}{T-t}  - \frac{1}{T}\right)\right)$.

</div>
