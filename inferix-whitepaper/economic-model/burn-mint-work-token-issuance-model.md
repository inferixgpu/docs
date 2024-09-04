# Burn-Mint-Work token issuance model

Increasing the \emph{token velocity} and controlling inflation are critical issues for any utility token. Various issuance models for utility tokens have been proposed, but fundamentally in DePIN projects, there are two commonly used methods: \emph{Work Token} and \emph{Burn-Mint-Equilibrium} (BME). While the Work Token (used by Filecoin project) has the advantage of improving \emph{token velocity}, it requires the provided service to be purely a commodity, with no manual human intervention. On the other hand, BME (used by famous projects like Helium and Factom~\cite{Helium2018,Factom2018}) lacks control over the volume of verified work completed and the ability to adequately penalize substandard service providers~\cite{Samani2018}.

Inferix's BMW (Burn-Mint-Work) is the token issuance mechanism designed to address the creation of tokens based on the amount of work completed and a Node's working capacity. When BMW is combined with the IBME mechanism (c.f.~\cref{subsec:inferix_bench_ibme}), it also helps solve the inflation control issue within the Inferix system, allowing \$IFX tokens to be minted flexibly based on the total volume of work completed and the total amount of money users pay for services across the Inferix network.

Inferix's BMW is an improvement on the BME algorithm, with the important parameter being "work" calculated based on the PoR algorithm. While BME (Burn and Mint Equilibrium) balances only two parameters, burn and mint, BMW balances three parameters: burn, mint, and work. BMW also incorporates penalty mechanisms for substandard providers from the Work Token model.

When Inferix completes a graphics rendering or federated AI task $t$ for a customer, by the Provider A, the network charges a service fee calculated as follows:

$$
    \mathcal{F}\left(t\right) \triangleq W_{t} \times \mathcal{P}_{A}
$$

where $$W_t$$ is the amount of work completed for $$t$$ measured in IBM (c.f.~\cref{subsec:governance}), and $$\mathcal{P}\left(A\right)$$ is the unit price for one IBM, which can be adjusted by Provider A. The Matcher algorithm on the Manager Node automatically searches and provides the best options for both the user and the provider.

To order services, users must top up a prepaid account with Inferix's internal payment token, called \emph{ifxDollar}, at an exchange rate of $\SI[]{1}{USD} = \SI[]{1}{ifxDollar}$ at the time of the top-up.
    
After completing a rendering job, $80\%$ of the service fee is used to purchase an amount of \$IFX tokens from available supply sources (e.g., DEX/CEX exchanges). This amount of \$IFX tokens is then burned. Next, $20\%$ of the service fee will be retained and managed by the Inferix Foundation, these funds will be used to reward developers who contribute to the Inferix ecosystem.
    
The issuance of new tokens on Inferix is executed after each \emph{epoch period}, initially set at $72$ hours but later adjustable through DAO governance. Suppose after an epoch period $p$, the total amount of work completed across the network is $W_p$. In that case, the system will issue a quantity of tokens according to the following formula:

$$
    \mathcal{T} \triangleq W_p \times E_p
$$

where $E_p$ is a parameter taken from the Emission Plan, which is planned by Inferix Governance and periodically adjusted by monitoring the IBME ratio (c.f.~\cref{subsec:governance}).
    
The newly issued \$IFX tokens are allocated to stakeholders in the network as detailed in~\cref{subsec:token_metrics_and_allocation}. This token issuance process must be entirely independent of the token burn process to generate \emph{ifxDollar} mentioned above. When service demand increases, more \$IFX tokens are burned, leading to a decrease in the total supply of \$IFX, which puts upward pressure on the price of \$IFX tokens. This price increase results in fewer tokens needing to be burned to complete the same amount of work, thereby bringing the system back into equilibrium. An increase in the price of \$IFX tokens also increases the profitability of providers, attracting more providers joining and increasing supply. When service demand decreases, the opposite scenario occurs, leading to a state of equilibrium.