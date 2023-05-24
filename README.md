# Correction of the solar disk images for the area calculation: obtaining sphereical projections of the pixels

# Overview

This project aims to provide a method for accurately calculating the surface area of the Sun's disk from 2D solar disk images. The 2D representation of the solar surface introduces projection effects, where the weights of pixels vary depending on their proximity to the limb or the center of the Sun. To overcome this limitation, we present a technique to obtain spherical projections of the pixels, enabling precise area calculations for each pixel.

# Method

A detailed description of the area calculation method can be found in the research paper titled "On the three-dimensional relation between the coronal dimming,
erupting filament and CME: Case study of the 28 October 2021 X1.0 event" by Chikunova et al. (2023). We recommend referring to this paper for a comprehensive understanding of the methodology.

# Code repository
The code can be accessed in the following Python notebook:
 [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Chigaga/area_calculation/blob/main/area_calculation.ipynb)
 
The notebook provides the implementation of various functions necessary for the area calculation process.

## Functions:
- `calculate_pixel_area`
Calculates the area of a single pixel based on its spherical projection. It takes into account the pixel's position in the solar map.  The function returns the calculated area value.
```
pixel_area = calculate_pixel_area(pixel_coords,smap)
```
- `calculate_region_area`
Calculates the total area of a specified rectangle region on the solar disk. It takes the region's boundaries as input and iterates over the pixels within the region to calculate their individual areas. The function returns the total area of the chosen region. This function can be adapted to the region of any shape.
```
region_area = calculate_region_area(xlim, ylim, smap)
```
- `create_area_map`
Generates an area correction map for the entire solar disk image. It applies the "calculate_pixel_area" function to each pixel in the image, resulting in a map where each pixel value represents its corresponding area in km2. The function returns the area map as a 2D array.
```
area_map = create_area_map(smap)
```


# Contact
For any further assistance or inquiries, please don't hesitate to reach out!

*Galina Chikunova*
galina.chikunova@skoltech.ru
