# IB and IBM

Based on PoR, Inferix can assess the computing power of a Worker Node at a given time and uses a measurement unit called _Inferix Bench_ (IB). When IB is multiplied by the node's working time, it results in _Inferix Bench minutes_, abbreviated as IBM. Thus, IBM is the metric used to measure the workload within the Inferix network.
    
To provide a quantitative perspective, 1 IB is defined as the average rendering capacity of a _standard unit node_ with 2x RTX4090 GPUs, 32 GB of RAM, 1x Intel Core i9 CPU, SSD storage. This figure is updated daily using DAO mechanism, using benchmarks of a set of sample scenes on 10 nodes. The hardware specification of _standard unit nodes_ and the _sample scenes_ are also DAO-adjustable.

Assuming the average rendering time for one frame of a scene $$G$$ in the sample set is $$T^{0}_{G}$$, then it is not a fixed number, but is instead derived from the combined rendering capacity of the $$10$$ randomly selected _standard unit nodes_ at the benchmarking time. The value of $$T^{0}_{G}$$ is influenced by GPU, CPU, storage read/write speeds and network speeds at the time of benchmarking, though the variation is negligible.

To determine the IB of any given node $$n$$, Inferix sends render requests for scene $$G$$ (randomly selected) to that node periodically. Assuming the average time it takes that node to render one frame in $$G$$ is $$T_G$$, the rendering power of $$n$$ is defined by:

$$
\text{IB}\left(n\right) \triangleq \frac{T^{0}_{G}}{T_G}
$$

Thus, the larger the $$T_G$$, the smaller the $$\text{IB}_n$$ value.