# Algorithms

To handle this problem, we follow the approach of digital watermarking ([\[6\]](../references.md),[\[7\]](../references.md)) and propose a scheme called _Active Noise Generation and Verification_ (ANGV) which is a variant of _proof of ownership_ ([\[8\]](../references.md),[\[9\]](../references.md)). Our scheme has several favorable properties:

1. **Efficiency**: noise generation and verification require much lower computation resources compared with the graphics rendering; the total performance of the system is not affected.
2. **Fidelity**: the scheme needs to modify the initial scene so the rendered output will be distorted; but the distortion is regulated being below the human perception capability, hence there is no loss of quality.
3. **Robustness**: the embedded noises are robust under rendering enhancements (e.g. anti-aliasing) and post-processing operations.
4. **Effectiveness**: there is no need to use special graphics rendering software as in the case of FHE.

## 
