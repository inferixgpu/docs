# High-level description

To handle this problem, we follow the approach of digital watermarking\cite{Cox1997,Cox1999} and propose a scheme called _Active Noise Generation and Verification_ (ANGV) which is a variant of _proof of ownership_\cite{Wu1998,Yeung1997}. Our scheme has several favorable properties:

* _Efficiency:_ noise generation and verification require much lower computational resources compared with the graphics rendering; the total performance of the system is not affected.
* _Fidelity:_ the scheme needs to modify the initial scene so the rendered output will be distorted, but the distortion is human perception sub-threshold.
* _Robustness:_ the embedded noises are robust under rendering enhancements and post-processing operations (e.g. de-noising, anti-aliasing).
* _Effectiveness:_ there is no need to use special rendering software as in the case of FHE.
* _Security:_ without knowing the verification key, attackers need the same computational cost with the rendering to bypass the authenticity verification.

In current digital watermarking schemes for authentication and ownership verification\cite{Wu1998,Yeung1997,Wolfgang1999,Craver1997}, invisible watermarks will be embedded into the digital content needed to be protected. The detector (or verifier) tries to extract the watermark from a tested content, then compares the extracted watermark with the original embedded one, if the comparison is passed then the content is authenticated.

However, in the context of Inferix's rendering network, the _manager_ has access to the image only after the graphics scene has been rendered by _workers_. It is nonsense to embed watermark into the image at this point since the watermarking cannot help to detect any malicious manipulations which may happen before that, i.e. in the rendering process. Our approach is to embed watermarks into the graphics scene submitted by users before sending it to _workers_. The _Active Noise Generation and Verification_ scheme consists of two algorithms as described below.

