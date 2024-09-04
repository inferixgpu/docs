# Worker node

It is where the actual rendering takes place. Each Worker Node is equipped with a tool called the Render Engine Controller, along with one or several render software or render engines, such as Blender Cycles, V-Ray, Keyshot, D5 Render, Octane, etc. See\cref{fig:rendering_service} for more details.

The render engines utilized by Worker Nodes typically rely on path-tracing/ray-tracing techniques, which demand substantial compute resources. Some of these engines are open-source and free, such as Cycles, while others, like V-Ray, are paid software. If there are any render engine costs, they will be factored into the rendering price that the Inferix network charges users.

\subsection{Decentralized Storage and Data Security}
Data storage and security are critical for Inferix users. The data for a 3D scene typically ranges from a few dozen MBs to several GBs, while AI model data can reach up to several TBs. Managing this data requires specialized methods.