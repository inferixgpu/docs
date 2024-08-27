# Adaptive noise spreading

As discussed above, each atomic $$w_i \in W$$ has its distortion contribution at the spatial region $$k_i$$ on the rendered image. Since the rendering process contains multiple options to improve the quality of the output (noise reduction, anti-aliasing, etc.), it is severe if the region $$k_i$$(s) fall into perceptually insignificant regions\cite{Cox1997} of the image because the deliberate distortions raised by $$w_i$$(s) would be eliminated by the rendering enhancement. Hence, distortions are preferred to be placed in human perceptually significant regions. However, to keep the compromise between the fidelity of the rendered frames and the robustness of noise verification, the strength of the distortion of each $$w_i$$ must be tuned so that its deviation from locally enclosed regions is within a predetermined bound.

We handle this problem using the adaptive noise spreading\cite{Swanson1996,Podilchuk1998,Voloshynovskiy2000}. Research on the human visual perception agrees that the important information of images is located at high energy and low frequency spectral regions\cite{Jayant1993}. Then before embedding the object vector $$\Omega$$, we render the scene $$G$$ at some low settings to get a sampling instance of the image. Next, we proceed both the spatial and spectral analysis on this instance to get perceptually significant spatial regions, called preferred regions. The atomic noises $$w_i$$(s) will be placed in these regions. Simultaneously, we tune the expectation value $$\mu$$ used in generating atomic noises so that the energy (statistically given in\cref{prop:convergence_of_energy}) of high frequencies of the noises are sufficiently higher than the threshold used in the noise verification (c.f.\cref{subsec:noise_verification_implementation}).

_Proposition 2:_ (Convergence of energies)

Let $$\left\{ \mathcal{X}_i, \mathcal{Y}_i \mid i \in \mathbb{N} \right\}$$ be a set of independent and identically distributed normal random variables $$\mathcal{X}_i \sim \mathcal{Y}_i \sim \mathcal{N}\left(\mu, \sigma^2\right)$$. Let $$[X_i \quad Y_i]^t$$  be a sample of the random vector $$[\mathcal{X}_i \quad \mathcal{Y}_i]^t$$ and $$w_i$$ be the signal $$\left(x,y\right) \mapsto Ae^{2i\pi\left(\frac{x}{X_i} + \frac{y}{Y_i}\right)}$$ for any $$i \in \mathbb{N}$$. Then the average of discrete Fourier transforms $$\overline{F}_n = \frac{1}{n}\sum\limits_{i=1}^{n} F_i$$ converges:

$$
\overline{F}_n \left(u,v\right) \xrightarrow[n \to \infty]{a.s} \frac{A}{M \times N} \frac{\left(1 - e^{2i\pi \frac{M}{\mu}}\right) \left(1 - e^{2i\pi \frac{N}{\mu}}\right)}{\left(1 - e^{2i\pi\left(\frac{1}{\mu} + \frac{u}{M}\right)}\right) \left(1 - e^{2i\pi\left(\frac{1}{\mu} + \frac{v}{N}\right)}\right)}
$$

for all $0 \leq u < M, \ 0 \leq v < N$.

_Proof._ Direct application of the continuous mapping theorem. For details, see appendix~\labelcref{proof:convergence_of_energy}.

It is worth noting that the rendering work of $$G$$ generally contains multiple tasks, each requires to render multiple image frames. But the number of reference instances used for spectral analysis is much smaller, practically less than $$1\%$$ the total number of rendered frames. While keeping the robustness of ANGV, we can adjust this ratio be even smaller by increasing the size $$n$$ of the noise vector $$W$$.