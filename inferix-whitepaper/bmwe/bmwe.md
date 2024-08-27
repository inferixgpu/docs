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
W \triangleq \left(w_1, \dots, w_n \right)
$$

where $$w_i , \left(1 \leq i \leq n\right)$$ is independently chosen from some normal probability distribution $$\mathcal{N}\left(\mu, \sigma^2\right)$$. Furthermore, $$w_i$$ has a special structure depending on where it is introduced in the scene $$G$$. The number $$n$$ of atomic watermark signals is chosen around an experimental trade-off between human perception threshold about the image distortion and the false positive ratio of the noise verification.

Using a uniformly generated task identification number $$J_{\mathtt{id}}$$, we calculate a verification key which is a vector of the same size as the noise vector $$W$$:

$$
K_{\mathtt{verif}} \left(S, W, J_{\mathtt{id}}\right) \triangleq \left( k_1,\dots,k_n \right)
$$

that will be used later for the noise verification.

We have discussed that embedding watermarks into $$I$$ cannot help the authentication, then the noise $$W$$ is not embedded into the image $$I$$ but into the scene $$G$$ (c.f.\cref{fig:noise_generation}). Let $$\mathcal{E}$$ denote the embedding function, we now create a watermarked scene:

$$
\hat{G} = \mathcal{E} \left(G, W\right)
$$

Finally, $$\hat{G}$$ is sent to _workers_ for rendering, that results in a rendered image:

$$
\hat{I} = \mathcal{R} \thinspace (\hat{G})
$$

If got accepted, namely $$\hat{I}$$ passes the noise verification which will be presented hereafter, this is the image sent back to the user (recall that $$I$$ in~\cref{equ:rendering_function} is not computed). The encoding function $$\mathcal{E}$$ and the noise $W$ are designed so that the distortion of $$\hat{I}$$ against $$I$$ is imperceptible\cite{Jayant1993,Wu2013}, then $$\hat{I}$$ can be authentically used as a result of the graphics rendering.
