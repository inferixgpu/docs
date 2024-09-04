# Integration

We integrate the Active Noise Generation and Verification scheme into the original rendering flow (c.f.\cref{fig:rendering\_service}) by placing respectively the noise generation and the noise verification into the rendering task controller of the \emph{manager} and the proof-of-rendering verification of the \emph{verifier}. The completed flow is depicted in\cref{fig:rendering\_flow\_with\_angv}.

<figure><img src="../../.gitbook/assets/rendering-service-with-angv.svg" alt=""><figcaption><p>aa</p></figcaption></figure>

In the introductory section of the paper, we have discussed the problem of rendering verification, that is to automatically verify whether the submitted scenes of users are genuinely rendered or not. The ANGV is proposed to deal with the challenge, ANGV serves then as a \emph{proof of rendering} (PoR), inspired from the \emph{proof of ownership} schemes\cite{Wu1998,Yeung1997}. Other components of the Inferix network simply refers PoR for the underlying ANGV algorithm.
