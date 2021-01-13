# image-processing
Program1 : Program to display grayscale image

import numpy as np
import cv2
image=cv2.imread('flower1.jpg',1)
cv2.imshow('Original', image) 
cv2.waitKey(0)
cv2.destroyAllWindows() 
cv2.imwrite("grayscale.png",image) 

![image](https://user-images.githubusercontent.com/72547536/104418948-c186de80-559d-11eb-9f67-fb9e6d97e15f.png)
