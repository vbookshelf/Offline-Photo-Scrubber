# Offline Photo Scrubber
A desktop, offline, open source browser based tool to remove hidden EXIF metadata (GPS coordinates, camera serial numbers, timestamps) from PNG and JPG photos.

Most people don’t realize that when they take a photo with a smartphone or digital camera, the device includes hidden metadata (EXIF data) in the image file:

- Exact GPS Coordinates: Pinpointing their home, their child's school, or a secret location.
- Device Footprints: The exact smartphone model, camera serial numbers, and software used.
- Timestamps: The exact second, minute, and date the photo was taken.

This app can be used to scrub out metadata from images.

- Local Processing: The app runs completely in the user's browser via vanilla JavaScript. Because it doesn’t send images to an external server, it offers absolute privacy.

- Lossless Stripping: Most basic tools "clean" an image by rendering it onto a hidden canvas and re-encoding it. That can reduce the picture quality. This code parses the binary chunks of JPEGs and PNGs, cutting out the metadata chunks (APP1 markers for EXIF in JPEGs, eXIf/tEXt chunks in PNGs) without touching the actual image data. The picture quality stays identical to the original image.

- Re-Encoding on Orientation: If an image has an orientation tag (e.g., shot sideways/upside down), the code falls back to re-encoding it at ~92% quality via Canvas to bake the rotation in. This means that it's no longer "lossless" for those specific images.

- Transparency: The app lists all the metadata that was removed.

## How to use

Simply download the project folder and place it on your desktop. Then double click the photo-scrubber.html file. The app will open in your browser. 

<br>

## Revision History

Version 1.0<br>
23-June-2026<br>
Prototype. Released for testing.

<br>

