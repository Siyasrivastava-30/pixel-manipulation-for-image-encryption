# pixel-manipulation-for-image-encryption
from PIL import Image

def encrypt_image(image_path, key):
    # Open the image file
    with Image.open(image_path) as img:
        # Get the image dimensions
        width, height = img.size
        # Create a new image with the same dimensions
        encrypted_img = Image.new('RGB', (width, height))
        # Iterate over each pixel in the image
        for x in range(width):
            for y in range(height):
                # Get the RGB values of the current pixel
                r, g, b = img.getpixel((x, y))
                # Encrypt the pixel values using the key
                r = (r + key) % 256
                g = (g + key) % 256
                b = (b + key) % 256
                # Set the encrypted pixel values in the new image
                encrypted_img.putpixel((x, y), (r, g, b))
        # Save the encrypted image
        encrypted_img.save('encrypted_image.png')
# Example usage
image_path = 'original_image.png'
key = 123
encrypt_image(image_path, key)
