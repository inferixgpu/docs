# Geometric constraints

By the nature of physically based rendering\cite{Hughes2014}, an object (or any part of it) in the scene will not be visible if and only if there is no visible light (or in general the light is out of the capability of the sensor) scattered from the surface of the object to the digital camera object. This may be caused by several reasons: the object is not located in the frustum of the camera, is hidden by other objects, or the object is made of some transparent material. Furthermore, the atomic signals $$w_i \ \left(1 \leq i \leq n\right)$$ should not interfere themselves since this makes the noise verification to be unnecessarily complicated. Consequently, we require the noise embedding to satisfy first the following constraints:

 * there are no collisions between $$\omega_i \ \left(1 \leq i \leq n\right)$$,
 * object vector $$\Omega$$ is completely located in the camera frustum,
 * no $$\omega_i$$ is hidden by another object (even partially), including both $$\omega_j \in \Omega, \ j \neq i$$ and objects of the scene.

As mentioned in\cref{subsec:structure_of_noise}, the characteristics of atomic noises in frequency domain are crucial for the robustness of noise verification: we need to restore a certain amount of information about these characteristics from very small distortions made by the objects $$\omega_i \in \Omega$$ on rendered images. Because of the unavoidable requirement about the fidelity of images, we have to keep these distortions local, concretely these distortions must be well-placed on regions whose locations can be pre-calculated. A practical approach is to constrain the distortion made by $\omega_i$ to be of the same shape as the atomic noise $$w_i$$. Geometrically, each $$\omega_i$$ has a \emph{rotation vector} which characterizes the direction of the object in the global coordinate system (i.e. world space~\cite{Hughes2014}) containing all objects of the scene $G$. To keep the rectangular shape of the distortion of $$\omega_i$$, we require that:

 * the rotation vector of $\omega_i$ is equal with the rotation vector of the digital camera of $G$ for all $\omega_i \in \Omega$.
