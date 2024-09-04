# Verification key generation

The constraints and trade-offs discussed in the [noise insertion](/inferix-whitepaper/implementation/noise-insertion/README.md) and the [noise spreading](/inferix-whitepaper/implementation/adaptive-noise-spreading.md) are to ensure the _fidelity_ of rendered results and the _robustness_ of the verification, but they do not concern the security. Indeed, any attacker knowing the algorithm and parameters including trade-offs, can straightforwardly generate (without rendering the graphics scene) forged images with the same spectral characteristics, finally bypasses the verification. The security is supported using verification keys.

Each rendering task has a secret key, in current implementation, this key is also the task identification number $$J_{\mathtt{id}}$$. When embedding the noise vector $$W$$ into the scene $$G$$, this number is used to compute distortion regions $$k_i$$ for all $$1 \leq i \leq n$$, the vector $$\left(k_i\right)_{1 \leq i \leq n}$$ is called verification key. The computation is modeled as a function (c.f.~\cref{equ:verification_key}):

$$
K_{\mathtt{verif}} \colon \left(S,W,J_{\mathtt{id}}\right) \mapsto \left(k_i\right)_{1 \leq i \leq n}
$$

In the operation of the rendering network, the leak of used verification keys is unavoidable. For instance, a _worker_ may register itself to become a _verifier_ node; when got accepted, it will be assigned verification tasks containing verification keys, then will be able to collect used keys. Even worse, colluding _workers_ may exchange collected keys so that each of them will possess a much larger collection [[12]](/inferix-whitepaper/references.md#12). Another possibility is the malicious _workers_ may get verification keys from some compromised _verifiers_. Hence, the $$K_{\mathtt{verif}}$$ must be designed so that the knowledge about used keys does not leak any information about the next generated keys. The following proposition is necessary for the security of ANGV.

_**Proposition 3.**_ $$K_{\mathtt{verif}}$$ is a cryptographic hash function.