# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
```
### Developed By:SANDHIYA R
### Register Number: 212222230129
```
#### i) To Read,display the image
```
import cv2
image=cv2.imread('CATS.jpg',1)
image=cv2.resize(image,(400,300))
cv2.imshow('IMAGE',image)
cv2.waitKey(0)
```
### Output:

### i) Read and display the image

![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/6c949b64-bc7a-42f4-bf8a-360fc046fe83)

#### ii)Write the image
```
import cv2
img=cv2.imread("CATS.jpg",1)
cv2.imwrite("cats.jpg",img)

```

### Output:

### ii)Write the image
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/07e221e5-7921-49af-9400-efd6f352e79a)

### iii)Shape of the Image
```
print(img.shape)
```

### Output:
### iii)Shape of the Image
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/12a2207f-bb3d-4582-8d43-bf29674a1df8)

### iv)Access rows and columns
```
import random
import cv2
image=cv2.imread('CATS.jpg',1)
image=cv2.resize(image,(400,400))
for i in range(100):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),random.randint(0,255),random.randint(0,255)]
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### Output:
### iv)Access rows and columns
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/b17664e0-3586-4ffd-bed6-2e887a0702c4)

### v)Cut and paste portion of image
```
tag = image[300:400,300:400]
image[50:150,50:150] = tag
cv2.imshow('partimage1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:
### v)Cut and paste portion of image
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/2be19d6b-2b5d-4a2b-8bbd-1a0f4aeeae76)

### vi) BGR and RGB to HSV and GRAY
```
import cv2
image= cv2.imread('CATS.jpg')
cv2.imshow('ORIGINAL IMAGE',image)
hsv_image = cv2.cvtColor(image,cv2.COLOR_BGR2HSV)

cv2.imshow('BGR2HSV',hsv_image)
hsvImage1=cv2.cvtColor(image,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsvImage1)
grayImage = cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)

cv2.imshow('BGR2GRAY',grayImage)
grayImage1 = cv2.cvtColor(image,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',grayImage1)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
### Output:
### vi) BGR and RGB to HSV and GRAY
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/eb040c56-8424-4a40-afc6-be7de4eea465)
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/96986a6b-5cb5-4e67-9e17-5fb7b2e3dddf)
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/c8e751cb-d6b4-434f-a39e-db7ddfcb4572)
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/35c548b5-1d09-43f1-a4ac-81099fe88f0e)
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/599e4682-f341-4541-81b2-063a0503eec4)

### vii) HSV to RGB and BGR
```
import cv2
image=cv2.imread('CATS.jpg')
image=cv2.resize(image,(300,200))

image=cv2.cvtColor(image,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',image)

RGB = cv2.cvtColor(image,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(image,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()

```
### Output:
### vii) HSV to RGB and BGR
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/cefb0e66-fccb-4f25-bd63-6a2ba1cbff4f)
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/3dcc0861-b7c0-4aca-9f34-48e7bca43f43)
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/e087a8fc-d17f-4c55-b714-7129f4529085)

### viii) RGB and BGR to YCrCb
```
import cv2
image=cv2.imread('CATS.jpg')
image=cv2.resize(image,(300,200))
cv2.imshow('Original RGB Image',image)

YCrCb1 = cv2.cvtColor(image,cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(image,cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()

```
### Output:
### viii) RGB and BGR to YCrCb
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/cebda66c-1b2a-429b-920f-478f69722019)
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/bd69adf5-9242-46ee-bc6c-06b16a0bc0f8)
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/bc3f1378-81aa-413b-bc18-a8362f437987)

### ix) Split and merge RGB Image
```
import cv2
image=cv2.imread('CATS.jpg',1)
image=cv2.resize(image,(300,200))

R=image[:,:,2]
G=image[:,:,1]
B=image[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged=cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
### 0utput:
### ix) Split and merge RGB Image
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/6d6faee0-84f0-4750-a8b2-449e08dd5330)
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/6b57fcd3-4abd-4754-a3ce-6db363063b7b)
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/d2e915df-726d-4284-a180-0a1752e5cd7d)
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/9bd66428-07e9-4744-9231-d68e8cb72ede)

### x) Split and merge HSV Image
```
import cv2
image=cv2.imread("CATS.jpg",1)
image= cv2.resize(image,(300,200))
image=cv2.cvtColor(image,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(image)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()

```
### Output:
### x) Split and merge HSV Image
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/3e23d693-d5d7-4713-a675-32056c6cedff)
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/edccab37-4653-4295-acb5-dc323cee5e18)
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/1b5f75e6-9235-4d3d-a3a2-4f59a57c044e)
![image](https://github.com/SandhiyaR1/COLOR_CONVERSIONS_OF-IMAGE/assets/113497571/2a9cd92b-6b9e-441c-9d82-e6269d73355d)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







