# Table of contents

* [Getting Started](README.md)
  * [Overview](getting-started/overview.md)
  * [$IFX](readme/usdifx.md)
  * [Resources](getting-started/resources.md)
  * [Brand Kit](getting-started/brand-kit.md)
  * [Frequently asked questions (FAQs)](readme/frequently-asked-questions-faqs.md)
* [Inferix Whitepaper](inferix-whitepaper/README.md)
  * [Introduction](inferix-whitepaper/introduction/README.md)
    * [Rendering network using crowdsourced GPU](inferix-whitepaper/introduction/rendering-network-using-crowdsourced-gpu.md)
    * [Rendering verification problem](inferix-whitepaper/introduction/rendering-verification-problem.md)
  * [High-level description of ANGV](inferix-whitepaper/high-level-description/README.md)
    * [Noise generation](inferix-whitepaper/high-level-description/noise-generation.md)
    * [Noise verification](inferix-whitepaper/high-level-description/noise-verification.md)
    * [Thread model](inferix-whitepaper/high-level-description/thread-model.md)
  * [Implementation of ANGV](inferix-whitepaper/implementation/README.md)
    * [Structure of noise](inferix-whitepaper/implementation/structure-of-noise.md)
    * [Noise insertion](inferix-whitepaper/implementation/noise-insertion/README.md)
      * [Geometric constraints](inferix-whitepaper/implementation/noise-insertion/geometric-constraints.md)
      * [Distortion region](inferix-whitepaper/implementation/noise-insertion/distortion-region.md)
    * [Adaptive noise spreading](inferix-whitepaper/implementation/adaptive-noise-spreading.md)
    * [Verification key generation](inferix-whitepaper/implementation/verification-key-generation.md)
    * [Noise verification](inferix-whitepaper/implementation/noise-verification.md)
    * [Threat analysis](inferix-whitepaper/implementation/threat-analysis/README.md)
      * [Attacks on verification keys](inferix-whitepaper/implementation/threat-analysis/attacks-on-verification-keys.md)
      * [Attacks on noises](inferix-whitepaper/implementation/threat-analysis/attacks-on-noises.md)
      * [Attacks on verifiers](inferix-whitepaper/implementation/threat-analysis/attacks-on-verifiers.md)
    * [Performance evaluation](inferix-whitepaper/implementation/performance-evaluation.md)
    * [Integration](inferix-whitepaper/implementation/integration.md)
  * [Decentralized visual computing](inferix-whitepaper/decentralized-visual-computing/README.md)
    * [Client Apps plugin](inferix-whitepaper/decentralized-visual-computing/client-apps-plugin.md)
    * [Client API and SDK](inferix-whitepaper/decentralized-visual-computing/client-api-and-sdk.md)
    * [Manager node](inferix-whitepaper/decentralized-visual-computing/manager-node.md)
    * [Worker node](inferix-whitepaper/decentralized-visual-computing/worker-node.md)
    * [Decentralized storage](inferix-whitepaper/decentralized-visual-computing/decentralized-storage-and-data-security/README.md)
      * [Data categories](inferix-whitepaper/decentralized-visual-computing/decentralized-storage-and-data-security/data-categories.md)
      * [Multi-level 3D polygon data](inferix-whitepaper/decentralized-visual-computing/decentralized-storage-and-data-security/multi-level-3d-polygon-data.md)
      * [Polygon digester](inferix-whitepaper/decentralized-visual-computing/decentralized-storage-and-data-security/polygon-digester.md)
      * [Decentralized storage](inferix-whitepaper/decentralized-visual-computing/decentralized-storage-and-data-security/decentralized-storage.md)
      * [Decentralized cache](inferix-whitepaper/decentralized-visual-computing/decentralized-storage-and-data-security/decentralized-cache.md)
    * [Data security with FHE and TEE](inferix-whitepaper/decentralized-visual-computing/data-security-with-fhe-and-tee/README.md)
      * [Verifier data security enhancement with FHE](inferix-whitepaper/decentralized-visual-computing/data-security-with-fhe-and-tee/verifier-data-security-enhancement-with-fhe.md)
      * [Worker and Manager data security enhancement with FHE](inferix-whitepaper/decentralized-visual-computing/data-security-with-fhe-and-tee/worker-and-manager-data-security-enhancement-with-fhe.md)
  * [Decentralized federated AI](inferix-whitepaper/decentralized-federated-ai/README.md)
    * [Federated learning with TensorOpera](inferix-whitepaper/decentralized-federated-ai/federated-learning-with-tensoropera.md)
    * [Meta LLaMA](inferix-whitepaper/decentralized-federated-ai/meta-llama.md)
    * [Stable Diffusion](inferix-whitepaper/decentralized-federated-ai/stable-diffusion.md)
    * [Other AI models](inferix-whitepaper/decentralized-federated-ai/other-ai-models.md)
    * [Inferix AI](inferix-whitepaper/decentralized-federated-ai/inferix-ai.md)
  * [Economic model](inferix-whitepaper/economic-model/README.md)
    * [GPU compute market for visual computing and federated AI](inferix-whitepaper/economic-model/gpu-compute-market-for-visual-computing-and-federated-ai.md)
    * [Inferix vision](inferix-whitepaper/economic-model/inferix-vision.md)
    * [$IFX token](inferix-whitepaper/economic-model/usdifx-token.md)
    * [Burn-Mint-Work token issuance model](inferix-whitepaper/economic-model/burn-mint-work-token-issuance-model.md)
    * [Inferix bench and IBME](inferix-whitepaper/economic-model/inferix-bench-and-ibme/README.md)
      * [IB and IBM](inferix-whitepaper/economic-model/inferix-bench-and-ibme/ib-and-ibm.md)
      * [IBME](inferix-whitepaper/economic-model/inferix-bench-and-ibme/ibme.md)
    * [Price simulation](inferix-whitepaper/economic-model/price-simulation.md)
    * [Token metrics and allocation](inferix-whitepaper/economic-model/token-metrics-and-allocation/README.md)
      * [Token allocation](inferix-whitepaper/economic-model/token-metrics-and-allocation/token-allocation.md)
      * [Token vesting](inferix-whitepaper/economic-model/token-metrics-and-allocation/token-vesting.md)
    * [Governance](inferix-whitepaper/economic-model/governance.md)
    * [Node staking and rewards](inferix-whitepaper/economic-model/node-staking-and-rewards/README.md)
      * [Worker](inferix-whitepaper/economic-model/node-staking-and-rewards/worker.md)
      * [Verifier](inferix-whitepaper/economic-model/node-staking-and-rewards/verifier.md)
      * [Manager](inferix-whitepaper/economic-model/node-staking-and-rewards/manager.md)
      * [Penalty pool](inferix-whitepaper/economic-model/node-staking-and-rewards/penalty-pool.md)
    * [Node sale and guaranteed node buyback](inferix-whitepaper/economic-model/node-sale-and-penalty-pool/README.md)
      * [Node sales](inferix-whitepaper/economic-model/node-sale-and-penalty-pool/node-sales.md)
      * [Guaranteed Node Buyback](inferix-whitepaper/economic-model/node-sale-and-penalty-pool/guaranteed-node-buy-back.md)
  * [Future development](inferix-whitepaper/future-development/README.md)
    * [PoR and NFT minting for graphics creative assets](inferix-whitepaper/future-development/por-and-nft-minting-for-graphics-creative-assets.md)
    * [ZKP and PoR communication](inferix-whitepaper/future-development/zkp-and-por-communication.md)
    * [Inferix RemotePC](inferix-whitepaper/future-development/inferix-remotepc.md)
    * [Rendering professional network](inferix-whitepaper/future-development/rendering-professional-network.md)
  * [References](inferix-whitepaper/references.md)
  * [Appendix A: Proofs](inferix-whitepaper/appendix.md)
  * [Appendix B: Price simulation details](inferix-whitepaper/appendix-b-price-simulation-details.md)
  * [Appendix C: Hardware requirements for nodes](inferix-whitepaper/appendix-c-hardware-requirements-for-nodes.md)
  * [Appendix D: Performance evaluation data](inferix-whitepaper/appendix-d-performance-evaluation-data.md)
* [Worker Node Guide](worker-node-guide/README.md)
  * [What is Worker Node](worker-node-guide/what-is-worker-node/README.md)
    * [How do the Worker Node work](worker-node-guide/what-is-worker-node/how-do-the-worker-node-work.md)
    * [Worker Node Rewards](worker-node-guide/what-is-worker-node/worker-node-rewards.md)
    * [How to run Worker Node](worker-node-guide/what-is-worker-node/how-to-run-worker-node.md)
    * [What is the Worker Node License (NFT)](worker-node-guide/what-is-worker-node/what-is-the-worker-node-license-nft.md)
  * [Worker Node Sales](worker-node-guide/worker-node-sales/README.md)
    * [Guide to Purchase Worker Nodes](worker-node-guide/worker-node-sales/guide-to-purchase-worker-nodes.md)
    * [Worker Node Sale Timeline](worker-node-guide/worker-node-sales/worker-node-sale-timeline.md)
    * [Node Supply, Price, Tiers and Purchase Caps](worker-node-guide/worker-node-sales/node-purchase-caps.md)
    * [Guaranteed Node Buyback](worker-node-guide/worker-node-sales/guaranteed-node-buyback.md)
    * [How to get Node Whitelisted?](worker-node-guide/worker-node-sales/how-to-get-whitelisted.md)
    * [Smart Contract Addresses](worker-node-guide/worker-node-sales/smart-contract-addresses.md)
    * [User Discounts & Referral Program](worker-node-guide/worker-node-sales/referral-program.md)
    * [Worker Node Purchase FAQ](worker-node-guide/worker-node-sales/worker-node-purchase-faq.md)
    * [ABKK Collaboration FAQ](worker-node-guide/worker-node-sales/abkk-collaboration-faq.md)
* [Verifier Node Guide](verifier-node-guide/README.md)
  * [What is Verifier Node](verifier-node-guide/what-is-verifier-node/README.md)
    * [How do the Verifier Node work](verifier-node-guide/what-is-verifier-node/how-do-the-verifier-node-work.md)
    * [Verifier Node Rewards](verifier-node-guide/what-is-verifier-node/verifier-node-rewards.md)
    * [How to run Verifier Node](verifier-node-guide/what-is-verifier-node/how-to-run-verifier-node.md)
    * [What is the Verifier Node License (NFT)](verifier-node-guide/what-is-verifier-node/what-is-the-verifier-node-license-nft.md)
  * [Verifier Node Sales](verifier-node-guide/verifier-node-sales/README.md)
    * [Guide to Purchase Verifier Nodes](verifier-node-guide/verifier-node-sales/guide-to-purchase-verifier-nodes.md)
    * [Verifier Node Sale Timeline](verifier-node-guide/verifier-node-sales/verifier-node-sale-timeline.md)
    * [Node Supply, Price, Tiers and Purchase Caps](verifier-node-guide/verifier-node-sales/node-purchase-caps.md)
    * [Guaranteed Node Buyback](verifier-node-guide/verifier-node-sales/guaranteed-node-buyback.md)
    * [How to get Node Whitelisted?](verifier-node-guide/verifier-node-sales/how-to-get-whitelisted.md)
    * [Smart Contract Addresses](verifier-node-guide/verifier-node-sales/smart-contract-addresses.md)
    * [User Discounts & Referral Program](verifier-node-guide/verifier-node-sales/referral-program.md)
    * [Verifier Node Purchase FAQ](verifier-node-guide/verifier-node-sales/verifier-node-purchase-faq.md)
    * [Aethir Node Winners FAQ](verifier-node-guide/verifier-node-sales/aethir-node-winners-faq.md)
* [Inferix MVP](inferix-mvp/README.md)
  * [Tutorial: MVP for designers & GPU owners](inferix-mvp/tutorial-mvp-for-designers-and-gpu-owners.md)
  * [PoR MVP](inferix-mvp/por-mvp.md)
* [Inferix Testnet 2 on Solana & IoTeX \[ENDED\]](inferix-testnet-2-on-solana-and-iotex-live/README.md)
  * [Adding GPUs to the Network](inferix-testnet-2-on-solana-and-iotex-live/adding-gpus-to-the-network/README.md)
    * [For GPU providers](inferix-testnet-2-on-solana-and-iotex-live/adding-gpus-to-the-network/for-gpu-providers.md)
    * [For GPU providers without funds](inferix-testnet-2-on-solana-and-iotex-live/adding-gpus-to-the-network/for-gpu-providers-without-funds.md)
    * [For users without GPUs](inferix-testnet-2-on-solana-and-iotex-live/adding-gpus-to-the-network/for-users-without-gpus.md)
    * [For Inferix Node Holders](inferix-testnet-2-on-solana-and-iotex-live/adding-gpus-to-the-network/for-inferix-node-holders.md)
  * [Renting GPU Devices](inferix-testnet-2-on-solana-and-iotex-live/renting-gpu-devices.md)
  * [User Revenue Calculation](inferix-testnet-2-on-solana-and-iotex-live/user-revenue-calculation/README.md)
    * [Worker Rewards](inferix-testnet-2-on-solana-and-iotex-live/user-revenue-calculation/worker-rewards.md)
    * [Rental Revenue](inferix-testnet-2-on-solana-and-iotex-live/user-revenue-calculation/rental-revenue.md)
    * [Viewing Revenue](inferix-testnet-2-on-solana-and-iotex-live/user-revenue-calculation/viewing-revenue.md)
    * [Claiming Rewards](inferix-testnet-2-on-solana-and-iotex-live/user-revenue-calculation/claiming-rewards.md)
  * [GPU Staking & Unstaking](inferix-testnet-2-on-solana-and-iotex-live/gpu-staking-and-unstaking/README.md)
    * [Staking Requirements](inferix-testnet-2-on-solana-and-iotex-live/gpu-staking-and-unstaking/staking-requirements.md)
    * [Unstaking GPUs](inferix-testnet-2-on-solana-and-iotex-live/gpu-staking-and-unstaking/unstaking-gpus.md)
  * [Guide to get tIFX tokens](inferix-testnet-2-on-solana-and-iotex-live/guide-to-get-tifx-tokens.md)
  * [Why choose Inferix DePIN GPU Solutions?](inferix-testnet-2-on-solana-and-iotex-live/why-choose-inferix-depin-gpu-solutions.md)
* [Inferix Testnet 1 on IoTeX \[ENDED\]](inferix-testnet-1-on-iotex-ended/README.md)
  * [Inferix GPU Solutions](inferix-testnet-1-on-iotex-ended/inferix-gpu-solutions.md)
  * [Adding GPUs to the Network](inferix-testnet-1-on-iotex-ended/adding-gpus-to-the-network.md)
  * [Renting GPU Devices](inferix-testnet-1-on-iotex-ended/renting-gpu-devices.md)
  * [User Revenue Calculation](inferix-testnet-1-on-iotex-ended/user-revenue-calculation.md)
  * [GPU Staking](inferix-testnet-1-on-iotex-ended/gpu-staking.md)
  * [Multiple options to participate in the Staking & Mining Program](inferix-testnet-1-on-iotex-ended/multiple-options-to-participate-in-the-staking-and-mining-program.md)
  * [Special airdrop for Inferix Node Holders! 🎉](inferix-testnet-1-on-iotex-ended/special-airdrop-for-inferix-node-holders.md)
  * [Guide to get tIFX tokens](inferix-testnet-1-on-iotex-ended/guide-to-get-tifx-tokens.md)
  * [FAQ](inferix-testnet-1-on-iotex-ended/faq.md)
* [Inferix Explorer](inferix-explorer.md)
* [Team & Achievements](team-and-achievements/README.md)
  * [Our Story](team-and-achievements/our-story.md)
  * [Team](team-and-achievements/team.md)
  * [Member of Cohort 1 DePINSurf](team-and-achievements/member-of-cohort-1-depinsurf.md)
  * [Achievements](team-and-achievements/achievements.md)
* [Community & Events](community-and-events/README.md)
  * [Events](community-and-events/events.md)
  * [Inferix Campaign: "ALLIANCE" (ENDED)](community-and-events/introducing-inferix-campaign-alliance.md)
* [Terms of Service](terms-of-service/README.md)
  * [Privacy Policy](terms-of-service/privacy-policy.md)
  * [Airdrop Terms of Service](terms-of-service/airdrop-terms-of-service.md)
