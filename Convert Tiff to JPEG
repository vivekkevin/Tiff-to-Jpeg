import tkinter as tk
from tkinter import filedialog
from PIL import Image, ImageTk

# Disable the DecompressionBombWarning
Image.MAX_IMAGE_PIXELS = None

def convert_tiff_to_jpeg():
    # Ask the user to select the input TIFF file
    input_path = filedialog.askopenfilename(filetypes=[("TIFF Files", "*.tiff;*.tif")])

    if not input_path:
        return

    try:
        # Open the TIFF image
        image = Image.open(input_path)

        # Ask the user to select the output JPEG file
        output_path = filedialog.asksaveasfilename(defaultextension=".jpg", filetypes=[("JPEG Files", "*.jpg")])

        if not output_path:
            return

        # Convert the image to JPEG format
        image.convert("RGB").save(output_path, "JPEG")

        result_label.config(text="Conversion successful!")
    except Exception as e:
        result_label.config(text="Conversion failed: " + str(e))


# Create the main window
window = tk.Tk()
window.title("TIFF to JPEG Converter")

# Create the button for converting TIFF to JPEG
convert_button = tk.Button(window, text="Convert", command=convert_tiff_to_jpeg)
convert_button.pack(pady=10)

# Create a label to display the result
result_label = tk.Label(window, text="")
result_label.pack()

# Start the GUI event loop
window.mainloop()
