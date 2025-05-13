# How do the Worker Node work

The graphics rendering service consists in a network of decentralized machines called _nodes_ which are of 3 kinds: _manager_, _verifier_ and _**worker**_. The _managers_ are dedicated machines of Inferix while _verifiers_ and _**workers**_ are machines joined by GPU owners.

A typical AI inference or graphic rendering session contains several steps here we explain main Worker Nodes in short-terms :point\_down: ([read the complete documentation about Worker Nodes HERE](../../inferix-whitepaper/decentralized-visual-computing/worker-node.md))

The task controller of the _manager_ receives the AI/rendering job request, the job will be split to several tasks and assigned to _workers._

After the tasks finished, the _Worker_ sent the results back to manager and they will be verified by Worker Nodes.

After the results are successfully verified, an amount of rewarded IFX tokens will be sent from Inferix Blockchain system to _worker._

***

_Penalty Pool_ is a token fund collected from penalties imposed on Worker Nodes that violate Inferix standards while performing assigned visual computing or AI inference tasks. The Penalty Pool is used as a reward for Verifiers who actively contribute to ensuring the efficient operation of the network.\
