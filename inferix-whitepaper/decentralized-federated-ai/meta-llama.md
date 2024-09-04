# Meta LLaMA

In its GPU hardware segment, Inferix focuses on devices optimized for graphics rendering, with the RTX\num{3090} and RTX\num{4090} serving as the flagship devices.

The TensorOpera\textsuperscript{\textregistered} team has released public data on deploying pre-trained models like LLaMA-2\,13B or LLaMA-3\,7B parameters on the RTX\num{4090}. Notably, LLaMA-2\,13B inference running on a single RTX\num{4090} using TensorOpera’s ScaleLLM achieves $$1.88$$ times lower latency compared to the same model running on a single A\num{100}\,GPU using vLLM. For the LLaMA-3\,7B, it can run with a token batch size of $$256$$ on a single RTX\num{4090}, without additional memory optimization~\cite{TensorOperaScaleLLMLlama213B2023}.

In their introduction to ScaleLLM, the TensorOpera\textsuperscript{\textregistered} team claims that by utilizing this engine with the RTX\num{4090}, LLMs can operate with three times less memory, run $1.8$ times faster, and be $$20$$ times more cost-effective compared to using A100 GPUs in traditional data centers.

Research and experimental benchmarks have shown that we can \emph{train larger LLMs on a larger number of distributed GPUs than in data centers with federated learning}, using Gradient Low-rank Projection (GaLore)~\cite{TensorOperaScaleLLMLlama213B2023,TensorOperaScaleScaleLLMServerless2022}.