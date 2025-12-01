# IMG_FORENSICS_TOOLKIT

**Professional CTF & Security Image Analysis Tool**

Live demo: [https://sanjaykohli.github.io/image_analysis/](https://sanjaykohli.github.io/image_analysis/)

---

## Overview

A professional-grade forensic image analysis toolkit designed for CTF competitions, security research, and digital forensics. Features a terminal aesthetic with real mathematical analysis algorithms - no fake AI logic.

## Key Features

### 🎯 Real Analysis (No Placeholders)
- **Compression Variance**: Mathematical pixel variance calculations
- **Noise Analysis**: Local variance detection algorithms
- **No Fake Verdicts**: Raw mathematical scores for user interpretation

### 🔍 CTF-Optimized Tools

#### Strings Extraction
- Extracts all printable ASCII and Unicode strings (min 4 chars)
- Highlights potential flags: `flag{...}`, `CTF{...}`
- Detects Base64-like patterns
- Shows long alphanumeric sequences (20+ chars)

#### Hex Viewer
- First 2KB and last 2KB binary dumps
- **Magic bytes detection** with file type verification
- Offset/Hex/ASCII view
- Highlights file headers
- Supports: JPEG, PNG, GIF, BMP, TIFF, WEBP

#### Steganography Detection
- **Bit plane analysis** (bits 0-7)
- Individual bit plane visualization
- **Appended data detection** for JPEGs
- Compares file size vs EOI marker (0xFF 0xD9)
- Flags hidden data after image end

#### Threat Intelligence
- URL extraction from binary
- Cryptocurrency address detection (BTC, ETH)
- Hidden archive detection (ZIP, RAR)
- Pattern matching for malicious indicators

### 🎨 Terminal Aesthetic
- Pitch black background (#000000)
- Dark grey panels (#0A0A0A)
- Matrix green accents (#00ff41)
- JetBrains Mono monospace font
- Minimal 1px borders (#333)
- Footer status bar

## Usage

### Quick Start
1. Open `analyzer.html` in a modern browser
2. Load an image or binary file (drag & drop or click)
3. Navigate analysis tabs
4. Export findings as JSON

### Navigation
- **OVERVIEW** - File statistics and preview
- **METADATA** - EXIF data extraction
- **STRINGS** - Printable string extraction
- **HEX_VIEW** - Binary hex dump with magic bytes
- **THREATS** - URL/crypto/archive detection
- **STEGANOGRAPHY** - Bit planes & appended data
- **COMPRESSION** - Variance analysis
- **VISUAL_ANALYSIS** - Image filters
- **TEXT_EXTRACT** - OCR

### Keyboard Shortcuts
```
Ctrl+N: New file
Ctrl+E: Export JSON
1-9: Quick tab navigation
```

## Technical Details

### Compression Analysis
Performs real mathematical calculations:
```javascript
// Local variance
variance = abs(current_pixel - avg_neighbors)
avg_variance = total_variance / pixel_count

// Compression artifact detection
compression_score = sum(abs(pixel - grayscale)) / pixel_count
```

### Strings Extraction Algorithm
```javascript
1. Read file as byte array
2. Extract printable ASCII (32-126)
3. Filter by minimum length (4 chars)
4. Highlight flag patterns
5. Detect Base64-like sequences
```

### Steganography Detection

#### Bit Plane Analysis
Extracts individual bit planes using bitwise operations:
```javascript
bit_0: LSB (least significant bit) - most commonly used for hiding data
bit_7: MSB (most significant bit)
```

#### Appended Data Detection (JPEG)
1. Search for EOI marker (0xFF 0xD9)
2. Calculate: `appended_bytes = file_size - (eoi_position + 2)`
3. Flag if appended_bytes > 0

### Hex Viewer
- Displays offset, hex values, and ASCII representation
- Highlights first 4 bytes (magic number)
- Verifies file signature against extension

## File Support

### Images
- JPEG/JPG - Full analysis including appended data detection
- PNG
- WEBP
- TIFF
- GIF
- BMP

### Non-Images
All features work on any binary file:
- Strings extraction
- Hex viewer
- Threat scanning
- (Image-specific features skipped gracefully)

## CTF Use Cases

### Finding Flags
1. Check **STRINGS** tab for `flag{...}` patterns
2. Examine **HEX_VIEW** for hidden text in header/footer
3. Cycle through **BIT_PLANES** (0-7) for embedded messages
4. Check **APPENDED_DATA** in JPEGs for hidden files

### File Verification
1. Compare **MAGIC_BYTES** to file extension
2. Look for mismatched file signatures
3. Check **METADATA** for manipulation traces

### Steganography Analysis
1. Analyze all 8 bit planes individually
2. Look for patterns in LSB (bit 0)
3. Check compression variance for anomalies
4. Examine data after EOI marker

## Design Philosophy

### No Fake Logic
- ❌ Removed `Math.random()` placeholders
- ✅ Real compression variance calculations
- ✅ Mathematical algorithms only
- ✅ User interprets raw data

### Terminal Aesthetic
- Designed for security professionals
- High-contrast for long analysis sessions
- Monospace font for data inspection
- Minimal, functional interface

## Export

Generates JSON reports with:
```json
{
  "file": {
    "name": "image.jpg",
    "size": 524288,
    "type": "image/jpeg"
  },
  "analysis": {
    "compression_variance": "12.3456",
    "noise_variance": "8.9012",
    "threat_count": "3",
    "strings_found": "47"
  }
}
```

## Privacy & Security

- 🔒 **100% Client-Side** - All processing in browser
- 🔒 **No Upload** - Files never leave your machine
- 🔒 **No Tracking** - Zero analytics or external requests
- 🔒 **Open Source** - Transparent and auditable

## Technologies

- **ExifReader** - EXIF metadata extraction
- **Tesseract.js** - OCR capabilities
- **jsPDF** - Report generation
- **Vanilla JS** - No frameworks required

## Browser Support

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+

## License

Open source - Free for personal and commercial use

---

**>_ IMG_FORENSICS_TOOLKIT**  
Real analysis. No bullshit.

By [Sanjay Kohli](https://github.com/sanjaykohli)
