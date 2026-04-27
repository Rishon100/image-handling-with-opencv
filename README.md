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
# YOUR CODE HERE
```

## 6. Display the Colour image using matplotlib imshow() & Print the image width, height & channel.
```python
# YOUR CODE HERE
```

## 7. Crop the image to extract any specific (Eagle alone) object from the image.
```python
# YOUR CODE HERE
```

## 8. Resize the image up by a factor of 2x.
```python
# YOUR CODE HERE
```

## 9. Flip the cropped/resized image horizontally.
```python
# YOUR CODE HERE
```

## 10. Read in the image ('Apollo-11-launch.jpg').
```python
# YOUR CODE HERE
```

## 11. Add the following text to the dark area at the bottom of the image (centered on the image):
```python
text = 'Apollo 11 Saturn V Launch, July 16, 1969'
font_face = cv2.FONT_HERSHEY_PLAIN

# YOUR CODE HERE: use putText()
```

## 12. Draw a magenta rectangle that encompasses the launch tower and the rocket.
```python
rect_color = magenta

# YOUR CODE HERE
```

## 13. Display the final annotated image.
```python
# YOUR CODE HERE
```

## 14. Read the image ('Boy.jpg').
```python
# YOUR CODE HERE
```

## 15. Adjust the brightness of the image.
```python
# Create a matrix of ones (with data type float64)

# matrix_ones = 

# YOUR CODE HERE
```

## 16. Create brighter and darker images.
```python
img_brighter = cv2.add(img, matrix)

img_darker = cv2.subtract(img, matrix)

# YOUR CODE HERE
```

## 17. Display the images (Original Image, Darker Image, Brighter Image).
```python
# YOUR CODE HERE
```

## 18. Modify the image contrast.
```python
# Create two higher contrast images using the 'scale' option with factors of 1.1 and 1.2 (without overflow fix)

matrix1 = 

matrix2 = 

# img_higher1 = 

# img_higher2 = 

# YOUR CODE HERE
```

## 19. Display the images (Original, Lower Contrast, Higher Contrast).
```python
# YOUR CODE HERE
```

## 20. Split the image (boy.jpg) into the B,G,R components & Display the channels.
```python
# YOUR CODE HERE
```

## 21. Merged the R, G, B , displays along with the original image
```python
# YOUR CODE HERE
```

## 22. Split the image into the H, S, V components & Display the channels.
```python
# YOUR CODE HERE
```

## 23. Merged the H, S, V, displays along with original image.
```python
# YOUR CODE HERE
```
---

## Output
The program successfully performs image transformations including brightness and contrast adjustments, bitwise operations, and channel separation using OpenCV.

---

