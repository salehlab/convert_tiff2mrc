
# TIFF to MRC Conversion Script

Welcome to the **TIFF to MRC Conversion Script**! 
This Python tool is designed to easily convert `.tif` or `.tiff` image files (like those used in electron microscopy) into the MRC format. 
You can use it to process single files or batch-convert multiple files in a directory.

## Features
- Converts both `.tif` and `.tiff` files to `.mrc`.
- Supports batch conversion using wildcard patterns (e.g., `*.tif` or `*.tiff`).
- Confirms the number of files to be converted before starting.
- Automatically checks for required Python modules and provides installation instructions if needed.

## Requirements
Make sure you have the following Python packages installed:
- `tifffile`
- `mrcfile`
- `numpy`

If you don't have them, simply install via pip:

```bash
pip install tifffile mrcfile numpy
```

## How to Use

1. Clone this repository:

    ```bash
    git clone https://github.com/yourusername/convert_tiff2mrc.git
    cd convert_tiff2mrc
    ```

2. Make the script executable:

    ```bash
    chmod +x convert_tiff2mrc.py
    ```

3. Place the script (`convert_tiff2mrc.py`) in the same directory as your `.tif` or `.tiff` files.

4. Run the script:

    ```bash
    python convert_tiff2mrc.py
    ```

## Customizing the Script
By default, the script converts all `.tif` and `.tiff` files in the current directory. You can point to a different directory or use custom patterns if needed.

For example, to convert files in a specific directory:

```python
batch_convert_tiff_to_mrc("/path/to/your/directory/*.tif")
```

## Contributing
We welcome contributions! Feel free to submit pull requests or open an issue if you find bugs or have suggestions.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
