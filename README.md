### Objective:
The goal of this project is to efficiently process, store, and analyze high-resolution images (100,000x100,000 pixels) of parasitic microorganisms captured by an electron microscope and a dye sensor. The objective is to identify and store images of cancerous parasites by quantifying the presence of luminescent dye within their bodies

#### Synthetic Data Generation:
- electron microscope images were generated using a Random Ellipse Overlay algorithm: a random ellipse is generated (with random axis lengths and angle of rotation). The center of the ellipse is computed by adding noise to the center of the image. This iteratively takes place until we reach the desired parasite area. This overlaying of random ellipses mimics the parasite's body
- dye sensor images were generated using random walk and fluid flow simulation: The process starts by identifying a random point of injection within the parasite. The dye then spreads using a modified version of the random walk algorithm that mimics blood vessel flow and fluid continuity

#### Image compression:
 To save storage space, the images are compressed using Run-Length Encoding (RLE). The bounding box of the parasite or dyed area is computed, and consecutive runs of pixels are encoded. 

#### Cancer detection (proxy):
The overlapping bounding box of the parasite and dye images is computed. By analyzing the overlapping pixels within this bounding box, the percentage of dye coverage is calculated. If the dye coverage exceeds 10% of the parasite's area, the parasite is classified as cancerous.
 
