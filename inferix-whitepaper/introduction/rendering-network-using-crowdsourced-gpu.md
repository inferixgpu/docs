# Rendering network using crowdsourced GPU

The graphics rendering service consists in a network of decentralized machines called _nodes_ which are of 3 kinds: _manager_, _worker_ and _verifier_. The _managers_ are dedicated machines of Inferix while _verifiers_ and _workers_ are machines joined by GPU owners. The number of _workers_ is normally much larger than the number of _managers_ and _verifiers_.

<figure><img src="../../.gitbook/assets/rendering-network-flow (2).svg" alt=""><figcaption><p>Rendering flow</p></figcaption></figure>

A typical rendering session contains several steps as shown in the image and explained below:

1. A user creates a rendering job request using the Inferix's plugin for client, this job uploads user's scene data to some _manager_.
2.  The rendering task controller of the _manager_ receives the rendering job request, then

    1. splits it into multiple rendering tasks, each task consists of the scene data and several parameters: range of frames to be rendered, output format, etc.
    2. generates corresponding verification keys and sends these keys to the verifying task controller.

    The rendering tasks will be assigned to _workers_ and the verification keys will be sent to the verifying task controller.
3. Receiving a rendering task, a _worker_ renders the included scene using the parameters given by the task. When it finishes, it saves the rendered frames to a decentralized storage, then notifies the _manager_ by a message containing a unique URL to the result.
4. The verifying task controller of the notified _manager_ receives the notification then creates a verification task; this task will be assigned to a _verifier_.
5. Receiving a verification task, a _verifier_
   1. checks the authenticity of the corresponding rendered frames, then
   2. notifies the _manager_ about the verification result.
6. If the rendered frames pass the verification, then the manager notifies the user by a message containing the URL to the rendered frames. Otherwise, these frames are rejected.
7. The user downloads the frames from the storage and manually confirms whether they meet the expectation, if they do not then the user sends a bad result claim to the manager.

The _managers_ synchronize a database of rendering and verification tasks. That makes the rendering service being both logically and physically decentralized: a graphics scene can be simultaneously rendered by different _workers_ and later checked by different _verifiers_, the machines of _workers_ and _verifiers_ can be also located at different geographical locations.
