\newpage

# Fourier Analysis

## The Heat Equation

## Fourier Transform

$$
\hat{f}(x) = \int_{-\infty}^\infty f(t)e^{-i2\pi xt}dt,\quad \forall x\in\mathbb{R}
$$

$$
f(t) = \int \hat{f}(\omega)e^{i\omega t}d\omega
$$

## Laplace Transform

$$
\mathcal{L}\{f\}(s) = \int_0^\infty f(t)e^{-st}dt,\quad s\in\mathbb{C}
$$


$$
\mathcal{L}\{f'\} = \mathcal{L}\{sF - f'(0)\}
$$

$$
\mathcal{L}\{f^{(n)}(t)\} = s^n\mathcal{L}\{f(t)\} - s^{n-1}f(0)... - f^{(n-1)}(0)
$$

## Deriving Laplace Transforms


### Simple Functions

$$
\begin{aligned}
    \mathcal{L}\{1\} &= \int_0^\infty e^{-st}dt\\
    &= {1\over s}\left(e^0 - \lim_{\alpha\rightarrow\infty}e^{-s\alpha}\right)\\
    &= {1\over s}
\end{aligned}
$$

### Trigonometric

$$
\begin{aligned}
    \mathcal{L}\{\sin\theta t\} = 
\end{aligned}
$$


