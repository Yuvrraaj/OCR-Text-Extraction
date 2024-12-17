# Image Processing and OCR Extraction

This project is a comprehensive pipeline for **image processing and text extraction** using OpenCV, Tesseract OCR, and Python. It includes key features like noise removal, image sharpening, resizing, text recognition, and specific data extraction like dates and prices.

## Features
1. **Image Display and Processing**
   - Display images using Matplotlib.
   - Invert, binarize, resize, and sharpen images.
2. **Noise Removal**
   - Reduce noise using dilation, erosion, morphological transformations, and median blurring.
3. **OCR Text Extraction**
   - Extract text from the image using **Tesseract OCR**.
4. **Data and MRP Extraction**
   - Identify dates (e.g., expiration dates) and MRP (Maximum Retail Price) from extracted text.

---

## Project Requirements
Ensure the following libraries and tools are installed:

### Python Libraries
- **OpenCV**
- **Matplotlib**
- **NumPy**
- **Pytesseract**
- **re** (Regex)

Install them using pip:
```bash
pip install opencv-python matplotlib numpy pytesseract
```

### Tesseract OCR
You must install **Tesseract OCR** on your machine and configure the `tesseract_cmd` path.

- Download Tesseract: [Tesseract OCR GitHub](https://github.com/tesseract-ocr/tesseract)
- Set the path to the executable in the code:
```python
pytesseract.pytesseract.tesseract_cmd = r'C:\Program Files\Tesseract-OCR\tesseract.exe'
```

---

## Project Workflow
1. **Input Image**: Load an image file (e.g., `i20.jpg`).
2. **Invert the Image**: Use `cv2.bitwise_not` to invert the image colors.
3. **Grayscale Conversion**: Convert the image to grayscale.
4. **Binarization**: Apply thresholding to create a binary image.
5. **Noise Removal**: Perform dilation, erosion, and blurring to clean the image.
6. **Resizing**: Resize the image for improved OCR accuracy.
7. **Sharpening**: Apply a sharpening kernel filter.
8. **Text Extraction**: Use **Tesseract OCR** to extract text from the processed image.
9. **Date & MRP Extraction**:
   - Use **Regex** to extract expiration dates and prices (MRP) from the OCR text.
   - Process extracted dates into `mm/yyyy` format.

---

## Code Overview
Here is the pipeline summary:
1. **Image Display**:
   - `display()` function to visualize images.
2. **Noise Removal**:
   - `noise_removal()` function for image cleaning.
3. **Resizing & Sharpening**:
   - `resize_image()` scales the image.
   - `sharpen_image()` enhances edges and details.
4. **OCR Text Extraction**:
   - Tesseract OCR extracts text from the image.
5. **Data Extraction**:
   - Regular expressions are used to identify dates and prices.

---

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name
   ```
2. Install dependencies:
   ```bash
   pip install opencv-python matplotlib numpy pytesseract
   ```
3. Update the path to `tesseract.exe` in the code:
   ```python
   pytesseract.pytesseract.tesseract_cmd = r'C:\Program Files\Tesseract-OCR\tesseract.exe'
   ```
4. Run the script:
   ```bash
   python script_name.py
   ```
5. View results:
   - Extracted text is displayed in the terminal.
   - Dates and MRP (if found) are printed as output.

---

## Example Output
Given an image containing text with dates and MRP:

### Extracted Text
```
Manufactured on: 05-05-2022
Expires on: 05-05-2024
MRP: Rs. 249.50
```

### Processed Output
```
Expiration Date: 05/2024
MRP: 249.5
```

---

## File Outputs
- **inverted.png**: Inverted image.
- **gray.png**: Grayscale image.
- **im_bw.png**: Binary image.
- **noise.png**: Noise-removed image.
- **resized.png**: Resized image.
- **sharpened.png**: Sharpened image.

---

## Notes
- Customize thresholds (e.g., `cv2.threshold`) for better results depending on the image.
- Verify Tesseract OCR installation and update the executable path.
- Test different images for robustness.

---

## Future Improvements
- Add pre-processing for rotated images (deskewing).
- Implement multi-language OCR support.
- Enhance regex patterns for other text formats.

---

## License
This project is open-source under the MIT License.

---

## Author
**Yuvraj Jha**

Feel free to contribute or open an issue!
