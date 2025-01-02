Steganography Practical: Hiding Data in Images
In this practical, we will walk through an example of hiding secret data (text) within an image using a popular technique called Least Significant Bit (LSB) steganography. This technique involves modifying the least significant bit of the pixels in an image to hide the secret data.

We will use a Python library called Pillow (Python Imaging Library, or PIL) for handling images, and Python’s built-in functionality for data encoding and decoding.

Step 1: Install Required Libraries
First, we need to install the required Python libraries:

```bash
Copy code
pip install pillow
```
Step 2: Hiding Data in an Image
In this step, we will hide a message inside an image using LSB.

Python Code for Hiding Data in Image:
```python

from PIL import Image

# Function to convert text into binary format
def text_to_bin(text):
    return ''.join(format(ord(i), '08b') for i in text)

# Function to embed text in image using LSB technique
def encode_image(image_path, secret_message, output_path):
    # Open the image file
    image = Image.open(image_path)
    binary_message = text_to_bin(secret_message) + '1111111111111110'  # Add delimiter to indicate the end of the message
    data_index = 0
    pixels = image.load()

    for row in range(image.height):
        for col in range(image.width):
            # Get the RGB values of the pixel
            r, g, b = pixels[col, row]

            # Modify the LSB of each color channel with the message
            if data_index < len(binary_message):
                # Modify red channel's LSB
                r = int(format(r, '08b')[:-1] + binary_message[data_index], 2)
                data_index += 1

            if data_index < len(binary_message):
                # Modify green channel's LSB
                g = int(format(g, '08b')[:-1] + binary_message[data_index], 2)
                data_index += 1

            if data_index < len(binary_message):
                # Modify blue channel's LSB
                b = int(format(b, '08b')[:-1] + binary_message[data_index], 2)
                data_index += 1

            # Update the pixel with modified values
            pixels[col, row] = (r, g, b)

            if data_index >= len(binary_message):
                break
        if data_index >= len(binary_message):
            break

    # Save the new image with hidden data
    image.save(output_path)
    print(f"Data successfully hidden in {output_path}")

# Example usage
image_path = 'input_image.png'  # Input image path
secret_message = 'This is a secret message'
output_path = 'encoded_image.png'  # Output image path
encode_image(image_path, secret_message, output_path)

```
Explanation:
Text to Binary Conversion:

The function text_to_bin() converts the secret text message into a binary string.
Embedding Data in the Image:

We open the image using Pillow, then iterate over each pixel of the image.
For each pixel, we modify the least significant bit (LSB) of the red, green, and blue (RGB) channels with the corresponding bits from the binary message.
After all the bits are embedded, we save the new image as encoded_image.png.
Delimiter:

A delimiter 1111111111111110 is added at the end of the message to mark the end of the embedded data.
Step 3: Extracting the Hidden Data from the Image
Once the message is embedded in the image, we can retrieve the hidden data.

Python Code for Extracting Hidden Data:
```python
Copy code
# Function to convert binary data to text
def bin_to_text(binary_data):
    binary_values = [binary_data[i:i + 8] for i in range(0, len(binary_data), 8)]
    message = ''.join([chr(int(bv, 2)) for bv in binary_values])
    return message

# Function to extract hidden data from the image
def decode_image(image_path):
    # Open the encoded image
    image = Image.open(image_path)
    pixels = image.load()
    binary_message = ''
    
    for row in range(image.height):
        for col in range(image.width):
            # Get the RGB values of the pixel
            r, g, b = pixels[col, row]
            
            # Extract the LSB from each channel and form the binary message
            binary_message += format(r, '08b')[-1]
            binary_message += format(g, '08b')[-1]
            binary_message += format(b, '08b')[-1]

    # Find the delimiter to stop reading
    end_marker = '1111111111111110'
    message_end = binary_message.find(end_marker)
    
    if message_end != -1:
        binary_message = binary_message[:message_end]
    else:
        print("No hidden message found.")
        return ""
    
    # Convert binary message to text
    hidden_message = bin_to_text(binary_message)
    return hidden_message

# Example usage
encoded_image_path = 'encoded_image.png'  # Encoded image path
hidden_message = decode_image(encoded_image_path)
print(f"Hidden message: {hidden_message}")

```
Explanation:
Extracting Data from the Image:

We iterate over each pixel of the image and extract the least significant bit from each of the RGB channels.
These bits are concatenated to form a binary string that represents the hidden message.
Stop Condition:

The function checks for the delimiter 1111111111111110 to mark the end of the hidden data and stops reading further.
Binary to Text Conversion:

The extracted binary string is converted back into text using the bin_to_text() function.
Step 4: Running the Practical
Hide the Message:
Run the encoding script to hide a message in the image (input_image.png) and generate a new image (encoded_image.png).
Extract the Message:
Use the decoding script to extract the hidden message from the encoded image.
Conclusion
This practical demonstrates how to hide a message in an image using LSB (Least Significant Bit) steganography.
We used the Pillow library in Python to manipulate the image and embed a secret message.
This technique works well for small amounts of data, as it modifies only the least significant bit of each pixel, making it difficult for the human eye to notice.