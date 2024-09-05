# Performance evaluation

We evaluate the execution time of noise insertion and noise verification on several scenes, the lengths of the noise vectors variate from 2 to 40. The tests are executed on a workstation of Intel:registered: Core:tm: i5 2.5 GHz CPU, 32 GB RAM and NVIDIA GeForce RTX3070 GPU. The performance of noise insertion and verification is given in the figures below, detailed data is given in tables in [Appendix D](../appendix-d-performance-evaluation-data.md).

#### Figures 9-10: <a href="#fig_noise_insertion_verification" id="fig_noise_insertion_verification"></a>

<div>

<figure><img src="../../.gitbook/assets/performance_eval.png" alt="" width="282"><figcaption><p>Noise insertion</p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/performance_eval_verif.png" alt="" width="277"><figcaption><p>Noise verification</p></figcaption></figure>

</div>

The noise insertion needs to analyze the structure of the input scene to generate and insert noises, that explains the noise insertion experimental results where the execution time, while being proportional with the length of the noise vector, depends importantly on the complexity of input scenes. A loose quantification for this complexity can be observed via the GPU execution times needed to render the scenes, shown in [Table 1](#fig_rendering_time_of_scenes).

#### Table 1: <a id="fig_rendering_time_of_scenes"></a>

| Scene | Rendering time (in seconds) | Rendered frame size |
| -- | -- | - |
| Coca-Cola | 8.09 | 1080x1080 |
| Grease Pencil Bike | 4.30 | 2880x1620 |
| Blender 3.5 Splash | 11.41 | 1327x1250 |
| Bathroom Above Corner | 146.41 | 4000x3000 |

Whereas the noise verification needs only to analyze the distortion regions whose locations are given by the verification key, then the execution time depends mostly on the number of the regions (which is also the length of the noise vector) and slightly on the size of the rendered frame.
