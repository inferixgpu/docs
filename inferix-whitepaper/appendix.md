# Appendix

## Proof of proposition 1
Substitute the atomic signal:
$$
\begin{equation*}
    w_i\left(x,y\right) = A e^{2i\pi\left(\frac{x}{X_i} + \frac{y}{Y_i}\right)} \ \left(0 \leq x < M, 0 \leq y < N  \right)
\end{equation*}
$$
into the discrete Fourier transform:
$$
\begin{equation*}
    F(u,v) = \frac{1}{M \times N} \sum\limits_{x = 0}^{M - 1} \sum\limits_{y = 0}^{N - 1} w_{i}(x,y) e^{2i\pi \left(\frac{x u}{M} + \frac{y v}{N}\right)}
\end{equation*}
$$
We have
$$
\begin{equation*}
    F\left(u,v\right) = \frac{A}{M \times N} \sum\limits_{x = 0}^{M - 1} \sum\limits_{y = 0}^{N - 1} e^{2i\pi\left(\frac{x}{X_i} + \frac{y}{Y_i}\right)} e^{2i\pi \left(\frac{x u}{M} + \frac{y v}{N}\right)}
\end{equation*}
$$
Moreover
$$
\begin{align*}
    &\sum\limits_{x = 0}^{M - 1} \sum\limits_{y = 0}^{N - 1} e^{2i\pi\left(\frac{x}{X_i} + \frac{y}{Y_i}\right)} e^{2i\pi \left(\frac{x u}{M} + \frac{y v}{N}\right)} \\ =&\sum\limits_{x = 0}^{M - 1} \sum\limits_{y = 0}^{N - 1} e^{2i\pi x \left(\frac{1}{X_i} + \frac{u}{M}\right)} e^{2i\pi y \left(\frac{1}{Y_i} + \frac{v}{N}\right)} \\ =&\left(\sum\limits_{x = 0}^{M - 1} e^{2i\pi x \left(\frac{1}{X_i} + \frac{u}{M}\right)}\right) \left(\sum\limits_{x = 0}^{N - 1} e^{2i\pi x \left(\frac{1}{Y_i} + \frac{v}{N}\right)}\right)
\end{align*}
$$
Using geometric sum formulae:
$$
\begin{align*}
    =& \frac{1 - e^{2i\pi M \left(\frac{1}{X_i} + \frac{u}{M}\right)}}{1 - e^{2i\pi \left(\frac{1}{X_i} + \frac{u}{M}\right)}} \frac{1 - e^{2i\pi N \left(\frac{1}{Y_i} + \frac{v}{N}\right)}}{1 - e^{2i\pi \left(\frac{1}{Y_i} + \frac{v}{N}\right)}} \\
    =& \frac{1 - e^{2i\pi \frac{M}{X_i} + 2i\pi u}}{1 - e^{2i\pi \left(\frac{1}{X_i} + \frac{u}{M}\right)}} \frac{1 - e^{2i\pi\frac{N}{Y_i} + 2i\pi v}}{1 - e^{2i\pi \left(\frac{1}{Y_i} + \frac{v}{N}\right)}} \\
    =& \frac{1 - e^{2i\pi \frac{M}{X_i}}}{1 - e^{2i\pi \left(\frac{1}{X_i} + \frac{u}{M}\right)}} \frac{1 - e^{2i\pi\frac{N}{Y_i}}}{1 - e^{2i\pi \left(\frac{1}{Y_i} + \frac{v}{N}\right)}}
\end{align*}
$$
Hence:
$$
\begin{equation*}
    F\left(u,v\right) = \frac{A}{M \times N} \frac{1 - e^{2i\pi \frac{M}{X_i}}}{1 - e^{2i\pi \left(\frac{1}{X_i} + \frac{u}{M}\right)}} \frac{1 - e^{2i\pi\frac{N}{Y_i}}}{1 - e^{2i\pi \left(\frac{1}{Y_i} + \frac{v}{N}\right)}}
\end{equation*}
$$