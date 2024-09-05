# Attacks on verification keys

As discussed in the [verification key generation](/inferix-whitepaper/implementation/verification-key-generation.md), colluding attackers may know a set of used keys, then use these keys to predict the next keys (this is called _random number generator attack_ [[20]](/inferix-whitepaper/references.md#20)). Furthermore, a large enough set of _workers_ may also temporarily saturate the rendering task assignment mechanism of the _manager_ to control which nodes will be assigned\cite{Lian2007}. These nodes already know the verification keys used for the assigned tasks, then they generate straightforwardly forged images which validate the noise verification. In short, once the verification key generation is predictable, the noise verification will be compromised.

This attack is mitigated due the [cryptographic hash property](/inferix-whitepaper/implementation/verification-key-generation.md) of $$K_{\mathtt{verif}}$$: knowledge about generated keys does not leak any information about the next keys.

