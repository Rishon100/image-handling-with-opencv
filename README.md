# image-handling-with-opencv
# Image Handling and Pixel Transformations Using OpenCV

## AIM
Develop a Python program using OpenCV to perform basic image processing operations such as image loading, brightness adjustment, contrast enhancement, and bitwise image manipulation.

---

## Objectives
- Read and display an image using OpenCV.
- Adjust the brightness of an image.
- Modify image contrast using scaling operations.
- Generate a new image using bitwise operations.
- Split a color image into its Blue, Green, and Red (BGR) channels.

---

## Software Requirements
- Anaconda Navigator
- Python 3.7
- Jupyter Notebook

---

## Algorithm / Procedure

### Step 1
Import the required libraries and load an image from the local directory. Display the loaded image.

### Step 2
Create a matrix of ones with the `float64` data type to control image brightness.

### Step 3
Generate brighter and darker versions of the image by adding and subtracting the brightness matrix from the original image. Display the original, brighter, and darker images.

### Step 4
Modify the contrast of the image using scaling factors such as `1.1` and `1.2` to create higher contrast images. Display the original image along with the modified contrast images.

### Step 5
Split the image (`boy.jpg`) into its Blue, Green, and Red (BGR) channels and display each channel separately.

---
Program Developed By:  
Name: V Rishon Anand  

Register Number: 212224240135 

# Ex. No. 01

## 1. Read the image ('Eagle_in_Flight.jpg') using OpenCV imread() as a grayscale image.
```python
img_bgr = cv2.imread("Eagle_in_Flight.jpg",0)
```

## 2. Print the image width, height & Channel.
```python
img_bgr.shape
```

## 3. Display the image using matplotlib imshow().
```python
plt.imshow(img_bgr,cmap="gray")
plt.title("gray image")
plt.axis("off")
plt.show()
```

## 4. Save the image as a PNG file using OpenCV imwrite().
```python
cv2.imwrite('output.jpg',img_bgr)
```

## 5. Read the saved image above as a color image using cv2.cvtColor().
```python
image12 = cv2.cvtColor(img1_1,cv2.COLOR_BGRA2RGBA)
```

## 6. Display the Colour image using matplotlib imshow() & Print the image width, height & channel.
```python
plt.imshow(image12)
plt.show()
```

## 7. Crop the image to extract any specific (Eagle alone) object from the image.
```python
cropped_image = img_e[20:420, 200:600]
plt.figure(figsize=[20,10])
plt.subplot(121)
plt.imshow(img_e[:,:,::-1])
plt.title("Original image")
plt.subplot(122)
plt.imshow(cropped_image[:,:,::-1])
plt.title("crop image")```

## 8. Resize the image up by a factor of 2x.
```python
resized_image = cv2.resize(cropped_image,None,fx = 2,fy = 2)
plt.imshow(resized_image[:,:,::-1])
plt.title("2x Resized Image")
plt.show()
```

## 9. Flip the cropped/resized image horizontally.
```python
flipped_image = cv2.flip(resized_image, 1)

plt.imshow(flipped_image[:,:,::-1])
plt.title("Horizontally Flipped Image")
plt.axis("off")
plt.show()
```

## 10. Read in the image ('Apollo-11-launch.jpg').
```python
img = cv2.imread("Apollo-11-launch.jpg")
plt.axis("off")
plt.title("Apollo 11  launch")
plt.imshow(img)
```

## 11. Add the following text to the dark area at the bottom of the image (centered on the image):
```python
text = 'Apollo 11 Saturn V Launch, July 16, 1969'
font_face = cv2.FONT_HERSHEY_PLAIN
x = 60
y = img.shape[0] - 20
cv2.putText(img,text,(x,y),font_face,1.5,(255,255,255),3);
# YOUR CODE HERE: use putText()
```

## 12. Draw a magenta rectangle that encompasses the launch tower and the rocket.
```python
rect_color = magenta

rect_color = (255,0,255)
cv2.rectangle(img, (500,80),(700,620),rect_color,3);
```

## 13. Display the final annotated image.
```python
plt.imshow(img,cmap = "gray")
plt.axis("off")
plt.show()
```

## 14. Read the image ('Boy.jpg').
```python
img2 = cv2.imread("boy.jpg")
plt.imshow(img2[:,:,::-1])
```

## 15. Adjust the brightness of the image.
```python
# Create a matrix of ones (with data type float64)

# matrix_ones = 

matrix_ones = np.ones(img2.shape,dtype = "float64") * 100
```

## 16. Create brighter and darker images.
```python
img_brighter = cv2.add(img2,matrix_ones.astype(np.uint8))
img_darker = cv2.subtract(img2,matrix_ones.astype(np.uint8))```

## 17. Display the images (Original Image, Darker Image, Brighter Image).
```python
plt.figure(figsize=(15,5))

plt.subplot(131)
plt.imshow(img2[:,:,::-1])
plt.title("Original Image")
plt.axis("off")

plt.subplot(132)
plt.imshow(img_darker[:,:,::-1])
plt.title("Darker Image")
plt.axis("off")

plt.subplot(133)
plt.imshow(img_brighter[:,:,::-1])
plt.title("Brighter Image")
plt.axis("off")

plt.show()
```

## 18. Modify the image contrast.
```python
# Create two higher contrast images using the 'scale' option with factors of 1.1 and 1.2 (without overflow fix)
matrix1 = np.ones(img2.shape,dtype = "float64") * 1.1
matrix2 = np.ones(img2.shape,dtype = "float64") * 1.2
img_higher1 = np.clip(img2 * matrix1,0,255).astype(np.uint8)
img_higher2 = np.clip(img2 * matrix2,0,255).astype(np.uint8)
```

## 19. Display the images (Original, Lower Contrast, Higher Contrast).
```python
plt.figure(figsize = [20,10])

plt.subplot(131)
plt.imshow(img2[:,:,::-1])
plt.axis("off")

plt.subplot(132)
plt.imshow(img_higher1[:,:,::-1])
plt.axis("off")

plt.subplot(133)
plt.imshow(img_higher2[:,:,::-1])
plt.axis("off")

plt.show()
```

## 20. Split the image (boy.jpg) into the B,G,R components & Display the channels.
```python
img2 = cv2.imread("boy.jpg")
B, G, R = cv2.split(img2)
plt.figure(figsize=[20,10])

plt.subplot(141)
plt.imshow(B)
plt.title("Blue")
plt.axis("off")

plt.subplot(142)
plt.imshow(G)
plt.title("Green")
plt.axis("off")

plt.subplot(143)
plt.imshow(R)
plt.title("Red")
plt.axis("off")

plt.subplot(144)
plt.imshow(img2[:,:,::-1])
plt.title("Original")
plt.axis("off")
```

## 21. Merged the R, G, B , displays along with the original image
```python
merged_img2 = cv2.merge((B,G,R))
plt.figure(figsize = [20,10])

plt.subplot(121)
plt.imshow(merged_img2)
plt.title("merged image")
plt.axis("off")

plt.subplot(122)
plt.imshow(img2[:,:,::-1])
plt.title("orignal")
plt.axis("off")

plt.show()
```

## 22. Split the image into the H, S, V components & Display the channels.
```python
hsv_img = cv2.cvtColor(img2, cv2.COLOR_BGR2HSV)
H, S, V = cv2.split(hsv_img)
plt.figure(figsize = [20,10])

plt.subplot(131)
plt.imshow(H)
plt.title("Hue")
plt.axis("off")

plt.subplot(132)
plt.imshow(S)
plt.title("Saturation")
plt.axis("off")

plt.subplot(133)
plt.imshow(V)
plt.title("Value")
plt.axis("off")

plt.show()
```

## 23. Merged the H, S, V, displays along with original image.
```python
merged_img3 = cv2.merge((H,S,V))
plt.figure(figsize = [20,10])

final_image = cv2.cvtColor(merged_img3, cv2.COLOR_HSV2BGR)

plt.subplot(121)
plt.imshow(final_image[:,:,::-1])
plt.title("Merged image")
plt.axis("off")

plt.subplot(122)
plt.imshow(img2[:,:,::-1])
plt.title("Original image")
plt.axis("off")

plt.show()
```
---

## Output
The program successfully performs image transformations including brightness and contrast adjustments, bitwise operations, and channel separation using OpenCV.

---

