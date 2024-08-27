# Noise verification

Different from proof of ownership schemes\cite{Wu1998,Yeung1997}, the verification of watermark requires a key. Given an image $$J$$ and a verification key $$K_{\mathtt{verif}}$$, we first try to recover a watermark $$\hat{W}$$ from $$J$$ using a decoding function $$\mathcal{D}$$:

$$
\hat{W} = \mathcal{D} \thinspace (J, K_{\mathtt{verif}})
$$

Next $$\hat{W}$$ is compared against $$W$$, if the deviation is above some threshold $$T$$:

$$
\lVert \hat{W} - W \rVert \geq T
$$

then $$J$$ will be accepted otherwise rejected.
