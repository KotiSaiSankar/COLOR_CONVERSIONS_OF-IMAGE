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
### Developed By: Koti Sai Sankar
### Register Number: 212222240111


## Output:

### i) Read and display the image
```py
    import cv2
    image=cv2.imread('gtr.jpg',1)
    image=cv2.resize(image,(400,300))
    cv2.imshow('Athmaj Venugopal',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
## Output:

![1](https://github.com/KotiSaiSankar/COLOR_CONVERSIONS_OF-IMAGE/assets/118344248/b4a18e7b-b235-49a2-a0d1-98932d099653)

### ii)Write the image
```py
    import cv2
    image=cv2.imread('gtr.jpg',0)
    cv2.imwrite('vintage.jpg',image)
```
## Output:
![2](https://github.com/KotiSaiSankar/COLOR_CONVERSIONS_OF-IMAGE/assets/118344248/f25a3c81-4d4f-41e7-8efa-f031a58da059)


### iii)Shape of the Image
```py
    import cv2
    image=cv2.imread('gtr.jpg',1)
    print(image.shape)
```
## Output:
![3](https://github.com/KotiSaiSankar/COLOR_CONVERSIONS_OF-IMAGE/assets/118344248/fda726be-d620-4b60-945f-28f60fad9a8b)

### iv)Access rows and columns
```py
    import random
    import cv2
    image=cv2.imread('gtr.jpg',1)
    image=cv2.resize(image,(400,400))
    for i in range (150,200):
      for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
## Output:

![4](https://github.com/KotiSaiSankar/COLOR_CONVERSIONS_OF-IMAGE/assets/118344248/13819a5e-45f4-4179-8063-a218968eb3d8)

### v)Cut and paste portion of image
```py
   import cv2
   image=cv2.imread('gtr.jpg',1)
   image=cv2.resize(image,(400,400))
   tag =image[130:200,110:190]
   image[110:180,120:200] = tag
   cv2.imshow('partimage1',image)
   cv2.waitKey(0)
   cv2.destroyAllWindows()
```
## Output:
![5](https://github.com/KotiSaiSankar/COLOR_CONVERSIONS_OF-IMAGE/assets/118344248/303076bf-05f3-4401-b0bc-d11448338bd3)


### vi) BGR and RGB to HSV and GRAY
```py
import cv2
img = cv2.imread('gtr.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)
hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)
gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)
gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![6](https://github.com/KotiSaiSankar/COLOR_CONVERSIONS_OF-IMAGE/assets/118344248/ff8cb450-1b3b-47a3-852d-33879af21bf8)

### vii) HSV to RGB and BGR
```py
import cv2
img = cv2.imread('gtr.jpg')
img = cv2.resize(img,(300,200))
img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)
RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)
BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![7](https://github.com/KotiSaiSankar/COLOR_CONVERSIONS_OF-IMAGE/assets/118344248/71a5fdf3-eeac-4d70-88cc-1f5e239a8731)

### viii) RGB and BGR to YCrCb
```py
import cv2
img = cv2.imread('gtr.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![8](https://github.com/KotiSaiSankar/COLOR_CONVERSIONS_OF-IMAGE/assets/118344248/9eba4c9c-9a8f-4d7d-b4ab-3d7890c4cbc8)


### ix) Split and merge RGB Image
```py
import cv2
img = cv2.imread('gtr.jpg',1)
img = cv2.resize(img,(300,200))
R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]
cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)
merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![9](https://github.com/KotiSaiSankar/COLOR_CONVERSIONS_OF-IMAGE/assets/118344248/00438c13-695c-47b0-88f5-9173aca553e1)


### x) Split and merge HSV Image
```py
import cv2
img = cv2.imread("gtr.jpg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
H,S,V=cv2.split(img)
cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)
merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![10](https://github.com/KotiSaiSankar/COLOR_CONVERSIONS_OF-IMAGE/assets/118344248/bb61466e-1971-45f8-a4de-0ebc07ca4830)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







