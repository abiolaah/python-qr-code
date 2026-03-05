## QR Code Generator (Python & Web)

This repository contains two simple QR code generators:

- **Python script** (`tcic-qrcode.py`) that creates a QR image file for a fixed URL.
- **Web app** (`index.html`) that lets you generate and customize QR codes in the browser (with optional logo, colors, dark mode, and social sharing).

### Requirements

- **Python**: 3.8+ (only needed for the script)
- **Python packages**: listed in `requirements.txt`

Install the Python dependency:

```bash
pip install -r requirements.txt
```

### Python Script Usage (`qrcode.py`)

The script uses the `qrcode` library to generate a PNG file with a QR code that points to a predefined Google Forms URL.

Run:

```bash
python qrcode.py
```

This will generate a file named `qr_code.png` in the same directory, using:

- Version 3 QR code
- High error correction
- Black QR on white background

To point the QR code at a different URL or text, edit the `data` variable in `qrcode.py` and re-run the script.

### Web QR Code Generator (`index.html`)

`index.html` is a standalone, client-side QR code generator. You can:

- **Enter text or a URL** to encode.
- **Customize colors** (QR foreground and background).
- **Upload an image or logo** to overlay in the center of the QR code.
- **Toggle dark mode** for the UI.
- **Download the QR** as a PNG.
- **Copy the QR image** to the clipboard (browser support required).
- **Share** the encoded text/URL via Twitter, Facebook, or WhatsApp.

#### How to Run the Web App

You can open the file directly or serve it with a simple HTTP server:

- **Option 1 – Open directly**
  - Double-click `index.html` or open it in your browser.

- **Option 2 – Serve via Python (recommended for some browsers)**

  ```bash
  # from the project root
  python -m http.server 8000
  ```

  Then open `http://localhost:8000/index.html` in your browser.

### Project Structure

- `qrcode.py` – Python script that generates `qr_code.png` for a specific URL.
- `index.html` – Modern, responsive web QR code generator UI.
- `requirements.txt` – Python dependency list for the script.
- `.gitignore` – Git ignore rules for the project.

### Notes

- The web app uses:
  - `qrcode.min.js` from a CDN to generate QR codes in the browser.
  - Font Awesome from a CDN for icons.
- No build step is required; everything runs locally with standard tools.
