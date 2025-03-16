# SCT_SC_2
#IMAGEFOUND
from PIL import Image
import os

image_path = r"C:\Users\stuti\Downloads\main_img.jpg"

# Verify file existence
if os.path.exists(image_path):
    print("File found! Loading image...")
    img = Image.open(image_path)
    img = img.convert("RGB")  # Ensure it's in RGB mode
    img.show()
else:
    print("Error: Image file not found. Check the path.")


#ENCRYPTION
from PIL import Image
import numpy as np

# Load the image
image_path = r"C:\Users\stuti\Downloads\main_img.jpg"
img = Image.open(image_path).convert("RGB")  # Ensure RGB mode

# Convert image to numpy array
img_array = np.array(img)

# Define the encryption key
key = 50  # Change this for different encryption

# Apply XOR encryption (pixel-wise)
encrypted_array = img_array ^ key

# Convert back to an image
encrypted_img = Image.fromarray(encrypted_array)

# Save the encrypted image
encrypted_path = r"C:\Users\stuti\Downloads\encrypted_img.png"
encrypted_img.save(encrypted_path)

# Show the encrypted image
encrypted_img.show()
print(f"✅ Encryption successful! Encrypted image saved at: {encrypted_path}")


#DECRYPTION
from PIL import Image
import numpy as np

# Load the encrypted image
encrypted_image_path = r"C:\Users\stuti\Downloads\encrypted_img.png"
encrypted_img = Image.open(encrypted_image_path).convert("RGB")

# Convert encrypted image to numpy array
encrypted_array = np.array(encrypted_img)

# Define the decryption key (must be the same as encryption key)
key = 50  

# Apply XOR decryption (reverses encryption)
decrypted_array = encrypted_array ^ key
                                
# Convert back to an image
decrypted_img = Image.fromarray(decrypted_array)

# Save and display the decrypted image
decrypted_path = r"C:\Users\stuti\Downloads\decrypted_img.png"
decrypted_img.save(decrypted_path)

# Show the decrypted image
decrypted_img.show()
print(f"✅ Decryption successful! Decrypted image saved at: {decrypted_path}")
