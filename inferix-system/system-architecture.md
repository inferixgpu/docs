# System architecture

Inferix is a decentralized GPU network for visual computing and AI, it is built to bridge the needs of users and hardware owners. Its solution meets real-world problems across a range of industries, not only for the AI field but also for high-quality rendering needs.

<figure><img src="../.gitbook/assets/Page08.jpg" alt=""><figcaption></figcaption></figure>

Users (e.g. 3D graphics artists, game developers, enterprises) who need GPU computing power for rendering high-quality graphics can use Inferix system to continuously access these precious resources with faster processing time and more efficient spending.

Owners of GPUs can share idle resources to Inferix network and earn long-term passive income while simultaneously balancing their main jobs or leisure activities.

<figure><img src="../.gitbook/assets/Page09.jpg" alt=""><figcaption></figcaption></figure>

## Rendering network

The graphics rendering service consists in a network of decentralized machines called *nodes* which are of 3 kinds: *manager*, *worker* and *verifier*. The *managers* and *verifiers* are dedicated machines of Inferix while the *workers* are machines joined by GPU owners. The number of *workers* is normally much larger than the number of *managers* and *verifiers*.

<!-- ![Graphics rendering flow](../.gitbook/assets/rendering_service.png#center) -->
<figure><img src="../.gitbook/assets/rendering_service.png" alt=""><figcaption></figcaption></figure>

A typical rendering session contains several steps:
 1. A user submits a graphics scene to some *manager* using the Inferix plugin for client.
 2. The *manager* who receives the graphics scene builds corresponding rendering jobs, each job consists of several parameters: range of images to be rendered, image format, etc. These job will be dispatched to *workers*.
 3. Receiving a rendering job, a *worker* renders the graphics scene using the parameters given by the job. When it finishes, it sends the rendered images to a shared storage.
 4. The *worker* then notifies a *manager* about the status of rendering job.
 5. The notified manager creates a verification job and dispatches this job to some *verifier*.
 6. Receiving a verification job, a *verifier* checks the authenticity of the corresponding rendered images.
 7. The *verifier* then notifies the *manager* about the verification results.
 8. The *manager* notifies the user about the graphics rendering result.
 9. If there is no error, the user can finally download the rendered images/video from the shared storage.
