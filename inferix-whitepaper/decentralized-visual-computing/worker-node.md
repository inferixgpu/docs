# Worker node

It is where the actual rendering takes place. Each Worker Node is equipped with a tool called the Render Engine Controller, along with one or several render software or render engines, such as Blender Cycles, V-Ray, Keyshot, D5 Render, Octane, etc. See the [rendering flow](/inferix-whitepaper/introduction/rendering-network-using-crowdsourced-gpu.md##fig_rendering_flow) for more details.

The render engines utilized by Worker Nodes typically rely on path-tracing/ray-tracing techniques, which demand substantial compute resources. Some of these engines are open-source and free, such as Cycles, while others, like V-Ray, are paid software. If there are any render engine costs, they will be factored into the rendering price that the Inferix network charges users.