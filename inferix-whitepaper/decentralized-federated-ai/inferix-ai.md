# Inferix AI

From the information presented above, we can conclude that the hardware of the Inferix network is well-suited to serve as an infrastructure for federated AI. Next, we will discuss the design of the Inferix Federated AI system.

#### Figure 13: <a id="fig_inferix_tensoropera_integrated_architecture"></a>
<figure><img src="../../.gitbook/assets/inferix-decentralized-fed-ai-architecture.svg" alt=""><figcaption><p>Inferix and TensorOpera integrated architecture</p></figcaption></figure>

In the [architectural design](#fig_inferix_tensoropera_integrated_architecture), Inferix enables _generative AI artists_ and content creators to access AI models trained by _AI Builders_ within the Inferix community, as well as models trained by the Inferix Team itself (built-in models). These services can be hosted on the Inferix Manager Node system or on the TensorOpera AI platform.

AI Builders have the option to run their models directly on the Inferix infrastructure or through the TensorOpera Bridge. The output result can be hosted in Inferix infra with custom domain option.

In addition to handling graphics rendering tasks, Inferix GPU Nodes also serve as Federated Learning Clients by running the Inferix TensorOpera CLI.

* _TensorOpera CLI:_ the CLI client that is built based on TensorOpera open source with Inferix PoW algorithm integrated.
* _Inferix PoW:_ general PoW algorithm used to calculate the actual work performed by workers, excluding those involved in rendering tasks. Inferix PoW is based on the Proof-of-Rendering mechanism to calculate the [Inferix Bench](/inferix-whitepaper/economic-model/inferix-bench-and-ibme/ib-and-ibm.md), incorporating an algorithm to accurately measure the actual working time of a node.
