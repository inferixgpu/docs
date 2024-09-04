# Noise insertion

Given a scene $$G$$, the random vector $$W = \left(w_i\right)_{1 \leq i \leq n}$$ is embedded into $$G$$ by first wrapping each atomic $$w_i$$ by a graphical object: let denote it $$\omega_i$$, then we obtain a vector of objects $$\Omega = \left(\omega_i\right)_{1 \leq i \leq n}$$. Next we insert $$\Omega$$ into $$G$$ so that every $$\omega_i$$ contributes to the rendered image, namely they distort this image. The distortion is kept to be lower than the human perception of light [[10]](/inferix-whitepaper/references.md#10), [[11]](/inferix-whitepaper/references.md#11).
