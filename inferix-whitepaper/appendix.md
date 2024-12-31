# Appendix A: Proofs

### Fourier transform of complex atomic signals

Substitute the atomic signal:

$$
\begin{equation*} w_i\left(x,y\right) = A e^{2i\pi\left(\frac{x}{X_i} + \frac{y}{Y_i}\right)} \ \left(0 \leq x < M, 0 \leq y < N \right) \end{equation*}
$$

into the discrete Fourier transform:

$$
\begin{equation*} F(u,v) = \frac{1}{M \times N} \sum\limits_{x = 0}^{M - 1} \sum\limits_{y = 0}^{N - 1} w_{i}(x,y) e^{2i\pi \left(\frac{x u}{M} + \frac{y v}{N}\right)} \end{equation*}
$$

We have

$$
\begin{equation*} F\left(u,v\right) = \frac{A}{M \times N} \sum\limits_{x = 0}^{M - 1} \sum\limits_{y = 0}^{N - 1} e^{2i\pi\left(\frac{x}{X_i} + \frac{y}{Y_i}\right)} e^{2i\pi \left(\frac{x u}{M} + \frac{y v}{N}\right)} \end{equation*}
$$

Moreover

$$
\begin{align*} &\sum\limits_{x = 0}^{M - 1} \sum\limits_{y = 0}^{N - 1} e^{2i\pi\left(\frac{x}{X_i} + \frac{y}{Y_i}\right)} e^{2i\pi \left(\frac{x u}{M} + \frac{y v}{N}\right)} \\ =&\sum\limits_{x = 0}^{M - 1} \sum\limits_{y = 0}^{N - 1} e^{2i\pi x \left(\frac{1}{X_i} + \frac{u}{M}\right)} e^{2i\pi y \left(\frac{1}{Y_i} + \frac{v}{N}\right)} \\ =&\left(\sum\limits_{x = 0}^{M - 1} e^{2i\pi x \left(\frac{1}{X_i} + \frac{u}{M}\right)}\right) \left(\sum\limits_{x = 0}^{N - 1} e^{2i\pi x \left(\frac{1}{Y_i} + \frac{v}{N}\right)}\right) \end{align*}
$$

Using geometric sum formulae:

$$
\begin{align*} =& \frac{1 - e^{2i\pi M \left(\frac{1}{X_i} + \frac{u}{M}\right)}}{1 - e^{2i\pi \left(\frac{1}{X_i} + \frac{u}{M}\right)}} \frac{1 - e^{2i\pi N \left(\frac{1}{Y_i} + \frac{v}{N}\right)}}{1 - e^{2i\pi \left(\frac{1}{Y_i} + \frac{v}{N}\right)}} \\ =& \frac{1 - e^{2i\pi \frac{M}{X_i} + 2i\pi u}}{1 - e^{2i\pi \left(\frac{1}{X_i} + \frac{u}{M}\right)}} \frac{1 - e^{2i\pi\frac{N}{Y_i} + 2i\pi v}}{1 - e^{2i\pi \left(\frac{1}{Y_i} + \frac{v}{N}\right)}} \\ =& \frac{1 - e^{2i\pi \frac{M}{X_i}}}{1 - e^{2i\pi \left(\frac{1}{X_i} + \frac{u}{M}\right)}} \frac{1 - e^{2i\pi\frac{N}{Y_i}}}{1 - e^{2i\pi \left(\frac{1}{Y_i} + \frac{v}{N}\right)}} \end{align*}
$$

Hence:

$$
\begin{equation*} F\left(u,v\right) = \frac{A}{M \times N} \frac{1 - e^{2i\pi \frac{M}{X_i}}}{1 - e^{2i\pi \left(\frac{1}{X_i} + \frac{u}{M}\right)}} \frac{1 - e^{2i\pi\frac{N}{Y_i}}}{1 - e^{2i\pi \left(\frac{1}{Y_i} + \frac{v}{N}\right)}} \end{equation*}
$$

### Convergence of energies

The random variables $$\mathcal{X}_i, \mathcal{Y}_i \left(i \in \mathbb{N}\right)$$ are independent then two variables:

$$
\overline{\mathcal{X}}_n = \frac{\mathcal{X}_1 + \dots \mathcal{X}_n}{n} \quad \text{and} \quad \overline{\mathcal{Y}}_n = \frac{\mathcal{Y}_1 + \dots \mathcal{Y}_n}{n}
$$

are independent for all $$n \in \mathbb{N}$$. Since $$\mathcal{X}_i \left(i \in \mathbb{N}\right)$$ are independent and identically distributed and $$\mathcal{X}_i \sim \mathcal{N}\left(\mu, \sigma^2\right)$$

$$
\overline{\mathcal{X}}_n \xrightarrow[n \to \infty]{a.s} \mu
$$

by strong law of large numbers; similarly $$\overline{\mathcal{Y}}_n \xrightarrow[n \to \infty]{a.s} \mu$$. Hence

$$
{[\overline{\mathcal{X}}_n \quad \overline{\mathcal{Y}}_n]^t} \xrightarrow[n \to \infty]{a.s} {[\overline{\mathcal{X}} \quad \overline{\mathcal{Y}}]^t}
$$

for some independent and identically distributed variables $$\overline{\mathcal{X}} \sim \overline{\mathcal{Y}} \sim \mu$$. Let us fix some $$0 \leq u < M$$ and $$0 \leq v < N$$, then it is obvious that the function

$$
F_{\left(u,v\right)} \triangleq \left(x,y\right) \mapsto \frac{A}{M \times N} \frac{\left(1 - e^{2i\pi \frac{M}{x}}\right) \left(1 - e^{2i\pi \frac{N}{y}}\right)}{\left(1 - e^{2i\pi\left(\frac{1}{x} + \frac{u}{M}\right)}\right) \left(1 - e^{2i\pi\left(\frac{1}{y} + \frac{v}{N}\right)}\right)}
$$

is continuous. We define the variable:

$$
\mathcal{F}_{\left(u,v\right)} \colon \Omega \to \mathbb{R}^2 \\ \omega \mapsto F_{\left(u,v\right)} \left(\mathcal{X} \left(\omega\right),\mathcal{Y}\left(\omega\right)\right)
$$

for some random variables $$\mathcal{X}$$ and $$\mathcal{Y}$$, then $$\mathcal{F}_{\left(u,v\right)}\left(\omega\right)$$ is nothing but the Fourier transform of the atomic signal whose the horizontal and the vertical period are $$\mathcal{X}\left(\omega\right)$$ and $$\mathcal{Y}\left(\omega\right)$$ respectively. Let us consider the sequence $$\left(\mathcal{F}_{\left(u,v\right)}^n\right)_{n \in \mathbb{N}}$$ where:

$$
\mathcal{F}_{\left(u,v\right)}^n \triangleq \omega \mapsto F_{\left(u,v\right)} \left(\overline{\mathcal{X}}_n \left(\omega\right),\overline{\mathcal{Y}}_n\left(\omega\right)\right)
$$

By the continuous mapping theorem:

$$
\mathcal{F}_{\left(u,v\right)}^n \xrightarrow[n \to \infty]{a.s} \omega \mapsto F_{\left(u,v\right)} \left(\overline{\mathcal{X}} \left(\omega\right),\overline{\mathcal{Y}}\left(\omega\right)\right)
$$

Since we have proved that $$\overline{\mathcal{X}} \sim \overline{\mathcal{Y}} \sim \mu$$ then the limit of the sequence is the constant variable $$F_{\left(u,v\right)} \left(\mu, \mu\right)$$. Also, since $$F_{\left(u,v\right)}$$ is continuous:

$$
\lvert F_{\left(u,v\right)}\left(\overline{\mathcal{X}}_n, \overline{\mathcal{Y}}_n\right) - \overline{F}_{\left(u,v\right)}\left(\mathcal{X}_n, \mathcal{Y}_n\right) \rvert \xrightarrow[n \to \infty]{} 0
$$

Hence $$\overline{F}_{\left(u,v\right)}\left(\mathcal{X}_n, \mathcal{Y}_n\right) \xrightarrow[n \to \infty]{a.s} F_{\left(u,v\right)} \left(\mu, \mu\right)$$.

_**Remark.**_ The proof does not require that $$X_i$$ and $$Y_i$$ have the same distribution. Indeed, if $$X_i \sim \mathcal{N}\left(\mu_{x},\cdot\right)$$ and $$Y_i \sim \mathcal{N}\left(\mu_{y},\cdot\right)$$ then $$\overline{F}_{\left(u,v\right)}\left(\mathcal{X}_n, \mathcal{Y}_n\right) \xrightarrow[n \to \infty]{a.s} F_{\left(u,v\right)} \left(\mu_x, \mu_y\right)$$.
