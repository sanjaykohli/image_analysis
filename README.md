# Forensic Image Analyzer

A comprehensive, client-side tool for analyzing images for forensic artifacts, hidden data, and AI generation traces.

**[Launch Analyzer](index.html)**

## Features

### 1. Metadata Analysis
Extracts and visualizes hidden metadata embedded in image files.
- **EXIF/IPTC/XMP**: View camera model, settings (ISO, Aperture), and software info.
- **Geolocation**: Extract GPS coordinates and view them on a map.
- **Timestamps**: Analyze creation and modification dates.

### 2. Steganography Detection
Detects potential hidden data or covert communications.
- **String Extraction**: Scans binary data for readable strings (URLs, emails, passwords).
- **Hex Viewer**: Inspect the raw file header and trailer bytes.
- **EOF Analysis**: Detects data appended after the image end-of-file marker.

### 3. AI Forensics
Determines if an image was synthetically generated.
- **Spectral Analysis (FFT)**: Detects grid artifacts common in GANs/Diffusion models.
- **Error Level Analysis (ELA)**: Visualizes compression inconsistencies.
- **Noise Residuals**: Analyzes sensor noise patterns.
- **Texture Consistency**: Checks for unnatural smoothness or uniformity.

### 4. Visual OSINT
Tools for manual inspection and Open-Source Intelligence gathering.
- **Filters**: Edge Detection, Invert, Contrast Boost.
- **Magnifier**: Pixel-level inspection.
- **Details**: Analyze visual clues like text, landmarks, and reflections.

## Usage
1. Open `index.html` in any modern web browser.
2. Drag and drop an image (JPEG, PNG, WEBP).
3. Select the analysis modules you wish to run.
4. Explore the results in the interactive dashboard.

## Privacy
**100% Client-Side.** No images are ever uploaded to a cloud server. All analysis happens locally in your browser using Web Workers and JavaScript.

## Contributing
This is an open-source project. Feel free to contribute or report issues.
[GitHub Repository](https://github.com/sanjaykohli/image_analysis)
