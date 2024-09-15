# pixel-manipulation-for-image-encryption
from PIL import Image

def encrypt_image(image_path, key):
    # Open the image file
    with Image.open(image_path) as img:
        # Get the image dimensions
        width, height = img.size
image_path = 'original_image.png'
key = 123
encrypt_image(image_path, key)
