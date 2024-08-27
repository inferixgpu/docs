# Structure of noise

As introduced in the previous section, a noise $$W$$ is a random vector $$\left(w_i\right)_{1 \leq i \leq n}$$ where each element is independently chosen from a normal distribution. This atomic watermark is constructed as a rectangular image of periodic patterns as follows:

* let fix some values $$M,N$$ for the width and the height of the rectangle, and
*   let $$\mathcal{X}\_i, \mathcal{Y}\_i$$ be independent and identically distributed normal random variables:

    $$
    \mathcal{X}_i \sim \mathcal{Y}_i \sim \mathcal{N}\left(\mu, \sigma^2\right)
    $$

    for some $$\mu$$ and $$\sigma$$, then take $$X_i, Y_i$$ be respectively some samples of $$\mathcal{X}_i, \mathcal{Y}_i$$.

The complex atomic signal $$w_i$$ is defined by:

$$
w_i(x,y) = A e^{2i\pi\left(\frac{x}{X_i} + \frac{y}{Y_i}\right)} \ \left(0 \leq x < M, 0 \leq y < N \right)
$$

for some amplitude $$A$$. We observe that $$w_i\left(x,y\right) = w_i\left(x + X_i, y\right) = w_i\left(x, y + Y_i\right) \, \forall x,y$$ then $$X_i, Y_i$$ are actually the horizontal and the vertical periods.

_Remark:_ $$\mathcal{X}_i$$ and $$\mathcal{Y}_i$$ are elements of a set $$\left\{ \mathcal{X}_i, \mathcal{Y}_i \mid 1 \leq i \leq n\right\}$$ of independent and identically distributed normal random variables $$\mathcal{N}\left(\mu, \sigma^2\right)$$. The parameters $$\mu$$ and $$\sigma$$ are chosen by analyzing the input scene that is discussed in\~\cref{subsec:noise\_spreading}.

_Proposition 1:_ (Fourier transform of complex atomic signals)

$$
F_i\left(u,v\right) = \frac{A}{M \times N} \frac{\left(1 - e^{2i\pi \frac{M}{X_i}}\right) \left(1 - e^{2i\pi \frac{N}{Y_i}}\right)}{\left(1 - e^{2i\pi\left(\frac{1}{X_i} + \frac{u}{M}\right)}\right) \left(1 - e^{2i\pi\left(\frac{1}{Y_i} + \frac{v}{N}\right)}\right)}
$$

_Proof:_ Direct calculation (for details, see appendix\~\labelcref{proof:fourier\_transform}).

The structure of noise given in\~\cref{equ:atomic\_watermark\_signals} has two folds: we empirically find that this form of signal makes the wrapping graphical objects (discussed in\cref{subsec:noise\_generation}) persistent in the rendering of graphics scenes. Furthermore, the distortion raised by any atomic watermark is easily controlled thanks to the simple form of the signal amplitude given in\cref{prop:fourier\_transform}.

The spectrums of atomic signals play a crucial role in the noise verification since they help to distinguish embedded noises from the original image signals. They are also completely determined by the periods $$X_i, Y_i$$ given fixed $$M,N$$ since the discrete Fourier transform in\cref{prop:fourier\_transform}. In turn, these periods statistically rely on the expectation $\mu$ by\cref{equ:normal\_random\_variables}, we will discuss how to choose this value in\~\cref{subsec:noise\_spreading}.

The length $n$ of the noise vector is one of the principal factors which decides the robustness of noise: the higher the value $$n$$, the lower the false positive of noise verification. But this size influences the quality of the rendered image: the lower value $n$, the higher fidelity of the rendered images. Consequently, the value $n$ is a trade-off between the robustness of the embedded noise and the fidelity of the rendered image, it is empirically chosen to be about $$8$$ to $$15$$.

<figure><img src="../../.gitbook/assets/random_vector_atomic_watermark_fft (1).png" alt=""><figcaption><p>A random vector of 5 atomic watermarks</p></figcaption></figure>

The figure above shows a noise as a vector of $$5$$ atomic watermarks and the Fourier transforms showing the corresponding frequency characteristics. The vital frequencies of energy are clearly shown in the spectrums. For illustration purpose, we take $$X_i = Y_i \sim \mathcal{N}\left(25,5\right) \ \left(1 \leq i \leq 5\right)$$, and $$M = N = 512$$.
