## Rendering network

The graphics rendering service consists in a network of decentralized machines called *nodes* which are of $3$ kinds: *manager*, *worker* and *verifier*. The *managers* and *verifiers* are dedicated machines of Inferix while the *workers* are machines joined by GPU owners. The number of *workers* is normally much larger than the number of *managers* and *verifiers*.

<figure><img id="figure" src="../../.gitbook/assets/rendering_service.png" alt=""><figcaption>Figure 1: Graphics rendering flow</figcaption></figure>

A typical rendering session contains several steps which are shown in <a href="#figure">Figure 1:</a>
 1. A user submits a graphics scene to some *manager* using the Inferix plugin for client.
 2. The *manager* who receives the graphics scene builds corresponding rendering jobs, each job consists of several parameters: range of images to be rendered, image format, etc. These job will be dispatched to *workers*.
 3. Receiving a rendering job, a *worker* renders the graphics scene using the parameters given by the job. When it finishes, it sends the rendered images to a shared storage.
 4. The *worker* then notifies a *manager* about the status of rendering job.
 5. The notified manager creates a verification job and dispatches this job to some *verifier*.
 6. Receiving a verification job, a *verifier* checks the authenticity of the corresponding rendered images.
 7. The *verifier* then notifies the *manager* about the verification results.
 8. The *manager* notifies the user about the graphics rendering result.
 9. If there is no error, the user can finally download the rendered images/video from the shared storage.

The *managers* synchronize a database of rendering and verification jobs. That makes the rendering service being both logically and physically decentralized: a graphic scene can be simultaneously rendered by different *workers* and later checked by different *verifiers*, the machines of *workers* and *verifiers* can be also located at different geographical locations.

## Rendering authentication problem
A user submits some graphics work to some *manager* (cf. <a href="#figure">Figure 1:</a>), this work consists of several graphics scenes; each contains information about graphical objects, the camera, light sources and materials. The photorealistic rendering consists of sophisticated computation processes that calculate light properties at surfaces of all visible objects, results in 3D rendered images of the scene [[1]](#1).

One of the most important problems that Inferix has to solve is to maintain the *authenticity* of rendered results. That means how to ensure that once a user submits a valid graphics scene, then after waiting for an amount of time, the user will receive authentically rendered images. The authenticity can be defined informally as if the result received from the rendering network and the result received when the scene is genuinely rendered by a graphics rendering software are human perceptual indistinguishable.

The *worker* joined the rendering network are mostly workstations of GPU owners who want to make profit from their unused computing resources. Respecting the privacy of GPU owners and their computation resources, beside a lightweight open source software installed to manage the communication with the network, there is completely no control on *worker*.

Consequently, there is no constraint to oblige *worker* to render the graphics scene correctly. Indeed, a malicious *worker* may receive a rendering job, but does nothing then uses some random images as results. Without rendering the graphics scene by themselves, the *managers* and users know only superficial features of what the rendered images look like. Obviously, the *managers* and users have no interest in rendering the scene themselves since if they can do that, there is no need to rely on *worker*. Moreover, we cannot deploy any surveillance mechanism on the machines of *worker* due to privacy reasons. Even if we try to do that, this is only a matter of time before the *worker* reverse engineers the mechanism and eventually bypass it. The situation seems not favor us: checking the authenticity of something while only having a little knowledge about it, otherwise the attacker has complete information.

Naturally, a public-key cryptography approach is using a scheme of *fully homomorphic encryption* (FHE) [[2]](#2). The graphics scene is encrypted first by a private key before sending to *worker*. Given the corresponding public key, the homomorphic encryption software performs the graphics rendering on the encrypted scene without needing to decrypt it. Finally, the encrypted rendered results are returned and decrypted at the user's side using the private key. The advantage of FHE is that the *worker*, even being able to modify the FHE softwares on their side, cannot interfere the FHE graphics rendering processes or forge the rendering results without being detected. Unfortunately, this approach is impractical since all state-of-the-art implementations will make the performance of the homomorphic encryption graphics rendering become unacceptable [[3]](#3).

## Algorithms
To handle this problem, we follow the approach of digital watermarking ([[4]](#4),[[5]](#5)) and propose a scheme called \emph{Active Noise Generation and Verification} (ANGV) which is a variant of *proof of ownership* ([[6]](#6),[[7]](#7)). Our scheme has several favorable properties:
 1. **Efficiency**: noise generation and verification requires much lower computation resources compared with the graphics rendering, the total performance of the system is not affected.
 2. **Fidelity**: the scheme needs to modify the initial scene so the rendered output will be distorted; but the distortion is regulated being below the human perception capability, hence there is no loss of quality.
 3. **Robustness**: the embedded noises are robust under rendering enhancements (e.g. anti-aliasing) and post-processing operations.
 4. **Effectiveness**: there is no need to use a special graphics rendering software as in the case of FHE.

## References
<a id="1">[1]<a>
John F. Hughes, Andries van Dam, Morgan McGuire, David F. Sklar, James D. Foley, Steven K. Feiner, Kurt Akeley. Addison-Wesley. Computer Graphics: Principles and Practice. 2014.

<a id="2">[2]<a>
Craig Gentry. Proceedings of the 41st Annual ACM Symposium on Theory of Computing. Fully Homomorphic Encryption using Ideal Lattices. 2009.

<a id="3">[3]<a>
Chiara Marcolla, Victor Sucasas, Marc Manzano, Riccardo Bassoli, Frank H. P. Fitzek, Najwa Aaraj. Survey on Fully Homomorphic Encryption, Theory, and Applications. 2022.

<a id="4">[4]<a>
Ingemar J. Cox, Joe Kilian, Tom Leighton, Talal Shamoon. IEEE Transactions on Image Processing. Secure Spread Spectrum Watermarking for Multimedia. 1997.

<a id="5">[5]<a>
Ingemar J. Cox, Matthew L. Miller, Andrew L. McKellips. IEEE Transactions on Image Processing. Watermarking as Communications with Side Information. 1999.

<a id="6">[6]<a>
Min Wu, Bede Liu. Proceedings of International Conference on Image Processing. Watermarking for Image Authentication. 1998.

<a id="7">[7]<a>
Minerva M. Yeung, Fred Mintzer. Proceedings of International Conference on Image Processing. An Invisible Watermarking Technique for Image Verification. 1997.