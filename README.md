# Bicubic_image_scaling
Bicubic interpolation is an advanced image scaling technique used to resize images with improved  smoothness and clarity

Bicubic interpolation is an advanced image scaling technique used to resize images with improved 
smoothness and clarity. It works by using the values of the 16 nearest pixels around a target 
location to calculate a new pixel value, ensuring a smoother transition between pixels. This 
method is particularly effective for upscaling images, as it minimizes artifacts and provides sharper 
results compared to simpler methods like nearest-neighbor or bilinear interpolation.

Bicubic Interpolation Algorithm Summary:

### Step 1: Identify Neighboring Pixels

• For a given location in the resized image, identify the corresponding location in the original 
image and its 16 neighboring pixels.

• Formulas:

• src_x = dst_x * (width_original / width_resized)

• src_y = dst_y * (height_original / height_resized)

• Neighbors are identified in a 4x4 grid around the floor values of src_x and src_y.

### Step 2: Calculate Distances

• Calculate the fractional part of the source coordinates to determine the sub-pixel position.

• Formulas:

• frac_x = src_x - floor(src_x)

• frac_y = src_y - floor(src_y)

• Calculate the distances from the sub-pixel position to each of the 16 neighboring pixels.

### Step 3: Determine Weights Using Cubic Convolution

• Apply a cubic convolution kernel to the distances to determine the weights for interpolation.

• Formula:

• f(x) = 

         (a + 2)|x|^3 - (a + 3)|x|^2 + 1 for |x| < 1,  

          a|x|^3 - 5a|x|^2 + 8a|x| - 4a for 1 ≤ |x| < 2,
         
          0 otherwise,

• Where a is typically set to -0.5.

### Step 4: Compute the Interpolated Value

• Use the weights to compute a weighted sum of the pixel values from the original image.

• Formula:

• Interpolated Value = Σ (Pixel Value_i * Weight_i) from i=1 to 16

• Normalize the interpolated value if necessary.

By repeating Steps 1-4 for each pixel in the resized image, bicubic interpolation produces a highresolution image with smooth transitions and minimal artifacts
