
# Image Processing with scikit-image

This repository contains a Python script that demonstrates fundamental image processing techniques using the `scikit-image` library. The script covers a wide range of topics, including image visualization, color manipulation, filtering, transformations, and restoration.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
  - [Loading and Visualizing Images](#loading-and-visualizing-images)
  - [Color Manipulation](#color-manipulation)
  - [Image Flipping](#image-flipping)
  - [Histograms and Thresholding](#histograms-and-thresholding)
  - [Edge Detection and Smoothing](#edge-detection-and-smoothing)
  - [Image Rescaling and Resizing](#image-rescaling-and-resizing)
  - [Image Restoration and Noise Reduction](#image-restoration-and-noise-reduction)
  - [Segmentation](#segmentation)
  - [Contour Detection](#contour-detection)
- [License](#license)

## Installation

To run the script, you need to have Python installed along with the following libraries:

- `scikit-image`
- `matplotlib`
- `numpy`

You can install the required libraries using pip:

```bash
pip install --upgrade scikit-image matplotlib numpy
```

## Usage

To run the script, use the following command:

```bash
python image_processing.py
```

The script will display various image processing techniques applied to a sample image. You can replace the sample image with your own by modifying the corresponding line in the script.

## Features

### Loading and Visualizing Images

The script starts by loading an example image using `scikit-image` and displays its dimensions:

```python
from skimage import data
rocket_image = data.rocket()
```

### Color Manipulation

The script demonstrates how to convert an image from RGB to grayscale and back:

```python
from skimage import color
grayscale = color.rgb2gray(rocket_image)
rgb = color.gray2rgb(grayscale)
```

### Image Flipping

You can flip images both vertically and horizontally using `numpy`:

```python
import numpy as np
vertically_flipped = np.flipud(image)
horizontally_flipped = np.fliplr(image)
```

### Histograms and Thresholding

The script shows how to generate histograms for different color channels and apply thresholding to partition an image into foreground and background:

```python
plt.hist(red.ravel(), bins=256)
from skimage.color import rgb2gray
gray_image = rgb2gray(image)
binary = gray_image > 127
```

### Edge Detection and Smoothing

Edge detection is performed using the Sobel operator, and Gaussian smoothing is applied to reduce noise:

```python
from skimage.filters import sobel, gaussian
edge_sobel = sobel(image)
gaussian_image = gaussian(image, channel_axis=-1)
```

### Image Rescaling and Resizing

The script includes examples of rescaling and resizing images:

```python
from skimage.transform import rescale, resize
rescaled_image = rescale(image, 1/4, anti_aliasing=True, channel_axis=-1)
resized_image = resize(image, (400, 500), anti_aliasing=True)
```

### Image Restoration and Noise Reduction

The script demonstrates image restoration using inpainting techniques and noise reduction using various filters:

```python
from skimage.restoration import inpaint, denoise_tv_chambolle, denoise_bilateral
restored_image = inpaint.inpaint_biharmonic(image, mask, channel_axis=-1)
denoised_image = denoise_tv_chambolle(noisy_image, weight=0.1, channel_axis=-1)
```

### Segmentation

Segmentation techniques such as SLIC (Simple Linear Iterative Clustering) are used to divide the image into segments:

```python
from skimage.segmentation import slic
segments = slic(image, n_segments=100)
```

### Contour Detection

The script also includes contour detection to find boundaries within the image:

```python
from skimage import measure
contours = measure.find_contours(threshold_image, 0.8)
```


