# Image Processing
- Used on Google Colab, 
- sample image files are also uploaded in this directory
- https://colab.research.google.com/drive/1EqYayRA1_Kmtxe30esMb1AB1ELkk7e1i
- 
## 1. Image Loading 
``` bash
from google.colab.patches import cv2_imshow
import numpy as np
import cv2
import math

#Method 1: Uploading lena.jpg directly to the Colab session (Temporary)
from google.colab import files
print("Please select 'einstein.jpg' to upload:")
files.upload()


img = cv2.imread('einstein.jpg', cv2.IMREAD_GRAYSCALE)
cv2_imshow(img)

print(img.max())
print(img.min())

print(img.shape)
for i in range(img.shape[0]):
    for j in range(img.shape[1]):
        a = img[i,j]
        if a>155:
            img[i,j]=255
        else:
            img[i,j]=0

cv2_imshow(img)

cv2.waitKey(0)
cv2.destroyAllWindows()

```

## 2. Negation of a Grayscal Image
``` bash
from google.colab.patches import cv2_imshow
import numpy as np
import cv2
#import math


#Method 1: Uploading lena.jpg directly to the Colab session (Temporary)
from google.colab import files
print("Please select 'lena.jpg' to upload:")
files.upload()

img = cv2.imread('lena.jpg', cv2.IMREAD_GRAYSCALE)
cv2_imshow(img)

print(img.max())
print(img.min())

print(img.shape)
for i in range(img.shape[0]):     #Rows
    for j in range(img.shape[1]): #Columns
        a = img.item(i,j)         # Retrieves the pixel value at position (i, j), for grayscale image 0-255
        img[i,j] = 255-a  #Negation transformation, Sets the pixel at position (i, j) to a new value: 255 - a.

cv2_imshow(img)          #Displays the inverted image after the transformation is complete.

cv2.waitKey(0) # Removed as it's not needed in Colab and can cause hanging
cv2.destroyAllWindows() # Removed as it's not needed in Colab and can cause hanging
```

## 3. Logarithmic Transformation of a grayscale image
``` bash

from google.colab.patches import cv2_imshow
import numpy as np
import cv2
import math

img = cv2.imread('lena.jpg', cv2.IMREAD_GRAYSCALE)
cv2_imshow(img)
out=img.copy()

print(img.max())
print(img.min())

#print(img.shape)
for i in range(img.shape[0]):
    for j in range(img.shape[1]):
        a = img.item(i,j)
        b=math.log(a+1,2)
        c=31
        out[i,j] = c*b

cv2_imshow(out)

cv2_imshow(img)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
## 4. Power Transformation Formula 
``` bash

from google.colab.patches import cv2_imshow
import cv2
import numpy as np
import matplotlib.pyplot as plt
import math

from google.colab.patches import cv2_imshow
img = cv2.imread('einstein.jpg', cv2.IMREAD_GRAYSCALE)
cv2_imshow(img)

store=img.copy()

c = 1
y = 2.5

for i in range(img.shape[0]):
    for j in range(img.shape[1]):
        a = img.item(i, j)

        r = a/255.0
        s = c*(r**y)

        store[i, j] = int(s*255)

cv2_imshow(store)

cv2.waitKey(0)
cv2.destroyAllWindows()

```

# Pattern-Recognition Sessional:
- https://www.kaggle.com/code/biplobc/lab-01-pattern-recognition
- https://www.kaggle.com/code/biplobc/lab-03-cats-and-dogs-classi-image-processing
- https://www.kaggle.com/code/biplobc/lab-04-pca-dimentionality-reduction
- https://www.kaggle.com/code/biplobc/lab-02-k-medoid-clustering-algorithm/edit
- https://www.kaggle.com/code/biplobc/k-nn-class-classification


https://github.com/Tanjim131/CSE-474-Pattern-Recognition-Sessional/blob/main/Channel%20Equalization/Channel%20Equalization.pdf
