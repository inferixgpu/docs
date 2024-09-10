# Data security with FHE and TEE

Data stored within the Inferix network is categorized into two types:
 * _Session data_ which includes input data along with temporary data generated during the rendering process. This data typically exists for a short duration, ranging from a few minutes to several hours.
 * _Persistent data_ which consists of the output from the rendering process and is stored long-term in the system. Examples of persistent data include images and videos after rendering, or VR scenes created after lightmap baking.

Inferix encrypts session data to ensure it remains secure against decryption attacks during data transfer. For persistent data, Inferix offers long-term hosting on its storage system and allows users to share the data publicly or with specific permissions over the Internet.

Our surveys show that, on average, over 80\% of 3D model data from graphic artists are public data shared on the internet, while nearly 20\% are their original creations and need to be protected. Therefore, Inferix will offer data security level options for end-users to choose from. Higher security level options will incur additional costs for computing resources, storage, and bandwidth, which will be added to the service fees that the end-user must pay.

There are three components related to data security in the Inferix network: the Manager, Worker and Verifier. We will present a security approach for each of these components below.