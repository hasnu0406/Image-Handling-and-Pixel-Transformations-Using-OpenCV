# Image-Handling-and-Pixel-Transformations-Using-OpenCV 
## Program Developed By:
### NAME: HASNA MUBARAK AZEEM
### REG NO: 212223240052

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels


## Ex. No. 01

#### 1. Read the image using OpenCV
```python
import cv2
import matplotlib.pyplot as plt
img = cv2.imread('hasna.jpeg', cv2.IMREAD_COLOR)

```

#### 2. Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```python
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape

```

#### 3. Display the image using Matplotlib
```python
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```

#### 4. Save the image as a PNG file using OpenCV imwrite().
```python
img=cv2.imread("hasna.jpeg")
cv2.imwrite("hasna.png",img)
```

#### 5. Read the saved image above as a color image using cv2.cvtColor().
```python
image = cv2.imread('hasna.jpeg')
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```

#### 6. Draw a line from top-left to bottom-right 
```python
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
```

#### 7. Draw a circle at the center of the image.
```python
image = cv2.imread('hasna.jpeg') 
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```

#### 8. Draw a rectangle around  the whole image
```python
image = cv2.imread('hasna.jpeg') 
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()

```

#### 9. Add the text "OpenCV Drawing" at the top-left corner of the image.
```python
image = cv2.imread('hasna.jpeg') 
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```

#### 10.Convert the image from RGB to HSV and display it.
```python
image = cv2.imread('hasna.jpeg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
```

#### 11. Convert RGB to GRAY
```python
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
```

#### 12. Convert RGB to YCrCb
```python
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
```

#### 13. Convert HSV back to RGB
```python
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```

#### 14. Modify a block of pixels (300x300) to white, starting from (200, 200)
```python
image[200:500, 200:500] = [255, 255, 255]
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```

#### 15. Resize the original image to half its size and display it.
```python
image = cv2.imread('hasna.jpeg')
image.shape
resized_image = cv2.resize(image, (768 // 2, 600 // 2)) 
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```

#### 16. Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.
```python
image = cv2.imread('hasna.jpeg')
image.shape
roi = image[50:350, 50:350]
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```

#### 17. Flip the original image horizontally and display it.
```python
image = cv2.imread('hasna.jpeg') 
flipped_horizontally = cv2.flip(image, 1)
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
```

#### 18. Flip the original image vertically and display it.
```python
flipped_vertically = cv2.flip(image, 0)
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```


## Output:
 1. Read the image using OpenCV

 
<img width="306" height="409" alt="download" src="https://github.com/user-attachments/assets/a6243f04-7609-4253-a919-eed2049cfd2c" />






2.  Draw a line from top-left to bottom-right


<img width="306" height="409" alt="download" src="https://github.com/user-attachments/assets/4766b9a0-f18d-43a6-bb82-2932c7cd631a" />




3)Draw a circle at the center of the image.



<img width="306" height="409" alt="download" src="https://github.com/user-attachments/assets/137bdb0d-2753-457b-a4cd-19ab17a80e62" />




4)Draw a rectangle around  the whole image



<img width="306" height="409" alt="download" src="https://github.com/user-attachments/assets/72357c31-d713-4632-9308-7acd7c86e6dd" />



5)Add the text "OpenCV Drawing" at the top-left corner of the image.



<img width="306" height="409" alt="download" src="https://github.com/user-attachments/assets/efc6743e-7737-4917-9e14-e1a8fd18eb0d" />



6)Convert the image from RGB to HSV and display it.


<img width="306" height="409" alt="download" src="https://github.com/user-attachments/assets/3aa3e0ee-02c1-4b4f-a881-11342caf41bf" />

7) Convert the image from RGB to GRAY and display it. 



<img width="306" height="409" alt="download" src="https://github.com/user-attachments/assets/e05cafe6-68e5-4a56-b682-252899c38e9d" />




8) Convert the image from RGB to YCrCb and display it. 



<img width="306" height="409" alt="download" src="https://github.com/user-attachments/assets/2cec7735-21f4-4077-8e42-69805d67aa89" />


9)Convert the HSV image back to RGB and display it.



<img width="306" height="409" alt="download" src="https://github.com/user-attachments/assets/66239fda-1392-4f2b-8525-989f963dad15" />

10) Modify the color of the pixel at (200, 200) to white.


<img width="306" height="409" alt="download" src="https://github.com/user-attachments/assets/d7f5602f-f55b-48df-8dc7-1d3027f88991" />


11)  Resize the original image to half its size and display it.

    
<img width="493" height="409" alt="download" src="https://github.com/user-attachments/assets/334f2e9e-8cb7-4b9d-ba9b-a7c68d4f7ece" />



12)Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.



<img width="389" height="409" alt="download" src="https://github.com/user-attachments/assets/b184ab3a-76a4-4f07-a77a-2dbeeb3b6496" />



13) Flip the original image horizontally and display it.


<img width="306" height="409" alt="download" src="https://github.com/user-attachments/assets/eea87e09-edc5-4e3e-9b98-887250e1f171" />



14) Flip the original image vertically and display it.

<img width="306" height="409" alt="download" src="https://github.com/user-attachments/assets/b964828e-09e7-4bb6-91bf-bddbca23842b" />



## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
