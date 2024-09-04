# Price simulation

Now, we will build a price simulation for Inferix's GPU rendering service and compare Inferix's price competitiveness with traditional Cloud Rendering services. The details of these calculations are listed in appendix~\labelcref{sec:price_simulation_details}. The table in~\cref{fig:pricing_simulation} shows the most important information.

\begin{figure}[h]
    % \captionsetup{name=Table}
    \centering
    \includegraphics[width=\linewidth]{pricing-simulation.pdf}
    \caption{Pricing simulation}
    \label{fig:pricing_simulation}
\end{figure}

In this simulation, the calculations are standardized for a single GPU device. The _Provider Price_ refers to the minimum service price that a GPU Provider will set to ensure that revenue is always twice the cost per hour of operation.

In the best-case scenario, where GPUs receive enough tasks to operate full-time every day, providers can break even in no more than $$17$$ months for the RTX$3060$, RTX$3070$, and RTX$3080$ models, and $24$ months for the RTX$3090$ and RTX$4090$ models. However, since the RTX$3090$ and RTX$4090$ models are better suited for federated AI tasks, their IBME scores may be higher. Moreover, the choice of which GPU model to use for rendering also depends on whether the customer prioritizes shortening the rendering time or prefers a more reasonable price. Therefore, the decision on which device to invest in depends on the specific conditions of each individual in particular market conditions.

A crucial point to note here is that with the proposed \emph{Provider Price}, Inferix’s service price is the equivalent of only from $12\%$ to $38\%$ of the average price in the traditional cloud rendering market at the time of writing this paper~\cite{RenderFarm2024,RebusFarm2024,FoxRenderfarm2024}. This means that providers can adjust the price higher to shorten the payback period.

_*Price of 1 IBM*_: Based on the calculation method for IBM discussed in~\cref{subsec:inferix_bench_ibme}, the price of $$1$$ IBM is approximately 0.16$ according to this pricing simulation.