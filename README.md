# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:
#### Import numpy module as np and pandas as pd.
<br>

### Step 2:
#### Assign the values to variables in the program.
<br>

### Step 3:
#### Get the values from the user appropriately.
<br>

### Step 4:
#### Continue the program by implementing the codes of required topics.
<br>

### Step 5:
#### Thus the program is executed in google colab.
<br>

## Program:

Developed By:
Register Number:

### Installing OpenCV , importing necessary libraries and displaying images  

```py
# Install OpenCV library
!pip install opencv-python-headless

import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images 
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

```

#### (i)Image Translation
```py
# Load an image from URL or file path
image_url = '1.jpg'  
image = cv2.imread(image_url)

# Define translation matrix
tx = 50  # Translation along x-axis
ty = 30  # Translation along y-axis
translation_matrix = np.float32([[1, 0, tx], [0, 1, ty]])  # Create translation matrix

# Apply translation to the image
translated_image = cv2.warpAffine(image, translation_matrix, (image.shape[1], image.shape[0]))

# Display original and translated images
print("Original Image:")
show_image(image)
print("Translated Image:")
show_image(translated_image)
```

#### (ii) Image Scaling
```py

# Load an image from URL or file path
image_url = '2.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)


# Define scale factors
scale_x = 1.5  # Scaling factor along x-axis
scale_y = 1.5  # Scaling factor along y-axis


# Apply scaling to the image
scaled_image = cv2.resize(image, None, fx=scale_x, fy=scale_y, interpolation=cv2.INTER_LINEAR)

# Display original and scaled images
print("Original Image:")
show_image(image)
print("Scaled Image:")
show_image(scaled_image)

```




#### (iii)Image shearing
```py
# Load an image from URL or file path
image_url = '3.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define shear parameters
shear_factor_x = 0.5  # Shear factor along x-axis
shear_factor_y = 0.2  # Shear factor along y-axis

# Define shear matrix
shear_matrix = np.float32([[1, shear_factor_x, 0], [shear_factor_y, 1, 0]])

# Apply shear to the image
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

# Display original and sheared images
print("Original Image:")
show_image(image)
print("Sheared Image:")
show_image(sheared_image)

```



#### (iv)Image Reflection

```py
# Load an image from URL or file path
image_url = '4.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Reflect the image horizontally
reflected_image_horizontal = cv2.flip(image, 1)

# Reflect the image vertically
reflected_image_vertical = cv2.flip(image, 0)

# Reflect the image both horizontally and vertically
reflected_image_both = cv2.flip(image, -1)

```

##### → Reflecting Horizontally

```py
# Display original and reflected images

show_image(image)
print("↑ Original Image")
show_image(reflected_image_horizontal)
print("↑ Reflected Horizontally")
```

##### → Reflected Vertically

```py
show_image(image)
print("↑ Original Image")
show_image(reflected_image_vertical)
print("↑ Reflected Vertically")

```

##### → Reflecting Horizontally & Vertically
```py

show_image(image)
print("↑ Original Image")
show_image(reflected_image_both)
print("↑ Reflected Both")

```

### (v)Image Rotation

```py
# Load an image from URL or file path
image_url = '5.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)


# Define rotation angle in degrees
angle = 45

# Get image height and width
height, width = image.shape[:2]

# Calculate rotation matrix
rotation_matrix = cv2.getRotationMatrix2D((width / 2, height / 2), angle, 1)

# Perform image rotation
rotated_image = cv2.warpAffine(image, rotation_matrix, (width, height))

# Display original and rotated images
print("Original Image:")
show_image(image)
print("Rotated Image:")
show_image(rotated_image)

```



### (vi)Image Cropping

```py
# Load an image from URL or file path
image_url = '6.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define cropping coordinates (x, y, width, height)
x = 100  # Starting x-coordinate
y = 50   # Starting y-coordinate
width = 200  # Width of the cropped region
height = 150  # Height of the cropped region

# Perform image cropping
cropped_image = image[y:y+height, x:x+width]

# Display original and cropped images
print("Original Image:")
show_image(image)
print("Cropped Image:")
show_image(cropped_image)

```




## Output:

### (i) Image Translation
<br>
<br>

![image](https://github.com/PSriVarshan/IMAGE-TRANSFORMATIONS/assets/114944059/e7bb136d-4570-4c28-a637-5f292d474650) ![image](https://github.com/PSriVarshan/IMAGE-TRANSFORMATIONS/assets/114944059/ce484cc9-5730-478b-8477-c7fecc0f88bb)



<br>
<br>

### (ii) Image Scaling
<br>
<br>

![image](https://github.com/PSriVarshan/IMAGE-TRANSFORMATIONS/assets/114944059/a9061299-0dd9-4666-bad7-fcf0ba20c3ad) ![image](https://github.com/PSriVarshan/IMAGE-TRANSFORMATIONS/assets/114944059/cfb058d6-52ac-4941-b66b-0b7838157ef9)



<br>
<br>


### (iii) Image shearing
<br>
<br>

![image](https://github.com/PSriVarshan/IMAGE-TRANSFORMATIONS/assets/114944059/050db428-58da-4af0-8e7c-8722bccc907e) ![image](https://github.com/PSriVarshan/IMAGE-TRANSFORMATIONS/assets/114944059/7c6da6cc-52f0-4fe7-a38e-eb8399bfd141)


<br>
<br>


### (iv) Image Reflection


#### Reflecting Horizontally

![image](https://github.com/PSriVarshan/IMAGE-TRANSFORMATIONS/assets/114944059/031c2534-a348-4934-8cf3-c9c31b62a1c9) ![image](https://github.com/PSriVarshan/IMAGE-TRANSFORMATIONS/assets/114944059/0c2d790d-d43f-4048-9ceb-601529dbcf60)



#### Reflecting Vertically

![image](https://github.com/PSriVarshan/IMAGE-TRANSFORMATIONS/assets/114944059/8c432222-638e-4df7-8624-f023e766527a) ![image](https://github.com/PSriVarshan/IMAGE-TRANSFORMATIONS/assets/114944059/35e4d9be-02dc-4cf4-bf7a-dc06daab2da8)


#### Reflecting Horizontally & Vertically

![image](https://github.com/PSriVarshan/IMAGE-TRANSFORMATIONS/assets/114944059/b9c2b391-1789-44c4-b479-a298f0e10404) ![image](https://github.com/PSriVarshan/IMAGE-TRANSFORMATIONS/assets/114944059/bd70512f-d8ed-4944-8d30-389665bf2e60)


<br>
<br>


### (v) Image Rotation
<br>
<br>

![image](https://github.com/PSriVarshan/IMAGE-TRANSFORMATIONS/assets/114944059/8e79f34d-206d-4391-871c-9cfeec9777f3) ![image](https://github.com/PSriVarshan/IMAGE-TRANSFORMATIONS/assets/114944059/479c903f-00bd-443f-9f02-1f0a016fa4bf)


<br>
<br>



### (vi) Image Cropping
<br>
<br>

![image](https://github.com/PSriVarshan/IMAGE-TRANSFORMATIONS/assets/114944059/7be119ee-fdc7-472e-9335-7af2ba69ca23) ![image](https://github.com/PSriVarshan/IMAGE-TRANSFORMATIONS/assets/114944059/c151f9f2-34c8-46d5-a382-be2229a87724)

<br>
<br>




## Result: 

### Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
