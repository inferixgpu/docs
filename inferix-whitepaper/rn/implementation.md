# Implementation

In the previous section, we have described the high-level view of the Active Noise Generation and Verification algorithms. In this section, we present in detail the current implementation of watermark insertion and verification.

## Structure of watermark

Following [Equation 2](algorithms.md), a noise is a random vector $$W = \left(w_i\right)_{1 \leq i \leq n}$$ where each $$w_i$$ is independently chosen from a normal distribution $$\mathcal{N}\left(\mu, \sigma^2\right)$$. The atomic watermark $$w_i$$ is implemented a rectangular image of periodic patterns as follows:

 * let fix some values $M,N$ for the width and the height of the rectangle, and
 * let $$\mathcal{X}_i, \mathcal{Y}_i$$ be normal random variables:
   $$
   \begin{equation}
        \mathcal{X}_i \sim \mathcal{N}\left(\mu, \sigma^2\right) \quad \mathcal{Y}_i \sim \mathcal{N}\left(\mu, \sigma^2\right)
    \end{equation}
   $$
   then take $$X_i, Y_i$$ be respectively some samples of $$\mathcal{X}_i, \mathcal{Y}_i$$.

The image $$w_i$$ is defined by:
$$
\begin{equation} w_i(x,y) = e^{2i\pi\left(\frac{x}{X_i} + \frac{y}{Y_i}\right)} \ \left(1 \leq x \leq M, 1 \leq y \leq N \right) \end{equation}
$$
We note that $$w_i\left(x,y\right) = w_i\left(x + X_i, y\right) = w_i\left(x, y + Y_i\right) \, \forall x,y$$ then $$X_i, Y_i$$ are respectively the periods following the horizontal and the vertical axis.

The [Figure 4](implementation.md#structure-of-watermark) presents a noise as a vector of $$5$$ atomic watermarks and the Fourier transformations showing the corresponding frequency characteristics. For illustration purpose, we take $$X_i = Y_i$$ where $$X_i \sim \mathcal{N}\left(25,5\right) \ \left(1 \leq i \leq 5\right)$$, and $$M = N = 512$$.

<figure><img src="../../.gitbook/assets/random_vector_atomic_watermark_fft.png" alt=""><figcaption><p>Figure 4: A random vector of <span class="math">5</span> atomic watermarks</p></figcaption></figure>

The frequency characteristics of atomic watermarks play a crucial role in the noise verification since they help to distinguish embedded noises from the original signals of the image. From [Equation 9](implementation.md), the frequencies are completely determined by the periods $$X_i, Y_i$$ since the discrete Fourier transform:
$$
\begin{equation}
    F(u,v) = \frac{1}{M \times N} \sum\limits_{x = 0}^{M - 1} \sum\limits_{y = 0}^{N - 1} w_{i}(x,y) e^{2i\pi \left(\frac{x u}{M} + \frac{y v}{N}\right)}
\end{equation}
$$
These periods in turn rely on the expectation $$\mu$$ by [Equation 8](implementation.md), we will discuss the computation of this value in~\cref{subsec:noise_verification_implementation}.

The frequencies are determined by the periods $$X_i, Y_i$$ which in turn rely on the expectation $$\mu$$, we will discuss the computation of this value in the [Section: Noise verification](implementation.md#noise-verification).

The size $$n$$ of the random vector is one of the principal factors which decides the robustness of watermark: the higher value of $$n$$ the lower the false positive of noise verification. This value influences the quality of the rendered image: the lower value of $n$ the higher fidelity of the rendered images. Empirically, this value is chosen to be about $$8$$ to $$10$$.

## Noise embedding

## Noise verification
