# Data categories

3D data stored in the Inferix system includes:
 * Geometry data of 3D models, characterized by polygons that form the shape of objects. Depending on the render engine, different formats may be used. The higher the number of polygons, the more detailed the rendering result will be; however, the render time will also increase, and more storage space will be required.
 * Texture data, which is the surface image of the object. Inferix uses data formats with the best compression algorithms for GPUs, such as Basis and KTX, alongside common formats like JPEG, PNG, TIFF, or WebP.
 * Rendered results in image format
 * Rendered results in video format
 * Structural data in JSON format