# Noise generation

In practice, a scene may contain multiple frames, each task of this scene contains some range of frames to be rendered, consequently each worker may render only a subset of these frames. For the simplification purpose, we assume in this section that a scene has only one frame, so the output image is determined uniquely by the scene.

<figure><img src="../../.gitbook/assets/noise-generation.svg" alt=""><figcaption><p>Noise generation</p></figcaption></figure>

Let $$R$$ denote the rendering process, for each input scene $$G$$, the result of the rendering is an image:

$$
I = \mathcal{R} \left(G\right)
$$

It is important to note that $$I$$ is actually never computed, neither by the _manager_ in the noise embedding (see also the discussion about sampling frames in\cref{subsec:noise\_spreading}) nor by _workers_ in the frame rendering. The equation above represents only equality.

Similar with invisible watermark schemes in the literature\cite{Wu1998,Yeung1997,Craver1997}, a noise $$W$$ consists in a random vector of atomic watermarks:

$$
W \triangleq \left( w_1, \dots, w_n \right)
$$

where $$w\_i , \left(1 \leq i \leq n\right)$$ is independently chosen from some normal probability distribution $$\mathcal{N}\left(\mu, \sigma^2\right)$$. Furthermore, $$w\_i$$ has a special structure depending on where it is introduced in the scene $$G$$. The number $$n$$ of atomic watermark signals is chosen around an experimental trade-off between human perception threshold about the image distortion and the false positive ratio of the noise verification.
