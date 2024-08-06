# Implementation

In the previous section, we have presented the high-level description of the Active Noise Generation and Verification algorithms. In this section, we discuss in detail the current implementation of noise generation and verification.

## Structure of noise

Following [Equation 2](algorithms.md), a noise is a random vector $$W = \left(w_i\right)_{1 \leq i \leq n}$$ where each $$w_i$$ is independently chosen from a normal distribution $$\mathcal{N}\left(\mu, \sigma^2\right)$$. The atomic watermark $$w_i$$ is implemented a rectangular image of periodic patterns as follows:

 * let fix some values $M,N$ for the width and the height of the rectangle, and
 * let $$\mathcal{X}_i, \mathcal{Y}_i$$ be independent normal random variables:
   $$
   \begin{equation}
        \mathcal{X}_i \sim \mathcal{N}\left(\mu, \sigma^2\right) \quad \mathcal{Y}_i \sim \mathcal{N}\left(\mu, \sigma^2\right)
    \end{equation}
   $$
   then take $$X_i, Y_i$$ be respectively some samples of $$\mathcal{X}_i, \mathcal{Y}_i$$.

The complex atomic signal $$w_i$$ is defined by:
$$
\begin{equation}
w_i(x,y) = A e^{2i\pi\left(\frac{x}{X_i} + \frac{y}{Y_i}\right)} \ \left(0 \leq x < M, 0 \leq y < N \right)
\end{equation}
$$
for some amplitude $A$. We observe that $$w_i\left(x,y\right) = w_i\left(x + X_i, y\right) = w_i\left(x, y + Y_i\right) \, \forall x,y$$ then $$X_i, Y_i$$ are actually the horizontal and the vertical periods.

The [Figure 4](implementation.md#structure-of-watermark) shows a noise as a vector of $$5$$ atomic watermarks and the Fourier transformations showing the corresponding frequency characteristics. For illustration purpose, we take $$X_i = Y_i$$ where $$X_i \sim \mathcal{N}\left(25,5\right) \ \left(1 \leq i \leq 5\right)$$, and $$M = N = 512$$.

<figure><img src="../../.gitbook/assets/random_vector_atomic_watermark_fft.png" alt=""><figcaption><p>Figure 4: A random vector of <span class="math">5</span> atomic watermarks</p></figcaption></figure>

The frequency characteristics of atomic watermark signals play a crucial role in the noise verification since they help to distinguish embedded noises from the original signals of the image. The characteristics are completely determined by the periods $X_i, Y_i$ given fixed $M,N$ since the discrete Fourier transform in [Proposition 1](implementation.md#Proposition 1 (Fourier transform of complex atomic signal)). In turn, these periods statistically rely on the expectation $$\mu$$ by [Equation 1](implementation.md), we will discuss the computation of this value in the [Section: Noise verification](implementation.md#noise-verification).

### Proposition 1 (Fourier transform of complex atomic signal)
$$
\begin{equation*}
    F\left(u,v\right) = \frac{A}{M \times N} \frac{\left(1 - e^{2i\pi \frac{M}{X_i}}\right) \left(1 - e^{2i\pi \frac{N}{Y_i}}\right)}{\left(1 - e^{2i\pi\left(\frac{1}{X_i} + \frac{u}{M}\right)}\right) \left(1 - e^{2i\pi\left(\frac{1}{Y_i} + \frac{v}{N}\right)}\right)}   
\end{equation*}
$$

The size $$n$$ of the random vector is one of the principal factors which decides the robustness of noise: the higher value of $$n$$ the lower the false positive of noise verification. This value influences the quality of the rendered image: the lower value of $$n$$ the higher fidelity of the rendered images. Consequently, the value of $$n$$ is a trade-off between the robustness of the embedded noise and the fidelity of the rendered image, this value is empirically chosen to be about $$5$$ to $$8$$.

## Noise generation
Given a graphics scene $$S$$, the random vector $$W = \left(w_i\right)_{1 \leq i \leq n}$$ is embedded into $$S$$ by first wrapping each atomic $$w_i$$ by a graphical object: let denote it $$\omega_i$$, then we obtain a vector of objects $$\Omega = \left(\omega_i\right)_{1 \leq i \leq n}$$. Next by inserting $$\Omega$$ into $$S$$ so that every $$\omega_i$$ contribute to the rendered image, namely they distort this image, but the distortion must be kept so that it is lower than the human perception of light.

## Noise verification
