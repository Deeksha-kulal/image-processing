# image-processing
Program1 : Devolop a program to display gray scale image using read and write operation
description:
A grayscale: (or graylevel) image is simply one in which the only colors are shades of gray. The reason for differentiating such images from any other sort of color image is that less information needs to be provided for each pixel. In fact a `gray' color is one in which the red, green and blue components all have equal intensity in RGB space, and so it is only necessary to specify a single intensity value for each pixel, as opposed to the three intensities needed to specify each pixel in a full color image.
A binary image: is one that consists of pixels that can have one of exactly two colors, usually black and white. Binary images are also called bi-level or two-level. This means that each pixel is stored as a single bit—i.e., a 0 or 1. The names black-and-white, B&W, monochrome or monochromatic are often used for this concept, but may also designate any images that have only one sample per pixel, such as grayscale images
to read an image we have to use imread()
to display an image use the function imshow()
waitkey() is keyboard binding function
destroyAllWindows() simply destroy all the windows are created
imwrite used to save an image


import numpy as np
import cv2
image=cv2.imread('flower1.jpg',1)
cv2.imshow('Original', image) 
cv2.waitKey(0)
cv2.destroyAllWindows() 
cv2.imwrite("grayscale.png",image) 

output:
![image](https://user-images.githubusercontent.com/72547536/104418948-c186de80-559d-11eb-9f67-fb9e6d97e15f.png)
![image](https://user-images.githubusercontent.com/72547536/104419157-1165a580-559e-11eb-9c2f-cc79f4288cf0.png)


Program2: Develop a Program to perform linear transformation on image
description:
cv2.imread()read the given file
Scale percent is set 500 to scale the image 500% of its original dimension both width,height


import cv2
image= cv2.imread('flower1.jpg')
scale_percent = 500
width = int(image.shape[1] * scale_percent / 100)
height = int(image.shape[0] * scale_percent / 100)
dsize = (width, height)
output = cv2.resize(image, dsize)
cv2.imshow('Original',output) 
cv2.waitKey(0)

![image](https://user-images.githubusercontent.com/72547536/104424877-cc595900-5534-11eb-9ca5-906883fd0200.png)
![image](https://user-images.githubusercontent.com/72547536/104425028-0296d880-5535-11eb-8361-6c663d6eb55a.png)

Program2(b): rotation
import cv2
image=cv2.imread('flower1.jpg')
cv2.imshow('original',image)
src=cv2.rotate(image,cv2.ROTATE_90_CLOCKWISE)
cv2.imshow('output',src)
cv2.waitKey(0)

output:
![image](https://user-images.githubusercontent.com/72547536/104425793-f2cbc400-5535-11eb-84ef-44be17feb0e8.png)
![image](https://user-images.githubusercontent.com/72547536/104426077-4d652000-5536-11eb-8783-b986db214576.png)





