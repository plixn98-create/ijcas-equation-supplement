---
title: Appendix A. Lagrange equation for nominal and actual plant
---

# Introduction

This page provides the detailed derivations of the Lagrange equation corresponding to Eq. (22) for the **nominal** and **actual** plant presented in the paper.

---

## Lagrange Equation

In Eq. (22) of the paper, the Lagrange equation is expressed in the form $$\mathbf{M}\ddot{\mathbf{q}} + \mathbf{C} + \mathbf{G} = \mathbf{B}\mathbf{u}$$:

$$
\begin{bmatrix}
M_{11} & 0 & 0 & M_{14} \\
M_{21} & M_{22} & 0 & 0 \\
0 & 0 & M_{33} & 0 \\
M_{41} & 0 & 0 & M_{44}
\end{bmatrix}
\begin{bmatrix}
\ddot{\phi_x} \\ 
\ddot{\phi_y} \\ 
\ddot{\theta} \\ 
\ddot{\psi}
\end{bmatrix}
+
\begin{bmatrix}
C_1 \\ 
0 \\ 
C_3 \\ 
C_4
\end{bmatrix}
+
\begin{bmatrix}
0 \\ 
0 \\ 
0 \\ 
G_4
\end{bmatrix}
= \begin{bmatrix}
\frac{1}{2} & \frac{1}{2} & 0 \\
0 & 0 & 1 \\
-\frac{R}{W} & \frac{R}{W} & 0 \\
-\frac{1}{2} & -\frac{1}{2} & 0
\end{bmatrix}
\begin{bmatrix}
\tau_{xl} \\ 
\tau_{xr} \\ 
\tau_{y}
\end{bmatrix}
$$

## Nominal Plant

For the nominal plant, Eq. (22) is expressed as follows:

$$
\begin{cases}
M_{11} &= (2m + M)(R^2 + r^2 n_r^2) + 2I_w \\
M_{14} &= M_{41} = MRl\cos(\psi) \\
M_{21} &= \left(m + \frac{1}{2}M\right) r^2 n_r \\
M_{22} &= (2m + M) r^2 \\
M_{33} &= \frac{mW^2}{2} + Ml^2 \sin^2(\psi) + \frac{1}{2R^2} I_w W^2 + I_\theta \\
M_{44} &= Ml^2 + I_\psi
\end{cases}
$$

$$
\begin{cases}
C_1 &= -MRl \sin(\psi) \dot{\psi}^2 \\
C_3 &= 2Ml^2 \sin(\psi)\cos(\psi)\dot{\theta}\dot{\psi} \\
C_4 &= 0 \\
G_4 &= -Mgl \sin(\psi)
\end{cases}
$$

---

## Actual Plant

In the actual plant, $\dot{x}$, $\dot{\theta}_a$, and $\dot{\alpha}$ obtained using Eq. (14) can be converted to the form for $\dot{\phi}_x$ and $\dot{\theta}$ as follows:

$$
\dot{k} = k_{dl} \dot{\phi}_{xl} + k_{dr} \dot{\phi}_{xr} = k_{dx} \dot{\phi}_{x} + k_{d\theta} \dot{\theta} = (k_{dl}+k_{dr}) \dot{\phi}_x + \left( -\frac{W}{2R} k_{dl}+\frac{W}{2R} k_{dr} \right) \dot{\theta} \qquad \text{for } k \in \{x, \theta_a, \alpha \}  
$$

$$
\dot{k} = k_{dl}\dot{\phi}_{xl} + k_{dr}\dot{\phi}_{xr}
= k_{dx}\dot{\phi}_{x} + k_{d\theta}\dot{\theta}
= (k_{dl}+k_{dr})\dot{\phi}_x
+ \left(-\tfrac{W}{2R}k_{dl}+\tfrac{W}{2R}k_{dr}\right)\dot{\theta}
\quad \text{for } k \in \{x, \theta_a, \alpha\}
$$

Thus, for the actual plant, Eq. (22) is expressed as follows:

$$
\begin{cases}
M_{11} &= 2a_{\phi_x} + 2I_w \\  
M_{14} &= M_{41} = b_1 x_{dx} + b_5 \alpha_{dx} \\
M_{21} &= b_2  \\
M_{22} &= 2a_3 \\  
M_{33} &= 2a_{\theta} + \dfrac{1}{2R^2}I_w W^2 + I_{\theta}  \\
M_{44} &=  2a_6 + I_{\psi} = Ml^2  + I_{\psi} \\  
\end{cases}
$$

$$
\begin{cases}
C_1 &= 2 \dot{a}_{\phi_x} \dot{\phi}_x + (\dot{b_1} x_{dx} + b_1 \dot{x}_{dx} + \dot{b_5}\alpha_{dx} + b_5 \dot{\alpha}_{dx} ) \dot{\psi} \\
& - \frac{\partial  a_{\phi_x}}{\partial \phi_x} \dot{\phi}_x^2 - \frac{\partial a_{\theta}}{\partial \phi_x} \dot{\theta}^2 \\
& -  \left(b_1 \frac{\partial x_{dx}}{\partial\phi_x} + \frac{\partial b_5}{\partial\phi_x} \alpha_{dx} + b_5 \frac{\partial \alpha_{dx}}{\partial\phi_x} \right) \dot{\phi}_x \dot{\psi} \\
C_3 &= 2 \dot{a}_{\theta} \dot{\theta} - \frac{\partial a_{\phi_x}}{\partial \theta} \dot{\phi}_x^2 - \frac{\partial a_{\theta}}{\partial \theta}  \dot{\theta}^2 \\
& - \left(b_1 \frac{\partial x_{dx}}{\partial\theta} + \frac{\partial b_5}{\partial\theta} \alpha_{dx} + b_5 \frac{\partial \alpha_{dx}}{\partial\theta} \right) \dot{\phi}_x \dot{\psi} \\
C_4 &= (\dot{b_1} x_{dx} + b_1 \dot{x}_{dx} + \dot{b_5}\alpha_{dx} + b_5 \dot{\alpha}_{dx} ) \dot{\phi}_x \\
& - \left(\frac{\partial b_1}{\partial \psi} x_{dx} + \frac{\partial b_5}{\partial \psi} \alpha_{dx} \right) \dot{\phi}_x \dot{\psi} \\
G_1 &= \frac{\partial U}{\partial\phi_x} \\ 
&= (2m+M) g \left( -R \sin(\alpha) + \frac{W}{2} \cos(\alpha)\right) \frac{\partial \alpha}{\partial\phi_x} \\
G_3 &= \frac{\partial U}{\partial\theta} \\ 
&= (2m+M) g \left( -R \sin(\alpha) + \frac{W}{2} \cos(\alpha)\right) \frac{\partial \alpha}{\partial\theta} \\
G_4 &= \frac{\partial U}{\partial\psi} = -Mgl\sin(\psi) 
\end{cases}
$$

where

$$
\begin{cases}
a_1 &= m + \frac{1}{2}M \\
a_2 &= \left(m + \frac{1}{2}M \right)r^2n_r^2 \\
a_3 &= \left(m + \frac{1}{2}M \right)r^2 \\
a_4 &= \frac{mW^2}{4} + \frac{1}{2}Ml^2\sin^2(\psi) \\
a_5 &= \frac{1}{2} m W^2 \cos^2(\alpha) + \frac{1}{8} M W^2 \cos^2(\alpha) \\
a_6 &= \frac{1}{2}Ml^2 \\
a_{\phi_x} &= a_1 x_{dx}^2 + a_2 + a_4 \theta_{dx}^2 + a_5 \alpha_{dx}^2 \\
a_{\theta} &= a_1 x_{d\theta}^2 + a_4 \theta_{d\theta}^2 + a_5 \alpha_{d\theta}^2
\end{cases}
$$

$$
\begin{cases}
b_1 &=  Ml \cos(\psi)  \\
b_2 &= \left(2m + M \right)r^2n_r \\
b_3 &= Mrln_r \sin(\psi) \\
b_4 &= Mrl \sin(\psi) \\
b_5 &= -\frac{1}{2} MWl \cos(\alpha) \sin(\psi)
\end{cases}
$$

