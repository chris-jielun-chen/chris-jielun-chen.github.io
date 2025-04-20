--- 
layout: noheader 
title: "Interaction picture and beta function" 
date: 2025-04-19
--- 

This post is about the equivalence between two derivations of perturbation expansion.

<em>Interaction picture</em> frequently arises when analyzing a perturbed Hamiltonian of the form $\hat{H} = \hat{H}_0 + \xi \hat{V}$. For example, consider the task of estimating the partition function $Z = \text{Tr}(\exp(-\beta \hat{H}))$. We first do a "harmless" factorization by seperating the free part out, and call the rest $\hat{S}(\beta)$

$$
    e^{-\beta(\hat{H}_0+\xi \hat{V})}
    \;=\;
    e^{-\beta \hat{H}_0}\,
    \underbrace{e^{\beta \hat{H}_0}\,e^{-\beta(\hat{H}_0+\xi \hat{V})}}_{\displaystyle \hat{S}(\beta)},
$$

and the <em>interaction-picture operator</em> $\hat{V}_I(\tau) = e^{\tau \hat{H}_0} \hat{V} e^{-\tau \hat{H}_0}$ naturally appears by differentiating $\hat{S}(\tau)$,

$$
\begin{split}
\frac{d\hat{S}}{d\tau}
&=
\hat{H}_0\,e^{\tau \hat{H}_0}\,e^{-\tau(\hat{H}_0+\xi \hat{V})}
-
e^{\tau \hat{H}_0}\,
(\hat{H}_0+\xi \hat{V})\,e^{-\tau(\hat{H}_0+\xi \hat{V})}
\nonumber\\
&=
-\xi\,
\underbrace{e^{\tau \hat{H}_0}\,
            \hat{V}\,
            e^{-\tau \hat{H}_0}}_{\displaystyle \hat{V}_I(\tau)}
\,\hat{S}(\tau).
\end{split}
$$

With $\hat{S}(0) = I$, we can integrate both side of the equation and get

$$
\hat{S}(\beta)=I
\;-\;\xi\!\!\int_{0}^{\beta}\!\!d\tau_{1}\,
            \hat{V}_I(\tau_{1})\,
            \hat{S}(\tau_{1}) .
$$

and thus by repeatively substituting $\hat{S}$ to itself, we obtain the series expansion

$$
   Z = \text{Tr}\left(e^{\beta \hat{H}_0} \hat{S}(\beta)\right) = \sum_{m \geq 0} (-\xi)^m \int_{0}^{\beta} d\tau_1 ...\int_{0}^{\tau_{m-1}} d\tau_{m} \text{Tr}\left(e^{\beta \hat{H}_0} \hat{V}(\tau_1) ... \hat{V}(\tau_m)  \right)
$$

However, one can also consider a direct Taylor expansion

$$
\begin{split}
    Z &= \sum_{m \geq 0} \frac{\xi^m}{m!} \frac{\partial^m Z}{\partial \xi^m} \Bigg |_{\xi = 0}\\
\end{split}
$$

and each term takes a different form. For example the second order looks like

$$
\begin{split}
    \frac{\partial^2 Z}{\partial \xi^2} &= \text{Tr} \left( \sum_{l=0}^{\infty} \frac{(-\beta)^l}{l!} \frac{\partial^2 }{\partial \xi^2} \hat{H}^l \right) \\
    &=2\text{Tr}\left(\sum_{j,k,p=0}^{\infty} \frac{(-\beta)^{j+k+p+2} }{(j+k+p+2)!} \hat{H}^{j} \hat{V} \hat{H}^{k} \hat{V} \hat{H}^{p} \right)
\end{split}
$$

By the preceding argument we should have

$$
\color{red} 
\int_{0}^{\beta} d\tau_1 \int_{0}^{\tau_{1}} d\tau_{2} \text{Tr}\left(e^{\beta \hat{H}_0} \hat{V}(\tau_1) \hat{V}(\tau_2)  \right) \stackrel{?}{=} \sum_{j,k,p=0}^{\infty} \frac{(-\beta)^{j+k+p+2} }{(j+k+p+2)!} \text{Tr}\left(\hat{H}^{j} \hat{V} \hat{H}^{k} \hat{V} \hat{H}^{p} \right)
$$