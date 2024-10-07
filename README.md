# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary libraries and read the original image and save it as a image variable.

### Step2:
Translate the image using a function warpPerpective()

### Step3:
Scale the image by multiplying the rows and columns with a float value.

### Step4:
Shear the image in both the rows and columns.

### Step5:
Find the reflection of the image.

### Step 6:
Rotate the image using angle function.am:

Developed By: Yuvabharathi.B

Register Number: 212222230181
# Load the image
### Original image 
```


import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('came.jpeg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Plot the original and transformed images
plt.figure(figsize=(12, 8))
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')

````
![WhatsApp Image 2024-10-03 at 4 26 49 PM](https://github.com/user-attachments/assets/14b66658-8980-4847-a91b-08d1491402ff)


### i)Image Translation
```

rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  # Translate by (50, 100) pixels
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```
## Output:
![WhatsApp Image 2024-10-03 at 4 26 49 PM (1)](https://github.com/user-attachments/assets/6d154a33-f3a6-43bb-8f22-a330ab3a0215)

### ii) Image Scaling
```

scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR) 
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
```
## Output:
![WhatsApp Image 2024-10-03 at 4 26 49 PM (2)](https://github.com/user-attachments/assets/0c8a07e9-a651-4584-82d6-adad330bc56f)

```

M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
```
## Output:
![WhatsApp Image 2024-10-03 at 4 26 49 PM (3)](https://github.com/user-attachments/assets/7f0ef2f0-4204-4aaf-8c5d-921e181654cd)

### iv)Image Reflection
```

reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
```
## Output:
![WhatsApp Image 2024-10-03 at 4 26 49 PM (5)](https://github.com/user-attachments/assets/fd056c78-75da-4176-8ab3-c4657a69733c)

### v)Image Rotation
```

M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  # Rotate by 45 degrees
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
plt.tight_layout()
plt.show()
```
## Output:
![WhatsApp Image 2024-10-03 at 4 26 49 PM (6)](https://github.com/user-attachments/assets/14ba2d7b-83bc-4434-b0f6-a42e4eab7365)


# 6. Cropping
```
cropped_image = image_rgb[100:300, 500:2000]   # Crop a portion of the image
plt.figure(figsize=(17, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()
```
## Output:

![WhatsApp Image 2024-10-03 at 4 26 49 PM (7)](https://github.com/user-attachments/assets/a2942d72-2848-4676-a516-636597376dd6)





## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
