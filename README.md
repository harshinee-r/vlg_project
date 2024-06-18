# Low Light Image Enhancement using Python

## Architecture

### 1. Image Enhancement Function:

- Converts the image from BGR to HSV colour space.
- Normalizes the V (brightness) channel.
- Applies decomposition to separate illumination and reflectance components.
- Adjusts illumination.
- Reconstructs the enhanced V channel.
- Converts the image back to BGR colour space.

### 2. PSNR Calculation Function:

- Calculates the Peak Signal-to-Noise Ratio (PSNR) between the original and enhanced images to evaluate the enhancement quality.

### 3. Main Processing Loop:

- Loads images from the specified directory.
- Applies the enhancement algorithm to each image.
- Saves the enhanced images.
- Calculates and records the PSNR for each image.
- Displays a progress bar and status updates.

## Algorithm and Approach

### Algorithm

- _Conversion to HSV:_ The image is converted from BGR to HSV color space, where the V (value or brightness) channel can be independently manipulated.
- _Normalization of V Channel:_ The V channel is normalized to a range of 0 to 1 by dividing by 255.0.
- _Decomposition:_ The normalized V channel is decomposed into illumination (L) and reflectance (R) components.
- _Illumination Adjustment:_ The illumination component (L) is adjusted using normalization to enhance brightness.
- _Enhanced V Channel:_ The enhanced V channel is reconstructed by combining the adjusted illumination (L) and reflectance (R). The resulting enhanced V channel is normalized and converted back to an 8-bit image.
- _Reconstruction:_ The enhanced V channel is merged with the original H and S channels and converted back to BGR colour space.

### Approach

- _Loading Images:_ Images are loaded from the specified directory, and their filenames are filtered to include common image file formats.
- _Processing and Saving:_ Each image is resized, enhanced using the proposed algorithm, and saved to the specified output directory.
- _PSNR Calculation:_ The PSNR value for each image is calculated to measure the enhancement quality.
- _Progress Tracking:_ A progress bar is displayed to provide feedback on the processing status, including the percentage of images processed.

### Results

- The enhancement algorithm improves the visual quality of low-light images by adjusting illumination and preserving details.
- The PSNR values provide a quantitative measure of the enhancement quality, indicating the degree of similarity between the original and enhanced images.
- We observed that the PSNR values were between 25-30 for many images.
