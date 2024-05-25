import pytesseract
from PIL import Image
import os

# Ensure Tesseract is installed and set its path
pytesseract.pytesseract.tesseract_cmd = r'path_to_tesseract_executable'

def extract_text_from_images(image_folder):
    for filename in os.listdir(image_folder):
        if filename.endswith((".png", ".jpg", ".jpeg")):
            image_path = os.path.join(image_folder, filename)
            text = pytesseract.image_to_string(Image.open(image_path))
            print(f"Text from {filename}:\n{text}\n")

# Provide the folder path containing your images
image_folder = 'path_to_your_image_folder'
extract_text_from_images(image_folder)
