# How do the Verifier Node work

The graphics rendering service consists in a network of decentralized machines called _nodes_ which are of 3 kinds: _manager_, _worker_ and _**verifier**_. The _managers_ are dedicated machines of Inferix while _**verifiers**_ and _workers_ are machines joined by GPU owners.

A typical rendering session contains several steps here we explain main Verifier Nodes in short-terms :point\_down: ([read the complete Rendering  Flow HERE](../../inferix-whitepaper/introduction/rendering-network-using-crowdsourced-gpu.md))

The rendering task controller of the _manager_ receives the rendering job request, the rendering tasks are assigned to _workers_ and the verification keys will be sent to the verifying task controller.

The verifying task controller receives the notification and then it creates a verification task; **this task will be assigned to a **_**verifier**_.

After receiving a verification task, a _verifier:_

1. checks the authenticity of the corresponding rendered frames.
2. notifies the _manager_ about the verification result.

Then, if the rendered frames passed the verification, the manager notifies the user by a message containing the URL to the rendered frames. The user manually confirms whether the results meet the expectation, if they do not then the user sends a bad result claim to the manager.&#x20;

***

_Penalty Pool_ is a token fund collected from penalties imposed on Worker Nodes that violate Inferix standards while performing assigned visual computing or AI inference tasks. The Penalty Pool is used as a reward for Verifiers who actively contribute to ensuring the efficient operation of the network.\
