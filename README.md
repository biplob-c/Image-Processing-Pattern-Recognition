# Image Processing
(Google Colab)
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
## 2. 



# Pattern-Recognition Sessional:
BUET - 2020

https://github.com/Tanjim131/CSE-474-Pattern-Recognition-Sessional/blob/main/Channel%20Equalization/Channel%20Equalization.pdf
