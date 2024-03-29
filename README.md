# Calculation of the surface area of a sphere for each pixel

## Overview

This project aims to provide a method for accurately calculating the surface area of the Sun's disk from 2D solar disk images. The 2D representation of the solar surface introduces projection effects, where the weights of pixels vary depending on their proximity to the limb or the center of the Sun. To overcome this limitation, we present a technique to obtain spherical projections of the pixels, enabling precise area calculations for each pixel.

## Method

A detailed description of the area calculation method can be found in the research paper ([Chikunova et al. 2023](https://doi.org/10.1051/0004-6361/202347011))

*G. Chikunova, T. Podladchokova, K. Dissauer, A.M. Veronig, M. Dumbovic, M. Temmer, E. Dickson, 2023: "Three-dimensional relation between coronal dimming, filament eruption, and CME. A case study of the 28 October 2021 X1.0 event"*. 

We recommend referring to this paper for a comprehensive understanding of the methodology.

## Code repository
The code can be accessed in the following Python notebook:
 [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Chigaga/area_calculation/blob/main/area_calculation.ipynb)
 
The notebook provides functions necessary for the area calculation process and examples of their implementation. 

We used [Sunpy](https://docs.sunpy.org/en/stable/) open-source software package to access and process the solar images. We also thank Shantanu Jain for his helpful suggestions for the code development.

### Functions:
- `calculate_pixel_area`
Calculates the area of a single pixel based on its spherical projection. It takes into account the pixel's position in the solar map.  The function returns the calculated area value.
```
pixel_area = calculate_pixel_area(pixel_coords,smap)
```
- `calculate_region_area`
Calculates the total area of a specified region on the solar disk. It takes the list of regions' coordinates as input and iterates over the pixels within the region to calculate their individual areas. The function returns the total area of the chosen region. This function can be adapted to the region of any shape.
```
region_area = calculate_region_area(xlim, ylim, smap)
```
- `create_area_map`
Generates an area correction map for the entire solar disk image. It applies the "calculate_pixel_area" function to each pixel in the image, resulting in a map where each pixel value represents its corresponding area in km2. The function returns the area map as a SunpyMap object.
```
area_map = create_area_map(smap)
```

## Acknowledging and usage

If you use or reference the work presented in this repository, please cite the following paper:

> Chikunova, G., Podladchikova, T., Dissauer, K., Veronig, A. M., Dumbović, M., Temmer, M., & Dickson, E. C. M. (2023). Three-dimensional relation between coronal dimming, filament eruption, and CME - A case study of the 28 October 2021 X1.0 event. *Astronomy & Astrophysics*, 678, A166. DOI: [10.1051/0004-6361/202347011](https://doi.org/10.1051/0004-6361/202347011)

## License
License: This function is released under the Apache License. You can find the license file in the root directory of the GitHub repository. 

## Contact
For any further assistance or inquiries, please don't hesitate to reach out!

*Galina Chikunova*
galina.chikunova@skoltech.ru

## Contributors
* Galina Chikunova
* Tatiana Podladchikova
* Shantanu Jain

