# Worker Rewards

Worker rewards are composed of two parts: PoC rewards and PoD rewards.

### PoC: Proof of Capacity

Proof of Capacity (PoC) is a blockchain consensus algorithm that allows mining devices in the network to utilize their available computational power to determine mining rights and validate transactions. PoC rewards are designed to encourage participants to keep their computational resources (containers) online and available, even when not actively processing tasks. This ensures a consistent and reliable resource pool for the network. Any container that remains online and meets the network's uptime requirements is eligible for PoC rewards.

* PoC incentivizes GPUs to remain **online and available** even when not actively performing tasks.&#x20;
* The calculation is based on the **Inferix Bench of the GPU** and **its uptime**
* The longer the GPU remains online, the higher the PoC reward.
* PoC Formula:&#x20;

### &#x20;            **PoC Reward = InferixBench x UpTime**

### PoD: Proof of Delivery

Proof of Delivery (PoD) verifies that mining devices in the network are genuine and have been successfully rented by third parties, earning additional rewards. PoD rewards incentivize participants to actively contribute computational power for rendering tasks and deliver high- quality results. These rewards are granted to participants who successfully complete rendering tasks.

* PoD applies when **GPU resources are actively rented** and computational tasks are successfully completed.&#x20;
* The calculation is based on **lease duration (Lease Time)**
* PoD rewards are only granted after the completion of the computational task.
* PoD Formula:

### &#x20;            PoD Reward = InferixBench x LeaseTime

***

## Worker Reward Calculation

The total reward pool is determined based on overall network utilization and activity. Individual rewards are calculated proportionally, considering factors such as the container's Inferix Bench (reflecting performance and capabilities) and its uptime.

To compute the total daily earnings of a GPU, PoC and PoD rewards are aggregated with a weighting factor applied to PoD rewards:

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-13 at 22.06.18.png" alt=""><figcaption></figcaption></figure>

### PoC Rewards Calculation:

* Single GPU PoC Weight Formula

### &#x20;        Single GPU PoC Weight = InferixBench x UpTime

* Single GPU PoC Revenue Formula

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-13 at 22.09.11.png" alt=""><figcaption></figcaption></figure>

### PoD Rewards Calculation:

* Single GPU PoD Weight Formula

### &#x20;  Single GPU PoD Weight = InferixBench x LeaseTime

* Single GPU PoD Revenue Formula

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-13 at 22.11.34.png" alt=""><figcaption></figcaption></figure>

\***InferixBench** : GPU performance weight
