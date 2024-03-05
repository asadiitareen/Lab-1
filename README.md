
# Install required library
# pip install opencv-python
# Import necessary libraries
import cv2 
import matplotlib.pyplot as plt

# Function to load and display an image
def load_and_display_image(image_path):
    img = cv2.imread(image_path)
    
    # Check if the image is loaded successfully
    if img is not None:
        img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
        plt.imshow(img_rgb)
        plt.title("Original Image")
        plt.axis('off')
        plt.show()
    else:
        print(f"Error: Unable to load image from {image_path}")

# Function to resize an image
def resize_image(image_path, scale_percent):
    img = cv2.imread(image_path)
    
    if img is not None:
        width = int(img.shape[1] * scale_percent / 100)
        height = int(img.shape[0] * scale_percent / 100)
        resized_img = cv2.resize(img, (width, height))
        plt.imshow(resized_img)
        plt.title("Resized Image")
        plt.axis('off')
        plt.show()
    else:
        print(f"Error: Unable to load image from {image_path}")

# Function to convert an image to grayscale
def convert_to_grayscale(image_path):
    img = cv2.imread('horse pic.jpg')
    
    if img is not None:
        gray_img = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
        plt.imshow(gray_img, cmap='gray')
        plt.title("Grayscale Image")
        plt.axis('off')
        plt.show()
    else:
        print(f"Error: Unable to load image from {image_path}")

# Function to apply edge detection
def edge_detection(image_path):
    img = cv2.imread(image_path, cv2.IMREAD_GRAYSCALE)
    
    if img is not None:
        edges = cv2.Canny(img, 100, 200)
        plt.imshow(edges, cmap='gray')
        plt.title("Edge Detection")
        plt.axis('off')
        plt.show()
    else:
        print(f"Error: Unable to load image from {image_path}")

# Example usage
image_path = 'horse pic.jpg'  # Assuming the image is in the same directory as your script
load_and_display_image(image_path)
resize_image(image_path, 50)
convert_to_grayscale(image_path)
edge_detection(image_path)
