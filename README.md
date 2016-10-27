# pointcloud-loader
[under construction]

a file loader for tab separated location data text files: parsing each column to a Float32 array, find the minimum, maximum, and mean value. Then create a strided array that can be used for texture data that contains vertex data for a point cloud. The heavy lifting for the parser happens async in a Web Worker, and the strided arrays come in chunks of an adjustable length. The location data is stored in the float32 rgba values of a texture of 512 * 512 = 256K vertices. Ready to load from PNG I'd say. For now it rerenders all points on every animation frame, which is quite a waste. The 2.5 million samples from the reference dataset make ten chunks. Not so many draw calls after all and perhaps one texture should be renderable within the brief time of an acceptable animation frame even on a smartphone. No throttling activated yet so it might be a little bit much for some low end hardware.
