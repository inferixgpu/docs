# Worker

Workers are the most critical component of the Inferix network. The reward pool for Worker Nodes constitutes $$75\%$$ of the Ecosystem Fund and is distributed through the BMW model. In other words, three-quarters of the $$80\%$$ of the network's service revenue is allocated to Workers.
    
To receive BMW rewards, each Worker must hold an amount of \$IFX tokens at any given time. This token amount acts as a penalty fund in case the Worker fails to meet Inferix's standards. The minimum stake amount of node $$n$$ can be calculated as follows:
$$
    S\left(n\right) \triangleq 2 \times \mathcal{E} \times \text{IB} \left(n\right) \times P\left(n\right)
$$
where $$\text{IB}\left(n\right)$$ is the benchmark value of the node (c.f.~\cref{equ:inferix_bench}), $$P\left(n\right)$$ is the price per IBM defined by the node provider himself and $$\mathcal{E}$$ is a constant defined by number of minutes of the Epoch period, that is $$72 \times 60 = 4320$$.

For example, if a provider owns a node with 32 GB RAM, Intel\textregistered Core\texttrademark i9 CPU, and an RTX\num{4090} card, its computing power will be approximately \SI[]{0.5}{IB}. To participate in the Inferix network at a service price of \SI[]{2}[\$]{} per hour, it is needed to hold a quantity of \$IFX tokens equivalent to $0.5 \times 2 \times 4320 \div 60$ = \SI[]{72}{USD}.

_Inferix Edge:_ computers are specially designed to participate in the Inferix worker network. These machines are streamlined by removing non-essential components and focusing on enhancing the CPU, GPU, RAM, and motherboard to optimize performance for Visual Computing and federated AI tasks.
