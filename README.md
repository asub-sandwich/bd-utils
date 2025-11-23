# bd-utils

A small CLI wrapper to aid in the process of calculating bulk density from turntable photogrammetry. 

+ `mov2jpg` - Extract JPEG frames from Apple `.mov` videos using ffmpeg
+ `heic2jpg` - Convert HEIC photos (files or directories) to JPEG using ImageMagick
+ `fbx2obj` - Convert Autodesk FBX models (files or directories) to OBJ using `assimp`

This script was designed to:
1. Work with both `magick convert` and `convert` depending on versioning
2. Optionally - use `parallel` to speed up directory conversions
3. Optionally - use `exiftool` to copy metadata from video frames

---

## Installation

Download script somewhere to your `PATH`, for example:
```bash
  cp bd-utils ~/.local/bin
  chmod +x "$HOME/.local/bin/bd-utils"
```

---

## Dependencies

**Required**
+ `mov2jpg`: `ffmpeg`
+ `heic2jpg`: ImageMagick (`magick` or `convert`, depending)
+ `fbx2obj`: `assimp`

**Optional**
+ `exiftool`
  + Used by `mov2jpg` to copy metadata from the source `.mov` to each extracted `.jpg`.
  + If not installed, only metadata found by `ffmpeg` will be transferred
+ `parallel`
  + Used by `heic2jpg` and `fbx2obj` to speed up directory conversions.
  + If missing, conversion will run in a sequential loop.
  + The script automatically sets a parallel job to use half of the available CPU cores.

---

## Notes

The script supports both:
+ `magick convert input.heic output.jpg` for ImageMagick 7
+ `convert input.heic output.jpg` for ImageMagick

---

## License

GNU GPLv3.0
