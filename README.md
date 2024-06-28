# barcode_reader
## README

### Overview

This project consists of two Python scripts, `encode.py` and `decode.py`, which together encode a given string into a barcode-like image and then decode the image back into the original string. The encoding process translates characters into bars of varying widths, while the decoding process interprets these widths to reconstruct the original string.

### Prerequisites

- Python 3.x
- OpenCV (`cv2` library)
- NumPy
- PIL (Python Imaging Library)

### Files

1. **encode.py**: Encodes a given string into a barcode-like image.
2. **decode.py**: Decodes a barcode-like image back into the original string.

### Installation

To install the required libraries, you can use pip:

```bash
pip install opencv-python numpy pillow
```

### encode.py

This script creates an encoded barcode-like image from a given input text.

#### Steps

1. **Create an empty canvas**:
   - A white canvas of size 400x800 is created using NumPy.

2. **Define variables**:
   - `spacing_between_bars`: Space between the bars.
   - `bar_height_range`: Height range for the bars.
   - `empty_space_height_range`: Height range for shorter bars representing empty space.
   - `bar_width_dict`: Dictionary mapping each character ('a' to 'z') to a unique bar width.

3. **Encode and draw the barcode**:
   - The script converts the input text to lowercase.
   - For each character in the text, it draws a black rectangle of a specific width on the canvas.
   - Spaces are represented by shorter bars.

4. **Save the result as an image**:
   - The resulting barcode image is saved as `output.png`.

#### Usage

Replace the `input_text` variable with your desired text, and run the script:

```python
python encode.py
```

This will generate a barcode image `output.png`.

### decode.py

This script decodes a barcode-like image back into the original string.

#### Steps

1. **Load the image**:
   - The script reads the image file (`130023.png`).

2. **Map bar widths to characters**:
   - A dictionary maps each possible bar width to its corresponding character.

3. **Decode the barcode**:
   - The script examines the middle row of the image.
   - It measures the width of black bars and uses the dictionary to translate these widths into characters.
   - Spaces are represented by a single-width bar.

4. **Print the decoded string**:
   - The decoded string is printed to the console.

#### Usage

Make sure the barcode image is named `130023.png` and run the script:

```python
python decode.py
```

This will print the decoded string to the console.

### Example

To encode the string "Abbas Chaddad" and decode it back:

1. Edit `encode.py` to set `input_text = "Abbas Chaddad"`.
2. Run `encode.py` to generate `output.png`.
3. Rename `output.png` to `130023.png`.
4. Run `decode.py` to print the decoded string.

### Notes

- Ensure the input text in `encode.py` is lowercase or adjust the dictionary in `decode.py` accordingly.
- Adjust paths and filenames as necessary for your setup.
