# Data security with FHE and TEE

Data stored within the Inferix network is categorized into two types:
 * _Session data_ which includes input data along with temporary data generated during the rendering process. This data typically exists for a short duration, ranging from a few minutes to several hours.
 * _Persistent data_ which consists of the output from the rendering process and is stored long-term in the system. Examples of persistent data include images and videos after rendering, or VR scenes created after lightmap baking.

Inferix encrypts session data to ensure it remains secure against decryption attacks during data transfer. For persistent data, Inferix offers long-term hosting on its storage system and allows users to share the data publicly or with specific permissions over the Internet.