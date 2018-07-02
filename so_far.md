## Common terms: ##

- **Image** is defined as a two-dimensional functin f(x,y) where x and y are spatial (plane) coordinates and the amplitude of f at any pair of coordinates (x,y) is called the 
intensity/gray level of the image at that point. 

- **Frame buffer** is a portion of RAM containing a bitmap that drives a video display. It is a memory buffer containing a complete frame of data.

- **Bitmap** is a mapping from some domain (for example, a range of integers) to bits. When the domain is a rectangle (indexed by two coordinates) a bitmap gives a way to store 
a binary image, that is, an image in which each pixel is either black or white (or any two colors).

- **Pix map** refers to a map of pixels, where each one may store more than two colors, thus using more than one bit per pixel.

- **Pixel** is the smallest controllable element of a picture represented on the screen.

- **Sampling** is the process of recording an analog signal at regular discrete moments of time. (Digitization of space/time)

- **Quantization** is digitization of amplitude/intensity.

- In **pixel resolution**, the term resolution refers to the total number of count of pixels in an digital image. Eg: If an image has M rows and N columns, 
then its resolution can be defined as M X N.

- **MegaPixels** of camera = Column pixels (width ) X row pixels ( height ) / 1 Million.

- **Spatial resolution** can be defined as the smallest discernible detail in an image. Or in other way we can define spatial resolution as the number of independent pixels values per inch.

- The **grey level** / **grey value** indicates the brightness of a pixel. The minimum grey level is 0. The maximum grey level depends on the digitization depth of the image. 
Eg: For an 8-bit-deep image it is 255 (2^8). In a binary image a pixel can only take on either the value 0 or the value 255.

- **Color depth** / **bit depth** is either the number of bits used to indicate the color of a single pixel, in a bitmapped image or video frame buffer, 
or the number of bits used for each color component of a single pixel.

- **Sampling theorem**: For every complex signal with an f_max as its highest frequency sine component, atleast 2*f_max samples per second are required for a proper lossless reconstruction.

- **Fourier transform** is the frequency domain representation of signals. Any arbitrary signal can be expressed as a sum of sinusoids. 

- **Mask/kernel/template/window** is a 2D matrix whose values define the nature of process of image transformation.

- **Fourier transform** is the frequency domain representation of signals. Any arbitrary signal can be expressed as a sum of sinusoids. 
- **Mask/kernel/template/window** is a 2D matrix whose values define the nature of process.

- **Radiance** is the total amount of energy that flows from the light source.

- **Luminance**  is the measure of the amount of energy an observer perceives from a light source. 



## Types of noise ##

**1. Aliasing**

Occurs when reconstructed image varies from the original image if sampling theorem is not satisfied. Types are spatial and temporal.
Common names for spatial (moire patterns, jaggies) and temporal (strobing, wagon wheel effect).

Spatial aliasing is due to limited spatial resolution.

Spatial resolution is the ability of an image forming device to distinguish small details of an object. 
 
Temporal aliasing is due to limited temporal resolution.

Temporal resolution is the precision of measurement w.r.t time. 

Resolution is the minimum distance between distinguishable objects in an image.

*Further reference:* 

Ball example for aliasing: http://www.physlink.com/education/askexperts/ae490.cfm

Picture example for aliasing: https://en.wikipedia.org/wiki/Aliasing

To eliminate spatial filtering: Use a low pass filter so that sampling theorem is satisfied, blending

## Image Enhancements ##

Enhancements can be in spatial domain (where we directly manipulate the pixel values) or in the frequency domain (modification of its FT).

###Enhancements in the spatial domain###


A. Basic grey level transformations:

1.	Image Negatives: Used when we want to enhance white/gray detail in an image which is predominantly dark
2.	Log transformations: Mainly used to compress the dynamic range of images with large variations in pixel values. It expands the values of dark pixels in an image while compressing the higher level values. 
3.	Gamma correction [Power function]
4.	Piece-wise linear transformation functions.

    a.	Contrast stretching [Thresholding]

    b.	Gray-level slicing [Give high value of gray level to region of interest. You may/may not background]

    c.	Bit-plane slicing [Separating the contribution to the total image by specific bits]

B. Histogram processing

1. Histogram equalization

2. Histogram matching

C. Local enhancement: Same as above two but on a local pixel to pixel window basis. [Grey squares example]

D. Arithmetic/Logic operators [AND/OR are used for masking, subtraction for masking, averaging for Gaussian noise reduction]

E. Spatial Filtering

   1. Smoothening filters
  
    a. [average filter]

    b. Order statistics filter [Median filters, best for salt and pepper noise]

   2. Sharpening filters 

    a. [Laplacian transform, 2nd order derivative, highlights fine details]

    b. Unsharp masking and high boost filtering. 

    c. Gradient [sobel masks]

###Enhancements in the frequency domain###

- Fourier transform. Expressing an analog signal as a sum of sins and cosine waves.

- Sine frequency is related to rate of change [intensities]

- Notch filter: Forces the average value of image to 0.
 
- Convolution concept. 

- Ideal low pass filter has ringing problems

- Butterworth filter: depends on the order
 
- Gaussian low pass filter

- Same as above three categories for high pass

- Homomorphic filtering [used to remove multiplicative noise, used for correcting non-uniform illuminated images]

##Image enhancements##

Types of noise depending on models

- White noise: Has equal intensity at all at different frequencies.

- Gaussian noise

- Rayleigh noise

- Gamma noise

- Exponential noise

- Uniform noise

- Impulse (salt & pepper) noise

- Periodic noise

Few filter types in spatial domain:

- Arithmetic mean filter: noise reduced as a result of blurring.

- Geometric mean filter: smoothing but image details are lost

- Harmonic mean filter: good for salt noise, bad for pepper noise

- Contraharmonic filter: good for salt and pepper

- Median filter

- Max and min filter (max good for pepper noise, min makes white objects smaller and dark objects bigger)

- Midpoint filter

- Alpha trimmed mean filter: good for combination of salt and pepper and gaussian noise

- Adaptive local noise reduction filter

- Adaptive median filter

Few filter types in frequency domain:

- Band reject filter: better for additive periodic noise

- Band pass filter: helps in isolating the noise pattern

- Notch filter

- Weiner filter: very nice as long as an estimate of degradation function is known
