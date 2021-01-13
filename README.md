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
description:scaling
Scaling, like translation is is a simple transformation which just scales the coordinates of an object. It is
specified either by working directly with the local coordinates, or by expressing the coordinates in terms of
Frames
cv2.resize resize the image to the size disize and return numpy array
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
description:
A rotation is a transformation in which the object is rotated about a fixed point.
The direction of rotation can be clockwise or anticlockwise.

import cv2
image=cv2.imread('flower1.jpg')
cv2.imshow('original',image)
src=cv2.rotate(image,cv2.ROTATE_90_CLOCKWISE)
cv2.imshow('output',src)
cv2.waitKey(0)

output:
![image](https://user-images.githubusercontent.com/72547536/104425793-f2cbc400-5535-11eb-84ef-44be17feb0e8.png)
![image](https://user-images.githubusercontent.com/72547536/104426077-4d652000-5536-11eb-8783-b986db214576.png)

Program3:Program to find sum and mean of the image
description:
listdir()-it is used to get the list of all files and directories in the specified directory
append()this method in python adds the single item to the existing list

import cv2
import os
path = 'C:\dee'
imgs = []

files = os.listdir(path)
for file in files:
    filepath=path+"\\"+file
    imgs.append(cv2.imread(filepath))
i=0
im = []
for im in imgs:
    #cv2.imshow(files[i],imgs[i])
    im+=imgs[i]
    i=i+1
cv2.imshow("sum of four pictures",im)
meanImg = im/len(files)
cv2.imshow("mean of four pictures",meanImg)
cv2.waitKey(0)
output:
![image](https://user-images.githubusercontent.com/72547536/104431617-f0b93380-553c-11eb-9fd3-26236b40d6a9.png)
![image](https://user-images.githubusercontent.com/72547536/104432221-a4babe80-553d-11eb-962c-d85d7c87b57c.png)






Program4:Convert the image to gray scale and binary image
description:
A grayscale: (or graylevel) image is simply one in which the only colors are shades of gray. The reason for differentiating such images from any other sort of color image is that less information needs to be provided for each pixel. In fact a `gray' color is one in which the red, green and blue components all have equal intensity in RGB space, and so it is only necessary to specify a single intensity value for each pixel, as opposed to the three intensities needed to specify each pixel in a full color image.
A binary image: is one that consists of pixels that can have one of exactly two colors, usually black and white. Binary images are also called bi-level or two-level. This means that each pixel is stored as a single bit—i.e., a 0 or 1. The names black-and-white, B&W, monochrome or monochromatic are often used for this concept, but may also designate any images that have only one sample per pixel, such as grayscale images
image thresholding: it is a technique in opencv which is the assignment of pixel values in reaction to the threshold value provided

import cv2
originalImage=cv2.imread('b2.jpg')
grayImage=cv2.cvtColor(originalImage,cv2.COLOR_BGR2GRAY)
(thresh,blackAndWhiteImage)=cv2.threshold(grayImage,127,225,cv2.THRESH_BINARY)
cv2.imshow('Black white image',blackAndWhiteImage)
cv2.imshow('OriginalImagee',originalImage)
cv2.imshow('Gray Image',grayImage)
cv2.waitKey(0)
cv2.destroyAllWindows()

output:![image](https://user-images.githubusercontent.com/72547536/104428449-59061600-5539-11eb-8258-72e1d7b612dd.png)
![image](https://user-images.githubusercontent.com/72547536/104428573-7dfa8900-5539-11eb-8e76-f35a9cc6e60f.png)
![image](https://user-images.githubusercontent.com/72547536/104428711-a3879280-5539-11eb-8715-f9e3800227a3.png)

Program 5:Program to covert the given image to different color space
description:
color spacing:these are a way to represent the color channel present in the image that gives the image that particular hue
hsv:HSV is a cylindrical color model that remaps the RGB primary colors into dimensions that are easier for humans to understand. Like the Munsell Color System, these dimensions are hue, saturation, and value.
yuv:The YUV color model is the basic color model used in analogue color TV broadcasting. Initially YUV is the re-coding of RGB for transmission efficiency (minimizing bandwidth) and for downward compatibility with black-and white television.
rgb:In the RGB model, each color appears as a combination of red, green, and blue. This model is called additive, and the colors are called primary colors. The primary colors can be added to produce the secondary colors of light (see Figure "Primary and Secondary Colors for RGB and CMYK Models") - magenta (red plus blue), cyan (green plus blue), and yellow (red plus green). The combination of red, green, and blue at full intensities makes white.

import cv2
img = cv2.imread('flower.jpg')
yuv_img = cv2.cvtColor(img, cv2.COLOR_BGR2YUV)
cv2.imshow('YUV image', yuv_img)

hsv_img = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
cv2.imshow('HSV image', hsv_img)

rgb_img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
cv2.imshow('RGB image', rgb_img)
cv2.waitKey()
output:
![image](https://user-images.githubusercontent.com/72547536/104429055-07aa5680-553a-11eb-8046-85257f5d5064.png)
![image](https://user-images.githubusercontent.com/72547536/104429189-2e688d00-553a-11eb-8da8-11e600b6e986.png)
![image](https://user-images.githubusercontent.com/72547536/104429335-6243b280-553a-11eb-9e08-6ef6f5c80748.png)

Program 6:Program to create an image from 2D array
description:
2dArray:two dimensional array is an array within an array.it is the type of array the position of an data element is refered by two indices instead of one.
np.zeros():it returns a new array of given shape and type with zeros

import numpy as np
from PIL import Image
import cv2 as C
array=np.zeros([100,200,3],dtype=np.uint8)
array[:,:100]=[150,128,0]
array[:,100:]=[0,0,255]
img=Image.fromarray(array)
img.save('b2.jpg')
img.show()
C.waitKey(0)         

Output:
![image](https://user-images.githubusercontent.com/72547536/104432659-14c94480-553e-11eb-9b77-5604294c40fe.png)











