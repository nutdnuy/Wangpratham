---
title: Examples of Martingale
summary: The project was the WorldQuant University in MScFE 622 Continuous-time Stochastic Processes.
date: 2020-07-21
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

The project was the WorldQuant University in MScFE 622 Continuous-time Stochastic Processes.

## Question 1

Let $W = \{W_t : t \geq 0\}$ be a Brownian motion on $(\omega, \mathcal{F}, \mathbb{F} = (\mathcal{F}_t)_{t \geq 0},  \mathbb{P})$

### Question 1.1

Show that $W$ is an $\mathbb{F}$-martingale 

### Ans

We consider the information at the state $s$ such that $s \leq t$. From the assumption $W$ is Brownian motion, that imply $W_t \sim N(0,t)$ and $W_s \sim N(0,s)$. The conditional expectation given the information state $s$ of the Brownian motion is,

$$
\begin{align*}
\mathbb{E}[W_t|\mathcal{F}_s] &= \mathbb{E}[(W_t - W_s + W_s)|\mathcal{F}_s] & \text{Include and exclude rules} \\
&   = \mathbb{E}[(W_t - W_s)|\mathcal{F}_s]  + \mathbb{E}[W_s|\mathcal{F}_s] & \text{Linear property of the expectation } \\
& = \mathbb{E}[(W_t - W_s)] +  W_s & \text{$W_t - W_s \sim N(0,t-s)$ and it is independent of $\mathcal{F}_s$}\\
&   = \mathbb{E}[W_t] - \mathbb{E}[W_s] + W_s & \text{Linear property of the expectation} \\
& = 0 - 0+ W_s & \text{$W_t \sim N(0,t)$ and $W_s \sim N(0,s)$} \\
& = W_s.
\end{align*} 
$$

Therefore, $W$ is an $\mathbb{F}-$martingale. 

### Question 1.2
Show that for every $\alpha \in \mathbb{R}$, the process

$$X_t^{\alpha} =: \exp(\alpha W_t - \frac{1}{2}\alpha^2t)$$
is an $\mathbb{F}$-martingale

### Ans

We know that $W_t \sim N(0,t)$. From the moment generating of the normal distribution ($X \sim N(\mu,\sigma^2)$ then $M_X(\alpha) = \exp(\alpha\mu +  \frac{1}{2}\sigma^2\alpha^2)$,  the relationship between the $W_t-W_s \sim N(0,s-t)$ and its moment generating function is given by

$$
\begin{align}
M_{W_t-W_s}(\alpha) &= \mathbb{E}(\exp(\alpha(W_t-W_s))) \nonumber\\
 &=  \exp(\alpha\mu +  \frac{1}{2}\sigma^2\alpha^2) & W_t - W_s \sim N(0,s-t) \nonumber\\
& = \exp(\alpha (\mathbb{E}(W_t) - \mathbb{E}(W_s)) +  \frac{1}{2}(s-t)\alpha^2) & \mu = \mathbb{E}(x),\ \sigma^2 = s-t  \nonumber\\
& =  \exp(\frac{1}{2}(s-t)\alpha^2) & \mathbb{E}(W_t) = \mathbb{E}(W_s) = 0. \ (E3)
\end{align}
$$

Again,  we consider the conditional expected value of the process $X_t^\alpha$,

$$
\begin{align*}
\mathbb{E}[X_t^{\alpha}|\mathcal{F}_s]  &= \mathbb{E}\left[\exp(\alpha W_t - \frac{1}{2}\alpha^2t)\Bigg|\mathcal{F}_s\right] &\text{Given information} \\
& = \mathbb{E}\left[\exp(\alpha(W_t - W_s) + \alpha W_s- \frac{1}{2}\alpha^2t) \Bigg|\mathcal{F}_s\right] &  \text{Include and exclude rules} \\
& =  \mathbb{E}\left[\exp(\alpha(W_t - W_s))\exp(\alpha W_s -\frac{1}{2}\alpha^2t) \Bigg|\mathcal{F}_s\right] &\text{Exponential function's property} \\
& =  \exp(\alpha W_s -\frac{1}{2}\alpha^2t)  \mathbb{E}\left[\exp(\alpha(W_t - W_s)) \Bigg|\mathcal{F}_s\right] &\text{$W_s$ is measurable with respect to $\mathcal{F}_s$} \\
& =  \exp(\alpha W_s -\frac{1}{2}\alpha^2t) \mathbb{E}[\exp(\alpha(W_t - W_s))]&\text{$W_t - W_s \sim N(0,t-s)$ independent of $\mathcal{F}_s$}\\
& =   \exp(\alpha W_s -\frac{1}{2}\alpha^2t)\exp(\frac{1}{2}(s-t)\alpha^2)  &\text{Using MGF (E3)} \\
& =    \exp(\alpha W_s - \frac{1}{2}\alpha^2s)  &\text{Simplifying} \\
& =   X_s^\alpha &\text{From Definition of $X_s^\alpha$} 
\end{align*}
$$

Therefore, $X_t^\alpha$ is an $\mathbb{F}-$martingale for all $\alpha \in \mathbb{R}$. \\


## Question 2

Define the polynomials $H_n(x,y); \ n = 0,1,2,\dots$ by

$$H_n(x,y) = \frac{\partial^n}{\partial \alpha^n} \exp(\alpha x - \frac{1}{2}\alpha^2y) \ \text{at} \ \alpha = 0$$

For example,

$$H_0(x,y) = 1, \ H_(x,y) =x, \ H_2(x,y) = x^2-y, \ H_3(x,y) = x^3-3xy,\ H_4(x,y) = x^4-6x^2y+3y^3, \ \text{etc.}$$

It can be shown (using Taylor series) that

$$X_t^\alpha = \exp(\alpha W_t - \frac{1}{2}\alpha^2t) = \sum_{n = 0}^{\infty} \frac{\alpha^n}{n!}H_n(W_t,t)$$

We now show that $H_n(W_t,t)$ is a martingale for each $n$

### Question 2.1

Let $0 \leq s \leq t$ and $\alpha \in \mathbb{R}$. Explain why for each $F \in \mathcal{F}_s$


$$\int_{F} X_t^\alpha d \mathbb{P} = \int_{F} X_s^\alpha d\mathbb{P}$$

### Ans

This statement can be easily explained by the definition of the conditional expectation,

$$\mathbb{E}(X|F) = \int_F X d\mathbb{P},$$

for $F \in \mathcal{F}$. We use the conditional expectation of the process $X_t^\alpha$, 

$$
X_s^\alpha = \mathbb{E}[(X_t^\alpha|F)]=  \int_{F} X_s^\alpha d\mathbb{P} \ (E1.), 
$$

because of  an $\mathbb{F}$-martingale of $X_t^\alpha$ and the definition of the conditional expectation. We also know that $\mathbb{E}(X_t^\alpha) < \infty$. Then we consider again $X_s^\alpha$,

$$
X_s^\alpha = \mathbb{E}[(X_s^\alpha|F)]=  \int_{F} X_s^\alpha d\mathbb{P} \ (E2.), 
$$

due to $X_s$ is $\mathcal{F}_s$-measurable and the definition of the conditional expectation. Setting $E1 = E2$, 

$$\int_{F} X_t^\alpha d \mathbb{P} = \int_{F} X_s^\alpha d\mathbb{P}$$

### Question 2.2

By differentiating (3a) on both sides $n$ times with respect to $\alpha$ and interchanging the derivative with the integral (no need to justify this step), show that 

$$\mathbb{E}(H_n(W_t,t)|\mathcal{F}_s) = H_n(W_s,s),$$

### Ans

Taking $n$ time derivative respect to $\alpha$, we have

$$
\begin{align*}
\pdv[n]{}{\alpha}\int_{F} X_t^\alpha d \mathbb{P} &= \pdv[n]{}{\alpha}\int_{F} X_s^\alpha d\mathbb{P} &\text{From (3a)}  \\
\int_{F} \pdv[n]{}{\alpha} X_t^\alpha d \mathbb{P} &=\int_{F}  \pdv[n]{}{\alpha} X_s^\alpha d\mathbb{P} & \text{Interchange between} \\
&& \text{derivative and integral} \\
\int_{F} \pdv[n]{}{\alpha}\exp(\alpha W_t - \frac{1}{2}\alpha^2t) d \mathbb{P} &=\int_{F}  \pdv[n]{}{\alpha} \exp(\alpha W_s - \frac{1}{2}\alpha^2s) d \mathbb{P} &\text{Definition of $X_{\cdot}^\alpha$}\\
\int_{F} H_n(W_t,t)  d \mathbb{P} &=\int_{F} H_n(W_s,s)  d\mathbb{P} &\text{Definition of $H_n(x,y)$}\\
\mathbb{E}(H_n(W_t,t)|F)  &= \mathbb{E}(H_n(W_s,s)|F) &\text{Definition of}\\
&&\text{the conditional expectation}\\
\mathbb{E}(H_n(W_t,t)|F)  &=  H_n(W_s,s) &\text{$W_s$ is $F$-measurable}
\end{align*} 
$$

Since $F \in \mathcal{F}_s$, 

$$
\mathbb{E}(H_n(W_t,t)|\mathcal{F}_s)  =  H_n(W_s,s)
$$


### Question 2.3

Conclude that $\{ H_n(W_t,t) : t \geq 0 \}$ is a martingale.


### Ans

From the equation (\ref{4}), the process $\{ H_n(W_t,t) : t \geq 0 \}$ is an $\mathcal{F}_s$-martingale.

</div>
