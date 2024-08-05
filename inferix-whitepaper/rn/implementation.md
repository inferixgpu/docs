# Implementation
In the previous section, we have described the high-level view of the Active Noise Generation and Verification algorithms. In this section, we present in detail the current implementation of watermark insertion and verification.

## Structure of watermark
Following [Equation 2](./algorithms.md), a noise is a random vector $$W = \left(w_i\right)_{1 \leq i \leq n}$$ where each $$w_i$$ is independently chosen from a normal distribution $$\mathcal{N}\left(\mu, \sigma^2\right)$$. The atomic watermark $$w_i$$ is implemented a rectangular image of periodic patterns: we fix some $$M,N$$ for the width and the height of the image; and let $$X_i, Y_i$$ be respectively the periods following the horizontal and vertical axis (these values are chosen from a normal distribution), then: