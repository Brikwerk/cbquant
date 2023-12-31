# Comic Book Quantizer

Comic Book Quantizer (cbquant) is a command-line interface tool that converts images within comic book archive files to palette-based indexed images.

Using cbquant can result in up to 9x smaller comic book archive files, while still preserving the majority of details. This tool is ideal for generating compressed comic books or manga for viewing on grayscale e-ink devices.

## Features

- Quantization of comic book archive images to a specific number of colors, with dithering.
- Optional, separate quantization levels for color images and grayscale images.
- Resize images while maintaining aspect ratio.
- Parallelized conversion for fast quantization.

## Installation

From PyPi:

```bash
pip install cbquant
```

From the Github `main` branch:

```bash
pip install git+https://github.com/Brikwerk/cbquant
```

## Usage

Compress a single .cbz file (called `test.cbz`) to 2 colors for grayscale images and 4 colors for color images:

```bash
cbquant test.cbz --ncolors 2 --color_ncolors 4
```

Compress a directory of comic book archive files and output all compressed files to a new folder:

```bash
cbquant "/path/to/files/*" --ncolors 2 --color_ncolors 4 --height 1872 --output ./quant
```

## Acknowledgements

Thanks to [libimagequant](https://github.com/ImageOptim/libimagequant) and [libimagequant-python](https://github.com/RoadrunnerWMC/libimagequant-python) for the image quantization code used in this tool.
