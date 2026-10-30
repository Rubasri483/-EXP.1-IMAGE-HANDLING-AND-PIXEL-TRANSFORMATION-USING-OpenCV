# EXP-01-IMAGE-HANDLING-AND-PIXEL-TRANSFORMATION-USING-OpenCV-ASSIGNMENT

## NAME: RUBASRI R
## REG.NO: 212224240139

## AIM
Write a Python program using OpenCV that performs the following tasks:

1. Read and display an image.
2. Adjust the brightness of an image.
3. Modify the image contrast.
4. Generate a third image using bitwise operations.

## Software Required
- Anaconda - Python 3.7
- Jupyter Notebook

## Algorithm

# Step 1:
Load an image from your local directory and display it.

# Step 2:
Create a matrix of ones with data type `float64` to adjust brightness.

# Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image. Display all three images.

# Step 4:
Modify image contrast using scaling factors of 1.1 and 1.2. Display the original and contrast-adjusted images.

# Step 5:
Split the image (`Image.png`) into B, G, R components and display the channels.

---

## 1. Import the Required Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

## 2. Read and Display the Original Image

```python
img = cv2.imread('Image.png', cv2.IMREAD_COLOR)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

plt.imshow(img_rgb)
plt.title("Original Image")
plt.axis('off')
plt.show()
```


## OUTPUT:
<img width="348" height="413" alt="Screenshot 2026-10-30 160311" src="https://github.com/user-attachments/assets/7908a4d4-d42e-4329-8eb2-c1ee8208bcbf" />



## 3. Print Image Width, Height and Channels

```python
height, width, channels = img.shape

print("Image Width:", width)
print("Image Height:", height)
print("Image Channels:", channels)
print("Image Shape:", img.shape)
```

## 4. Draw a Line from Top-Left to Bottom-Right

```python
line_img = cv2.line(img_rgb.copy(), (0, 0), (768, 600), (255, 165, 0), 9)

plt.imshow(line_img)
plt.title("Image with Line")
plt.axis('off')
plt.show()
```

## OUTPUT:
<img width="345" height="404" alt="Screenshot 2026-10-30 214544" src="https://github.com/user-attachments/assets/3c57ea27-f20c-4812-babe-358c5a337ad7" />




## 5. Draw a Circle on the Image

```python
circle_img = cv2.circle(img_rgb.copy(), (400, 300), 150, (255, 165, 0), 10)

plt.imshow(circle_img)
plt.title("Image with Circle")
plt.axis('off')
plt.show()
```

## OUTPUT:
<img width="309" height="418" alt="image" src="https://github.com/user-attachments/assets/99e1538f-7b41-44c5-93a0-f11ddd14c5b7" />


## 6. Draw a Rectangle Around the Image

```python
rectangle_img = cv2.rectangle(img_rgb.copy(), (0, 0), (768, 600), (255, 165, 0), 10)

plt.imshow(rectangle_img)
plt.title("Image with Rectangle")
plt.axis('off')
plt.show()
```

## OUTPUT:
<img width="298" height="411" alt="image" src="https://github.com/user-attachments/assets/13b7245c-a8d8-4db4-9c74-ece0ab91a61e" />


## 7. Add Text to the Image

```python
text_img = cv2.putText(
    img_rgb.copy(), "Nikila", (100, 100),
    cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 165, 0), 10
)

plt.imshow(text_img)
plt.title("Image with Text")
plt.axis('off')
plt.show()
```
## OUTPUT:
<img width="323" height="417" alt="image" src="https://github.com/user-attachments/assets/2ed2315a-54b4-4b5a-99a1-db90b6bc6dc3" />


## 8. Save the Image as a PNG File

```python
cv2.imwrite('Output.png', img)
```

## 9. Read the Saved Image and Convert it to Grayscale

```python
image = cv2.imread('Output.png')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)

plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
plt.show()
```
## OUTPUT:
<img width="302" height="407" alt="image" src="https://github.com/user-attachments/assets/0d74fb14-4102-4ab6-bd40-cac25eba599f" />



## 10. Display the Original RGB Image

```python
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
plt.show()
```

## OUTPUT:
<img width="348" height="413" alt="Screenshot 2026-10-30 160311" src="https://github.com/user-attachments/assets/18827190-1be0-48b2-8b1f-f2f0a8e19df7" />




## 11. Convert RGB Image to HSV

```python
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)

plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="406" height="410" alt="image" src="https://github.com/user-attachments/assets/cd5e0d7e-5bd3-46cb-bf75-b71d2c6e829b" />

## 12. Convert RGB Image to YCrCb

```python
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)

plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="381" height="422" alt="image" src="https://github.com/user-attachments/assets/2430d770-5a23-4ee5-81f6-d1b2f6720570" />


## 13. Convert HSV Back to RGB

```python
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)

plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="326" height="407" alt="image" src="https://github.com/user-attachments/assets/04100b62-654a-4f3c-904a-1e4680beb5d9" />


## 14. Modify a Block of Pixels to White

```python
image = cv2.imread('Image.png')
image[200:500, 200:500] = [255, 255, 255]

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="333" height="381" alt="image" src="https://github.com/user-attachments/assets/414e17f0-351b-4711-9e82-f32148eb3766" />

## 15. Resize the Image to Half its Size

```python
image = cv2.imread('Image.png')
resized_image = cv2.resize(image, (768 // 2, 600 // 2))

resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)

print("Resized Image Shape:", resized_image_rgb.shape)

plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="521" height="411" alt="image" src="https://github.com/user-attachments/assets/c08cd875-a140-4146-92ea-3548d487f700" />


## 16. Crop a Specific Region of the Image

```python
image = cv2.imread('Image.png')
roi = image[50:350, 50:350]

roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)

plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="423" height="413" alt="image" src="https://github.com/user-attachments/assets/980621dc-f73c-4030-8c2a-f1b7c291aa03" />

## 17. Flip the Image Horizontally

```python
image = cv2.imread('Image.png')
flipped_horizontally = cv2.flip(image, 1)

flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)

plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="342" height="407" alt="image" src="https://github.com/user-attachments/assets/6095f583-bd8c-4a9d-9a3d-5e6710c90188" />


## 18. Flip the Image Vertically

```python
flipped_vertically = cv2.flip(image, 0)

flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)

plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="326" height="403" alt="image" src="https://github.com/user-attachments/assets/3471193f-33b2-435f-a34d-7e8df80174d8" />


## Result

Thus, the images were read and displayed, brightness and contrast adjustments were made, colour channels were split and merged, and bitwise operations were performed successfully using Python and OpenCV.
