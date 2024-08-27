# Structure of noise

As introduced in the previous section, a noise $$W$$ is a random vector $$\left(w_i\right)_{1 \leq i \leq n}$$ where each element is independently chosen from a normal distribution. This atomic watermark is constructed as a rectangular image of periodic patterns as follows:

* let fix some values $M,N$ for the width and the height of the rectangle, and
*   let $\mathcal{X}\_i, \mathcal{Y}\_i$ be independent and identically distributed normal random variables:

    $$
    \mathcal{X}_i \sim \mathcal{Y}_i \sim \mathcal{N}\left(\mu, \sigma^2\right)
    $$

    for some $$\mu$$ and $$\sigma$$, then take $$X_i, Y_i$$ be respectively some samples of $$\mathcal{X}_i, \mathcal{Y}_i$$.

The complex atomic signal $$w_i$$ is defined by:

$$
w_i(x,y) = A e^{2i\pi\left(\frac{x}{X_i} + \frac{y}{Y_i}\right)} \ \left(0 \leq x < M, 0 \leq y < N \right)
$$

for some amplitude $$A$$. We observe that $$w_i\left(x,y\right) = w_i\left(x + X_i, y\right) = w_i\left(x, y + Y_i\right) \, \forall x,y$$ then $$X_i, Y_i$$ are actually the horizontal and the vertical periods.

_Remark_
