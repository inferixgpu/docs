# Implementation

In the previous section, we have described the high-level view of the Active Noise Generation and Verification algorithms. In this section, we present in detail the current implementation of watermark insertion and verification.

## Structure of watermark

Following [Equation 2](algorithms.md), a noise is a random vector $$W = \left(w_i\right)_{1 \leq i \leq n}$$ where each $$w_i$$ is independently chosen from a normal distribution $$\mathcal{N}\left(\mu, \sigma^2\right)$$. The atomic watermark $$w_i$$ is implemented a rectangular image of periodic patterns as follows:

* let fix some values $M,N$ for the width and the height of the rectangle, and
* let $$X_i, Y_i$$ be respectively the periods following the horizontal and vertical axis, they are random variables $$X_i \sim \mathcal{N}\left(\mu, \sigma^2\right), Y_i \sim \mathcal{N}\left(\mu, \sigma^2\right)$$,

then the image $$w_i$$ is defined by:

$$
\begin{equation} w_i(x,y) = e^{2i\pi\left(\frac{x}{X_i} + \frac{y}{Y_i}\right)} \ \left(1 \leq x \leq M, 1 \leq y \leq N \right) \end{equation}
$$

The [Figure 4](implementation.md#structure-of-watermark) presents a noise as a vector of $$5$$ atomic watermarks and the Fourier transformations showing the corresponding frequency characteristics. For illustration purpose, we take $$X_i = Y_i$$ where $$X_i \sim \mathcal{N}\left(25,5\right) \ \left(1 \leq i \leq 5\right)$$, and $$M = N = 512$$.

<figure><img src="../../.gitbook/assets/random_vector_atomic_watermark_fft.png" alt=""><figcaption><p>Figure 4: A random vector of <span class="math">5</span> atomic watermarks</p></figcaption></figure>

The frequency characteristics of atomic watermarks play a crucial role in the noise verification since they help to distinguish embedded noises from the original signals of the image. The frequencies are determined by the periods $$X_i, Y_i$$ which in turn rely on the expectation $$\mu$$, we will discuss the computation of this value in the [Section: Noise verification](implementation.md#noise-verification).

The size $$n$$ of the random vector is one of the principal factors decides the robustness of watermark: the higher value of $$n$$ the lower the false positive of noise verification. Empirically, $$n$$ is about $$8$$ to $$10$$.

## Noise embedding

## Noise verification
