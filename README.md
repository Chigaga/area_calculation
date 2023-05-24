# Correction of the solar disk images for the area calculation: obtaining sphereical projections of the pixels

# Overview

This project aims to provide a method for accurately calculating the surface area of the Sun's disk from 2D solar disk images. The 2D representation of the solar surface introduces projection effects, where the weights of pixels vary depending on their proximity to the limb or the center of the Sun. To overcome this limitation, we present a technique to obtain spherical projections of the pixels, enabling precise area calculations for each pixel.

# Method

A detailed description of the area calculation method can be found in the research paper titled "On the three-dimensional relation between the coronal dimming,
erupting filament and CME: Case study of the 28 October 2021 X1.0 event" by Chikunova et al. (2023). We recommend referring to this paper for a comprehensive understanding of the methodology.

# Code repository
The code for performing the pixel area correction can be accessed in the following Python notebook:
 [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Chigaga/area_calculation/blob/main/area_calculation.ipynb)
 
The notebook provides the implementation of various functions necessary for the area calculation process.

## Functions:
- **calculate_pixel_area**
This function calculates the area of a single pixel based on its spherical projection. It takes into account the pixel's position in the solar map.  The function returns the calculated area value.

- **calculate_region_area**
Calculates the total area of a specified rectangle region on the solar disk. It takes the region's boundaries as input and iterates over the pixels within the region to calculate their individual areas. The function returns the total area of the chosen region. This function can be adapted to the region of any shape.

- **create_area_map**
- The "create_area_map" function generates an area correction map for the entire solar disk image. It applies the "calculate_pixel_area" function to each pixel in the image, resulting in a map where each pixel value represents its corresponding area in km2. The function returns the area map as a 2D array.

# Usage

To incorporate these functions into your project, follow these steps:
1. Import the necessary functions into your Python script or notebook:
```
from area_calculation import calculate_pixel_area, calculate_region_area, create_area_map
```
2. Use the functions as required in your project. For example, to calculate the area of a specific pixel:
```
pixel_area = calculate_pixel_area(pixel_coords,smap)
```
or to create an area map for a solar disk image:
```
area_map = create_area_map(smap)
```


For any further assistance or inquiries, please don't hesitate to reach out!

# Contact
Galina Chikunova
galina.chikunova@skoltech.ru
