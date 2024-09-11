# What is Verifier Node

Verifier Node is one of the fundamental components of the InferiX network backend infrastructure:

* **Worker Node:** The most essential component in the network, responsible for the bulk of the network’s rendering and processing tasks. Workers receive rewards from the network’s service revenue (75% of the Ecosystem Fund). Each Worker must hold a certain amount of $IFX tokens as a penalty fund to ensure they meet Inferix standards.
* **Verifier Node:** These nodes ensure the reliability and accuracy of the network. Inferix will have about 25,000 Verifier Nodes, and they are crucial for maintaining the integrity of the system. Unlike Workers, Verifier nodes don’t require heavy hardware and can be run on mobile devices. They receive 7.5% of the $IFX token supply as rewards.\
  \
  **Verifier** is the component that receives the least amount of data among the three main components of the Inferix network. The input data for a **Verifier** includes a random subset of the rendering job's output along with the algorithm and key to verify it. Rendering jobs that do not require high data security will be executed by **standard Verifiers.** Otherwise, those that require high data security will be executed by **secure Verifiers.**\
  \
  The hardware requirements for **secure Verifiers** are higher than those for **standard Verifiers**, and specifically, these nodes must be equipped with GPUs.\
  (read min. requirements[ HERE](../../inferix-whitepaper/appendix-c-hardware-requirements-for-nodes.md))\

* **Manager Node:** Manager nodes coordinate the overall network and are critical for handling the Proof of Render (PoR) algorithm. Inferix plans to have 2,500 Manager Nodes to manage millions of render jobs daily. The reward pool for Manager Nodes is 1.25% of the $IFX token supply.
