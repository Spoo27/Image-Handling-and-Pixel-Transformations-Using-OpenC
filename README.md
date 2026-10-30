# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

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
o Draw a line from the top-left to the bottom-right of the image.
o Draw a circle at the center of the image. 
o Draw a rectangle around a specific region of interest in the image. 
o Add the text "OpenCV Drawing" at the top-left corner of the image.

### Step 3:
o Convert the image from RGB to HSV and display it.
o Convert the image from RGB to GRAY and display it. 
o Convert the image from RGB to YCrCb and display it.  
o Convert the HSV image back to RGB and display it.

### Step 4:
o Access and print the value of the pixel at coordinates (100, 100). 
o Modify the color of the pixel at (200, 200) to white.

### Step 5:
o Resize the original image to half its size and display it.

### Step6:
o Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.

### Step7:
o Flip the original image horizontally and display it. 
o Flip the original image vertically and display it.

### Step8:
o Save the final modified image to your local directory.

## Program Developed By:
- **Name:** Spoorthi V
- **Register Number:** 212224230

## Ex. No. 01

### Import neccessary libraries
        import cv2
        import matplotlib.pyplot as plt
### Read the image using OpenCV
    img = cv2.imread('Qno. 1.jpg', cv2.IMREAD_COLOR)
### Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
    img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

    ### Display the image using Matplotlib
    plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
    plt.title("Original Image")
    plt.axis('off')  # Removes axis ticks and labels
    plt.show()
### Load the image
    image = cv2.imread('Qno. 1.jpg') 
### Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
    img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
    img_rgb.shape
### Draw a line from top-left to bottom-right
    line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
    plt.imshow(line_img, cmap='viridis')  
    plt.title("Image with Line")
    plt.axis('off')  
    plt.show()
    ### Load the image
    image = cv2.imread('Qno. 1.jpg') 
### Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
    img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
    img_rgb.shape
    circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)
    plt.imshow(circle_img, cmap='viridis')  
    plt.title("Image with Circle")
    plt.axis('off')  
    plt.show()
### Load the image
    image = cv2.imread('Qno. 1.jpg') 
### Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
    img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
      img.shape
### Draw a rectangle around the Whole image
    rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
    plt.imshow(rectangle_img, cmap='viridis')  
    plt.title("Image with Rectangle")
    plt.axis('off')  
    plt.show()
### Load the image
    image = cv2.imread('Qno. 1.jpg') 
### Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
    img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
### Add text to the image
    text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
    plt.imshow(text_img, cmap='viridis')  
    plt.title("Image with Text")
    plt.axis('off')
     plt.show()
### Load the image
    image = cv2.imread('Qno. 1.jpg') 
    image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
### Original RGB Image
        plt.imshow(image_rgb)
        plt.title("Original RGB Image")
        plt.axis("off")
### Convert RGB to HSV
        image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
### HSV Image
    plt.imshow(image_hsv)
    plt.title("HSV Image")
    plt.axis("off")
### Convert RGB to GRAY
    image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
### Grayscale Image
    plt.imshow(image_gray, cmap='gray')
    plt.title("Grayscale Image")
    plt.axis("off")
### Convert RGB to YCrCb
    image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
### YCrCb Image
    plt.imshow(image_ycrcb)
    plt.title("YCrCb Image")
    plt.axis("off")
### Convert HSV back to RGB
    image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
    plt.imshow(image_hsv_to_rgb)
    plt.title("HSV to RGB Image")
    plt.axis("off")
### Modify a block of pixels (300x300) to white, starting from (200, 200)
    image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
### Display the modified image
    plt.imshow(image_rgb)
    plt.title("Image with 300x300 White Block")
    plt.axis("off")
     plt.show()
### Load the image
    image = cv2.imread('Qno. 1.jpg') 
    image.shape
### Resize the image to half its size
    resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
### Convert BGR to RGB for displaying with Matplotlib
    resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
    resized_image_rgb.shape
### Display the resized image
    plt.imshow(resized_image_rgb)
    plt.title("Resized Image (Half Size)")
    plt.axis("off")
    plt.show()
### Load the image
    image = cv2.imread('Qno. 1.jpg') 
    image.shape
    ### Crop a 300x300 region starting from (50, 50)
    roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
### Convert BGR to RGB for displaying with Matplotlib
    roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
### Display the cropped region (ROI)
    plt.imshow(roi_rgb)
    plt.title("Cropped Region of Interest (ROI)")
    plt.axis("off")
    plt.show()
### Load the image
    image = cv2.imread('Qno. 1.jpg') 
### Flip the image horizontally (left-right)
    flipped_horizontally = cv2.flip(image, 1)
### Convert BGR to RGB for displaying with Matplotlib
    flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
### Horizontal flip
    plt.imshow(flipped_horizontally_rgb)
    plt.title("Flipped Horizontally")
    plt.axis("off")
### Flip the image vertically (up-down)
    flipped_vertically = cv2.flip(image, 0)
### Convert BGR to RGB for displaying with Matplotlib
    flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
### Vertical flip
    plt.imshow(flipped_vertically_rgb)
    plt.title("Flipped Vertically")
     plt.axis("off")


## Output:
<img width="570" height="455" alt="Screenshot 2026-10-30 140412" src="https://github.com/user-attachments/assets/1763db3a-5c67-4a17-afab-8d43a3a31792" />
<img width="587" height="473" alt="Screenshot 2026-10-30 140420" src="https://github.com/user-attachments/assets/6ba1fb00-3e3d-44c7-b954-368f69e7711d" />
<img width="586" height="455" alt="Screenshot 2026-10-30 140428" src="https://github.com/user-attachments/assets/41bb84c4-4459-40d8-803d-9bbf0e3217a9" />
<img width="595" height="458" alt="Screenshot 2026-10-30 140435" src="https://github.com/user-attachments/assets/e43d61b4-a4ba-49bf-8d5d-fb1b03e4cad9" />
<img width="586" height="456" alt="Screenshot 2026-10-30 140441" src="https://github.com/user-attachments/assets/a2b5ae8b-4d82-4628-aa1b-dad5b63f7c70" />
<img width="573" height="465" alt="Screenshot 2026-10-30 140448" src="https://github.com/user-attachments/assets/c5abe3f0-145b-412d-8b38-78cb889a7801" />
<img width="580" height="461" alt="Screenshot 2026-10-30 140455" src="https://github.com/user-attachments/assets/0eaa064a-9482-42eb-b017-fa863d44969a" />
<img width="596" height="451" alt="Screenshot 2026-10-30 140504" src="https://github.com/user-attachments/assets/11f7d347-3a90-47a9-a55a-8932148a8412" />
<img width="592" height="466" alt="Screenshot 2026-10-30 140511" src="https://github.com/user-attachments/assets/9d84a780-3698-4ded-b67a-3d4b3ab8cf82" />
<img width="575" height="470" alt="Screenshot 2026-10-30 140521" src="https://github.com/user-attachments/assets/f9c8fa69-3f20-43ab-b73d-6b1e3c1b87fa" />
<img width="582" height="452" alt="Screenshot 2026-10-30 140529" src="https://github.com/user-attachments/assets/dc025a7d-f520-4dd6-836d-9fc43ef6df5d" />
<img width="558" height="462" alt="Screenshot 2026-10-30 140538" src="https://github.com/user-attachments/assets/4847eac2-386e-415d-a3ff-aab9b1239595" />
<img width="452" height="456" alt="Screenshot 2026-10-30 140546" src="https://github.com/user-attachments/assets/7d5bdf89-5447-4fa0-a300-72c67e57cdf3" />
<img width="580" height="463" alt="Screenshot 2026-10-30 140552" src="https://github.com/user-attachments/assets/9d6d3bae-176b-48d2-aceb-f6000324f486" />
<img width="573" height="462" alt="Screenshot 2026-10-30 140600" src="https://github.com/user-attachments/assets/b5517f29-1cfd-4451-8ff0-68f1b21a7a6f" />

## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.


