# Meta LLaMA

In its GPU hardware segment, Inferix focuses on devices optimized for graphics rendering, with the RTX3090 and RTX4090 serving as the flagship devices.

The TensorOpera:registered: team has released public data on deploying pre-trained models like LLaMA-2 13B or LLaMA-3 7B parameters on the RTX4090. Notably, LLaMA-2 13B inference running on a single RTX4090 using TensorOpera’s ScaleLLM achieves 1.88 times lower latency compared to the same model running on a single A100 GPU using vLLM. For the LLaMA-3 7B, it can run with a token batch size of 256 on a single RTX4090, without additional memory optimization [23](/inferix-whitepaper/references.md#23).

In their introduction to ScaleLLM, the TensorOpera:registered: team claims that by utilizing this engine with the RTX4090, LLMs can operate with three times less memory, run 1.8 times faster, and be 20 times more cost-effective compared to using A100 GPUs in traditional data centers.

Research and experimental benchmarks have shown that we can _train larger LLMs on a larger number of distributed GPUs than in data centers with federated learning_, using Gradient Low-rank Projection (GaLore)[23](/inferix-whitepaper/references.md#23), [24](/inferix-whitepaper/references.md#24).